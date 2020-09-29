---
title: 'Patrones de orquestación: Aplicaciones sin servidor'
description: Solicitud de incorporación de cambios de Azure Durable Functions
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 6c5f6aaedbc13c47289e102bb59f7b066525b107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171668"
---
# <a name="orchestration-patterns"></a>Patrones de orquestación

Durable Functions facilita la creación de flujos de trabajo con estado que se componen de actividades discretas de larga duración en un entorno sin servidor. Dado que Durable Functions puede realizar el seguimiento del progreso de los flujos de trabajo y establecer puntos de comprobación periódicos en el historial de ejecución, se presta a implementar algunos patrones interesantes.

## <a name="function-chaining"></a>Diagrama de encadenamiento de funciones

En un proceso secuencial típico, las actividades deben ejecutarse una después de otra en un orden determinado. En algunos casos, la actividad siguiente puede requerir una salida de la función anterior. Esta dependencia del orden de las actividades crea una cadena de ejecución de funciones.

La ventaja de utilizar Durable Functions para implementar este patrón de flujo de trabajo proviene de su capacidad para establecer puntos de comprobación. Si el servidor se bloquea, se agota el tiempo de espera de la red o se produce algún otro problema, Durable Functions se puede reanudar desde el último estado conocido y continuar la ejecución del flujo de trabajo aunque esté en otro servidor.

```csharp
[FunctionName("PlaceOrder")]
public static async Task<string> PlaceOrder([OrchestrationTrigger] DurableOrchestrationContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    await context.CallActivityAsync<bool>("CheckAndReserveInventory", orderData);
    await context.CallActivityAsync<bool>("ProcessPayment", orderData);

    string trackingNumber = await context.CallActivityAsync<string>("ScheduleShipping", orderData);
    await context.CallActivityAsync<string>("EmailCustomer", trackingNumber);

    return trackingNumber;
}
```

En el ejemplo de código anterior, la función `CallActivityAsync` es responsable de ejecutar una actividad determinada en una máquina virtual del centro de datos. Si se devuelve "await" y se completa la tarea subyacente, la ejecución se registrará en la tabla de historial. El código de la función de orquestador puede utilizar cualquiera de las construcciones conocidas de la biblioteca TPL y las palabras clave async/await.

El código siguiente es un ejemplo simplificado del aspecto que puede tener el método `ProcessPayment`:

```csharp
[FunctionName("ProcessPayment")]
public static bool ProcessPayment([ActivityTrigger] DurableActivityContext context)
{
    OrderRequestData orderData = context.GetInput<OrderRequestData>();

    ApplyCoupons(orderData);
    if(IssuePaymentRequest(orderData)) {
        return true;
    }

    return false;
}
```

## <a name="asynchronous-http-apis"></a>API de HTTP asincrónico

En algunos casos, los flujos de trabajo pueden contener actividades que tardan un tiempo relativamente largo en completarse. Imagine un proceso que inicia la copia de seguridad de archivos multimedia en Blob Storage. En función del tamaño y la cantidad de los archivos multimedia, este proceso de copia de seguridad puede tardar horas en completarse.

En este escenario, la capacidad de `DurableOrchestrationClient` para comprobar el estado de un flujo de trabajo en ejecución resulta útil. Cuando se usa un `HttpTrigger` para iniciar un flujo de trabajo, se puede utilizar el método `CreateCheckStatusResponse` para devolver una instancia de `HttpResponseMessage`. Esta respuesta proporciona al cliente un URI en la carga útil que se puede usar para comprobar el estado del proceso en ejecución.

```csharp
[FunctionName("OrderWorkflow")]
public static async Task<HttpResponseMessage> Run(
    [HttpTrigger(AuthorizationLevel.Function, "POST")]HttpRequestMessage req,
    [OrchestrationClient ] DurableOrchestrationClient orchestrationClient)
{
    OrderRequestData data = await req.Content.ReadAsAsync<OrderRequestData>();

    string instanceId = await orchestrationClient.StartNewAsync("PlaceOrder", data);

    return orchestrationClient.CreateCheckStatusResponse(req, instanceId);
}
```

