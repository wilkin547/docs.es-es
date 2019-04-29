---
title: Patrones de orquestación - aplicaciones sin servidor
description: Incorporación de cambios de Azure Durable functions
author: cecilphillip
ms.author: cephilli
ms.date: 06/26/2018
ms.openlocfilehash: 8be499a24e2c5a94132ce07241e17f675e8a1274
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940964"
---
# <a name="orchestration-patterns"></a>Patrones de orquestación

Durable Functions facilita la creación de flujos de trabajo con estado que se componen de actividades discretas y de larga ejecución en un entorno sin servidor. Puesto que Durable Functions puede realizar un seguimiento del progreso de los flujos de trabajo y puntos de comprobación periódicamente el historial de ejecución, se presta a la implementación de algunos patrones interesantes.

## <a name="function-chaining"></a>Encadenamiento de funciones

En un proceso típico secuencial, las actividades que necesite ejecutar uno tras otro en un orden concreto. Opcionalmente, la próxima actividad puede requerir alguna salida de la función anterior. Esta dependencia en el orden de las actividades, crea una cadena de ejecución de función.

La ventaja de utilizar Durable Functions para implementar este patrón de flujo de trabajo radica en su capacidad para realizar los puntos de comprobación. Si el servidor se bloquea, el tiempo de espera de la red o algún otro problema se produce, Durable functions pueden reanudar desde el último estado conocido y seguir ejecutando el flujo de trabajo incluso si está en otro servidor.

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

En el ejemplo de código anterior, el `CallActivityAsync` función es responsable de ejecutar una actividad determinada en una máquina virtual en el centro de datos. Cuando se complete la expresión await devuelve y la tarea subyacente, se grabará la ejecución en la tabla de historial. El código de la función de orquestador puede hacer uso de cualquiera de las construcciones conocidas de la biblioteca TPL y las palabras clave async y await.

El código siguiente es un ejemplo simplificado de lo que el `ProcessPayment` método será similar a esta:

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

## <a name="asynchronous-http-apis"></a>API asincrónicas de HTTP

En algunos casos, los flujos de trabajo pueden contener actividades que tienen un período relativamente largo de tiempo en completarse. Imagine un proceso que inicia la copia de seguridad del medio de archivos en blob storage. Según el tamaño y la cantidad de los archivos multimedia, este proceso de copia de seguridad puede tardar horas en completarse.

En este escenario, el `DurableOrchestrationClient`de capacidad de comprobar el estado de un flujo de trabajo de ejecución es útil. Cuando se usa un `HttpTrigger` para iniciar un flujo de trabajo, el `CreateCheckStatusResponse` método puede utilizarse para devolver una instancia de `HttpResponseMessage`. Esta respuesta proporciona al cliente con un URI en la carga que puede usarse para comprobar el estado del proceso en ejecución.

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

El resultado de ejemplo siguiente muestra la estructura de la carga de respuesta.

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

Con el cliente HTTP que prefiera, GET se pueden realizar solicitudes al URI en statusQueryGetUri para inspeccionar el estado del flujo de trabajo de ejecución. La respuesta de estado devuelto debe ser similar el siguiente código.

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

A medida que continúa el proceso, la respuesta de estado cambiará a cualquiera **Failed** o **completado**. Se completa correctamente, el **salida** propiedad de la carga contendrá los datos devueltos.

## <a name="monitoring"></a>Supervisión

Para las tareas repetitivas simple, Azure Functions proporciona el `TimerTrigger` que se pueden programar basándose en una expresión CRON. El temporizador funciona bien para tareas simples y de corta duración, pero puede haber escenarios donde es necesaria la programación más flexible. Este escenario es cuando el patrón de supervisión y Durable Functions pueden ayudar a.

Durable Functions permite intervalos de programación flexibles, administración de la duración y la creación de varios procesos del monitor de una función de orquestación única. Un caso de uso para esta funcionalidad podría ser crear monitores para los cambios de precio de las acciones que se complete una vez que se alcanza un umbral determinado.

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

`DurableOrchestrationContext`del `CreateTimer` método configura la programación de la siguiente invocación del bucle para comprobar los cambios de precio de las acciones. `DurableOrchestrationContext` También tiene un `CurrentUtcDateTime` propiedad va a obtener el valor de fecha y hora actual en UTC. Es mejor utilizar esta propiedad en lugar de `DateTime.UtcNow` dado que se simula fácilmente para realizar pruebas.

## <a name="recommended-resources"></a>Recursos recomendados

* [Azure Durable Functions](https://docs.microsoft.com/azure/azure-functions/durable-functions-overview)
* [Prueba unitaria en .NET Core y .NET Standard](../../core/testing/index.md)

>[!div class="step-by-step"]
>[Anterior](durable-azure-functions.md)
>[Siguiente](serverless-business-scenarios.md)