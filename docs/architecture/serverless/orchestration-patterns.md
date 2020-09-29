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
# <a name="orchestration-patterns"></a><span data-ttu-id="7f689-103">Patrones de orquestación</span><span class="sxs-lookup"><span data-stu-id="7f689-103">Orchestration patterns</span></span>

<span data-ttu-id="7f689-104">Durable Functions facilita la creación de flujos de trabajo con estado que se componen de actividades discretas de larga duración en un entorno sin servidor.</span><span class="sxs-lookup"><span data-stu-id="7f689-104">Durable Functions makes it easier to create stateful workflows that are composed of discrete, long running activities in a serverless environment.</span></span> <span data-ttu-id="7f689-105">Dado que Durable Functions puede realizar el seguimiento del progreso de los flujos de trabajo y establecer puntos de comprobación periódicos en el historial de ejecución, se presta a implementar algunos patrones interesantes.</span><span class="sxs-lookup"><span data-stu-id="7f689-105">Since Durable Functions can track the progress of your workflows and periodically checkpoints the execution history, it lends itself to implementing some interesting patterns.</span></span>

## <a name="function-chaining"></a><span data-ttu-id="7f689-106">Diagrama de encadenamiento de funciones</span><span class="sxs-lookup"><span data-stu-id="7f689-106">Function chaining</span></span>

<span data-ttu-id="7f689-107">En un proceso secuencial típico, las actividades deben ejecutarse una después de otra en un orden determinado.</span><span class="sxs-lookup"><span data-stu-id="7f689-107">In a typical sequential process, activities need to execute one after the other in a particular order.</span></span> <span data-ttu-id="7f689-108">En algunos casos, la actividad siguiente puede requerir una salida de la función anterior.</span><span class="sxs-lookup"><span data-stu-id="7f689-108">Optionally, the upcoming activity may require some output from the previous function.</span></span> <span data-ttu-id="7f689-109">Esta dependencia del orden de las actividades crea una cadena de ejecución de funciones.</span><span class="sxs-lookup"><span data-stu-id="7f689-109">This dependency on the ordering of activities creates a function chain of execution.</span></span>

<span data-ttu-id="7f689-110">La ventaja de utilizar Durable Functions para implementar este patrón de flujo de trabajo proviene de su capacidad para establecer puntos de comprobación.</span><span class="sxs-lookup"><span data-stu-id="7f689-110">The benefit of using Durable Functions to implement this workflow pattern comes from its ability to do checkpointing.</span></span> <span data-ttu-id="7f689-111">Si el servidor se bloquea, se agota el tiempo de espera de la red o se produce algún otro problema, Durable Functions se puede reanudar desde el último estado conocido y continuar la ejecución del flujo de trabajo aunque esté en otro servidor.</span><span class="sxs-lookup"><span data-stu-id="7f689-111">If the server crashes, the network times out or some other issue occurs, Durable functions can resume from the last known state and continue running your workflow even if it's on another server.</span></span>

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

<span data-ttu-id="7f689-112">En el ejemplo de código anterior, la función `CallActivityAsync` es responsable de ejecutar una actividad determinada en una máquina virtual del centro de datos.</span><span class="sxs-lookup"><span data-stu-id="7f689-112">In the preceding code sample, the `CallActivityAsync` function is responsible for running a given activity on a virtual machine in the data center.</span></span> <span data-ttu-id="7f689-113">Si se devuelve "await" y se completa la tarea subyacente, la ejecución se registrará en la tabla de historial.</span><span class="sxs-lookup"><span data-stu-id="7f689-113">When the await returns and the underlying Task completes, the execution will be recorded to the history table.</span></span> <span data-ttu-id="7f689-114">El código de la función de orquestador puede utilizar cualquiera de las construcciones conocidas de la biblioteca TPL y las palabras clave async/await.</span><span class="sxs-lookup"><span data-stu-id="7f689-114">The code in the orchestrator function can make use of any of the familiar constructs of the Task Parallel Library and the async/await keywords.</span></span>