En el resultado de ejemplo siguiente se muestra la estructura de la carga útil de respuesta.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Mediante el cliente HTTP preferido, se pueden realizar solicitudes GET al URI de statusQueryGetUri para inspeccionar el estado del flujo de trabajo en ejecución. La respuesta de estado devuelta debe ser similar al código siguiente.

```json
{
    "runtimeStatus": "Running",
    "input": {
        "$type": "DurableFunctionsDemos.OrderRequestData, DurableFunctionsDemos"
    },
    "output": null,
    "createdTime": "2018-01-01T00:22:05Z",
    "lastUpdatedTime": "2018-01-01T00:22:09Z"
}
```

A medida que el proceso continúa, la respuesta de estado cambiará a **Error** o a **Completado**. Después de completarse correctamente, la propiedad **output** de la carga contendrá los datos devueltos.

## <a name="monitoring"></a>Supervisión

En el caso de tareas periódicas simples, Azure Functions proporciona el elemento `TimerTrigger` que se puede programar en función de una expresión CRON. El temporizador funciona bien para tareas sencillas y de corta duración, pero puede haber escenarios en los que se necesite una programación más flexible. Para estos escenarios podrían resultarle de ayuda el patrón de supervisión y Durable Functions.

Durable Functions permite intervalos de programación flexibles, administración del ciclo de vida y la posibilidad de crear varios procesos de supervisión a partir de una única función de orquestación. Un caso de uso de esta funcionalidad podría ser la creación de monitores para detectar los cambios de precios de las acciones que se completan una vez que se alcanza un determinado umbral.

```csharp
[FunctionName("CheckStockPrice")]
public static async Task CheckStockPrice([OrchestrationTrigger] DurableOrchestrationContext context)
{
    StockWatcherInfo stockInfo = context.GetInput<StockWatcherInfo>();
    const int checkIntervalSeconds = 120;
    StockPrice initialStockPrice = null;

    DateTime fireAt;
    DateTime exitTime = context.CurrentUtcDateTime.Add(stockInfo.TimeLimit);

    while (context.CurrentUtcDateTime < exitTime)
    {
        StockPrice currentStockPrice = await context.CallActivityAsync<StockPrice>("GetStockPrice", stockInfo);

        if (initialStockPrice == null)
        {
            initialStockPrice = currentStockPrice;
            fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
            await context.CreateTimer(fireAt, CancellationToken.None);
            continue;
        }

        decimal percentageChange = (initialStockPrice.Price - currentStockPrice.Price) /
                               ((initialStockPrice.Price + currentStockPrice.Price) / 2);

        if (Math.Abs(percentageChange) >= stockInfo.PercentageChange)
        {
            // Change threshold detected
            await context.CallActivityAsync("NotifyStockPercentageChange", currentStockPrice);
            break;
        }

        // Sleep til next polling interval
        fireAt = context.CurrentUtcDateTime.AddSeconds(checkIntervalSeconds);
        await context.CreateTimer(fireAt, CancellationToken.None);
    }
}
```

El método `CreateTimer` de `DurableOrchestrationContext` configura la programación de la siguiente invocación del bucle para comprobar si hay cambios en los precios de las acciones. `DurableOrchestrationContext` también tiene una propiedad `CurrentUtcDateTime` para obtener el valor de fecha y hora actual en formato UTC. Es mejor usar esta propiedad en lugar de `DateTime.UtcNow` porque se simula con facilidad para la realización de pruebas.

## <a name="recommended-resources"></a>Recursos recomendados

- [Azure Durable Functions](/azure/azure-functions/durable-functions-overview)
- [Prueba unitaria en .NET Core y .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Anterior](durable-azure-functions.md)
>[Siguiente](serverless-business-scenarios.md)
