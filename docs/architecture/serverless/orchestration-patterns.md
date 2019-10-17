---
title: 'Patrones de orquestación: aplicaciones sin servidor'
description: PR de Azure durable Functions
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 2bd81c29e727254af6c8ecf39ee4bfef1f39d009
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522639"
---
# <a name="orchestration-patterns"></a>Patrones de orquestación

Durable Functions facilita la creación de flujos de trabajo con estado que se componen de actividades discretas de larga ejecución en un entorno sin servidor. Dado que Durable Functions puede realizar el seguimiento del progreso de los flujos de trabajo y realiza un punto de comprobación periódico del historial de ejecución, se presta a implementar algunos patrones interesantes.

## <a name="function-chaining"></a>Encadenamiento de funciones

En un proceso secuencial típico, las actividades deben ejecutarse una después de la otra en un orden determinado. Opcionalmente, la actividad próxima puede requerir una salida de la función anterior. Esta dependencia del orden de las actividades crea una cadena de funciones de ejecución.

La ventaja de utilizar Durable Functions para implementar este modelo de flujo de trabajo proviene de su capacidad para realizar puntos de comprobación. Si el servidor se bloquea, se agota el tiempo de espera de la red o se produce algún otro problema, durable Functions se puede reanudar desde el último estado conocido y seguir ejecutando el flujo de trabajo aunque esté en otro servidor.

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

En el ejemplo de código anterior, la función `CallActivityAsync` es responsable de ejecutar una actividad determinada en una máquina virtual del centro de datos. Cuando se devuelve Await y se completa la tarea subyacente, la ejecución se registrará en la tabla de historial. El código de la función de orquestador puede hacer uso de cualquiera de las construcciones conocidas de la biblioteca TPL y las palabras clave Async/Await.

El código siguiente es un ejemplo simplificado de lo que puede tener el método `ProcessPayment`:

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

## <a name="asynchronous-http-apis"></a>API HTTP asincrónicas

En algunos casos, los flujos de trabajo pueden contener actividades que tardan mucho tiempo en completarse. Imagine un proceso que inicia la copia de seguridad de archivos multimedia en el almacenamiento de blobs. En función del tamaño y la cantidad de los archivos multimedia, este proceso de copia de seguridad puede tardar horas en completarse.

En este escenario, la capacidad de `DurableOrchestrationClient` para comprobar el estado de un flujo de trabajo en ejecución resulta útil. Cuando se usa un `HttpTrigger` para iniciar un flujo de trabajo, se puede usar el método `CreateCheckStatusResponse` para devolver una instancia de `HttpResponseMessage`. Esta respuesta proporciona al cliente un URI en la carga útil que se puede usar para comprobar el estado del proceso en ejecución.

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

En el resultado de ejemplo siguiente se muestra la estructura de la carga de respuesta.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Mediante el cliente HTTP preferido, se pueden realizar solicitudes GET en el URI de statusQueryGetUri para inspeccionar el estado del flujo de trabajo en ejecución. La respuesta de estado devuelta debe ser similar al código siguiente.

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

A medida que el proceso continúa, la respuesta de estado cambiará a **error** o **completado**. Cuando se complete correctamente, la propiedad de **salida** de la carga contendrá los datos devueltos.

## <a name="monitoring"></a>Supervisión

En el caso de tareas periódicas simples, Azure Functions proporciona el `TimerTrigger` que se puede programar en función de una expresión CRON. El temporizador funciona bien para tareas sencillas y de corta duración, pero puede haber escenarios en los que se necesite una programación más flexible. Este escenario es cuando el patrón de supervisión y el Durable Functions pueden ayudarle.

Durable Functions permite intervalos de programación flexibles, administración de la duración y la creación de varios procesos de supervisión desde una sola función de orquestación. Un caso de uso de esta funcionalidad podría ser crear monitores para los cambios de precios de las acciones que se completan una vez que se cumple un determinado umbral.

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

el método `CreateTimer` de `DurableOrchestrationContext` configura la programación de la siguiente invocación del bucle para comprobar si hay cambios en los precios de las acciones. `DurableOrchestrationContext` también tiene una propiedad `CurrentUtcDateTime` para obtener el valor DateTime actual en UTC. Es mejor usar esta propiedad en lugar de `DateTime.UtcNow` porque se simula con facilidad para pruebas.

## <a name="recommended-resources"></a>Recursos recomendados

- [Durable Functions de Azure](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
- [Prueba unitaria en .NET Core y .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Anterior](durable-azure-functions.md)
>[Siguiente](serverless-business-scenarios.md)