<span data-ttu-id="7f689-115">El código siguiente es un ejemplo simplificado del aspecto que puede tener el método `ProcessPayment`:</span><span class="sxs-lookup"><span data-stu-id="7f689-115">The following code is a simplified example of what the `ProcessPayment` method may look like:</span></span>

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

## <a name="asynchronous-http-apis"></a><span data-ttu-id="7f689-116">API de HTTP asincrónico</span><span class="sxs-lookup"><span data-stu-id="7f689-116">Asynchronous HTTP APIs</span></span>

<span data-ttu-id="7f689-117">En algunos casos, los flujos de trabajo pueden contener actividades que tardan un tiempo relativamente largo en completarse.</span><span class="sxs-lookup"><span data-stu-id="7f689-117">In some cases, workflows may contain activities that take a relatively long period of time to complete.</span></span> <span data-ttu-id="7f689-118">Imagine un proceso que inicia la copia de seguridad de archivos multimedia en Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="7f689-118">Imagine a process that kicks off the backup of media files into blob storage.</span></span> <span data-ttu-id="7f689-119">En función del tamaño y la cantidad de los archivos multimedia, este proceso de copia de seguridad puede tardar horas en completarse.</span><span class="sxs-lookup"><span data-stu-id="7f689-119">Depending on the size and quantity of the media files, this backup process may take hours to complete.</span></span>

<span data-ttu-id="7f689-120">En este escenario, la capacidad de `DurableOrchestrationClient` para comprobar el estado de un flujo de trabajo en ejecución resulta útil.</span><span class="sxs-lookup"><span data-stu-id="7f689-120">In this scenario, the `DurableOrchestrationClient`'s ability to check the status of a running workflow becomes useful.</span></span> <span data-ttu-id="7f689-121">Cuando se usa un `HttpTrigger` para iniciar un flujo de trabajo, se puede utilizar el método `CreateCheckStatusResponse` para devolver una instancia de `HttpResponseMessage`.</span><span class="sxs-lookup"><span data-stu-id="7f689-121">When using an `HttpTrigger` to start a workflow, the `CreateCheckStatusResponse` method can be used to return an instance of `HttpResponseMessage`.</span></span> <span data-ttu-id="7f689-122">Esta respuesta proporciona al cliente un URI en la carga útil que se puede usar para comprobar el estado del proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f689-122">This response provides the client with a URI in the payload that can be used to check the status of the running process.</span></span>

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

<span data-ttu-id="7f689-123">En el resultado de ejemplo siguiente se muestra la estructura de la carga útil de respuesta.</span><span class="sxs-lookup"><span data-stu-id="7f689-123">The sample result below shows the structure of the response payload.</span></span>

```json
{
    "id": "instanceId",
    "statusQueryGetUri": "http://host/statusUri",
    "sendEventPostUri": "http://host/eventUri",
    "terminatePostUri": "http://host/terminateUri"
}
```

<span data-ttu-id="7f689-124">Mediante el cliente HTTP preferido, se pueden realizar solicitudes GET al URI de statusQueryGetUri para inspeccionar el estado del flujo de trabajo en ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f689-124">Using your preferred HTTP client, GET requests can be made to the URI in statusQueryGetUri to inspect the status of the running workflow.</span></span> <span data-ttu-id="7f689-125">La respuesta de estado devuelta debe ser similar al código siguiente.</span><span class="sxs-lookup"><span data-stu-id="7f689-125">The returned status response should resemble the following code.</span></span>

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

<span data-ttu-id="7f689-126">A medida que el proceso continúa, la respuesta de estado cambiará a **Error** o a **Completado**.</span><span class="sxs-lookup"><span data-stu-id="7f689-126">As the process continues, the status response will change to either **Failed** or **Completed**.</span></span> <span data-ttu-id="7f689-127">Después de completarse correctamente, la propiedad **output** de la carga contendrá los datos devueltos.</span><span class="sxs-lookup"><span data-stu-id="7f689-127">On successful completion, the **output** property in the payload will contain any returned data.</span></span>

## <a name="monitoring"></a><span data-ttu-id="7f689-128">Supervisión</span><span class="sxs-lookup"><span data-stu-id="7f689-128">Monitoring</span></span>

<span data-ttu-id="7f689-129">En el caso de tareas periódicas simples, Azure Functions proporciona el elemento `TimerTrigger` que se puede programar en función de una expresión CRON.</span><span class="sxs-lookup"><span data-stu-id="7f689-129">For simple recurring tasks, Azure Functions provides the `TimerTrigger` that can be scheduled based on a CRON expression.</span></span> <span data-ttu-id="7f689-130">El temporizador funciona bien para tareas sencillas y de corta duración, pero puede haber escenarios en los que se necesite una programación más flexible.</span><span class="sxs-lookup"><span data-stu-id="7f689-130">The timer works well for simple, short-lived tasks, but there might be scenarios where more flexible scheduling is needed.</span></span> <span data-ttu-id="7f689-131">Para estos escenarios podrían resultarle de ayuda el patrón de supervisión y Durable Functions.</span><span class="sxs-lookup"><span data-stu-id="7f689-131">This scenario is when the monitoring pattern and Durable Functions can help.</span></span>

<span data-ttu-id="7f689-132">Durable Functions permite intervalos de programación flexibles, administración del ciclo de vida y la posibilidad de crear varios procesos de supervisión a partir de una única función de orquestación.</span><span class="sxs-lookup"><span data-stu-id="7f689-132">Durable Functions allows for flexible scheduling intervals, lifetime management, and the creation of multiple monitor processes from a single orchestration function.</span></span> <span data-ttu-id="7f689-133">Un caso de uso de esta funcionalidad podría ser la creación de monitores para detectar los cambios de precios de las acciones que se completan una vez que se alcanza un determinado umbral.</span><span class="sxs-lookup"><span data-stu-id="7f689-133">One use case for this functionality might be to create watchers for stock price changes that complete once a certain threshold is met.</span></span>

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

<span data-ttu-id="7f689-134">El método `CreateTimer` de `DurableOrchestrationContext` configura la programación de la siguiente invocación del bucle para comprobar si hay cambios en los precios de las acciones.</span><span class="sxs-lookup"><span data-stu-id="7f689-134">`DurableOrchestrationContext`'s `CreateTimer` method sets up the schedule for the next invocation of the loop to check for stock price changes.</span></span> <span data-ttu-id="7f689-135">`DurableOrchestrationContext` también tiene una propiedad `CurrentUtcDateTime` para obtener el valor de fecha y hora actual en formato UTC.</span><span class="sxs-lookup"><span data-stu-id="7f689-135">`DurableOrchestrationContext` also has a `CurrentUtcDateTime` property to get the current DateTime value in UTC.</span></span> <span data-ttu-id="7f689-136">Es mejor usar esta propiedad en lugar de `DateTime.UtcNow` porque se simula con facilidad para la realización de pruebas.</span><span class="sxs-lookup"><span data-stu-id="7f689-136">It's better to use this property instead of `DateTime.UtcNow` because it's easily mocked for testing.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="7f689-137">Recursos recomendados</span><span class="sxs-lookup"><span data-stu-id="7f689-137">Recommended resources</span></span>

- [<span data-ttu-id="7f689-138">Azure Durable Functions</span><span class="sxs-lookup"><span data-stu-id="7f689-138">Azure Durable Functions</span></span>](/azure/azure-functions/durable-functions-overview)
- [<span data-ttu-id="7f689-139">Prueba unitaria en .NET Core y .NET Standard</span><span class="sxs-lookup"><span data-stu-id="7f689-139">Unit Testing in .NET Core and .NET Standard</span></span>](../../core/testing/index.md)

>[!div class="step-by-step"]
><span data-ttu-id="7f689-140">[Anterior](durable-azure-functions.md)
>[Siguiente](serverless-business-scenarios.md)</span><span class="sxs-lookup"><span data-stu-id="7f689-140">[Previous](durable-azure-functions.md)
[Next](serverless-business-scenarios.md)</span></span>
