---
title: Medición del rendimiento mediante EventCounters en .NET Core
description: En este tutorial se aprende a medir el rendimiento mediante EventCounters.
ms.date: 08/07/2020
ms.topic: tutorial
ms.openlocfilehash: db9a0889d46cc4db02baac60cbed6f6e0ba6856b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90538571"
---
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a><span data-ttu-id="53d0a-103">Tutorial: Medición del rendimiento mediante EventCounters en .NET Core</span><span class="sxs-lookup"><span data-stu-id="53d0a-103">Tutorial: Measure performance using EventCounters in .NET Core</span></span>

<span data-ttu-id="53d0a-104">**Este artículo se aplica a: ✔️** SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="53d0a-104">**This article applies to: ✔️** .NET Core 3.0 SDK and later versions</span></span>

<span data-ttu-id="53d0a-105">En este tutorial se aprende a usar un <xref:System.Diagnostics.Tracing.EventCounter> para medir el rendimiento con una alta frecuencia de eventos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-105">In this tutorial, you'll learn how an <xref:System.Diagnostics.Tracing.EventCounter> can be used to measure performance with a high frequency of events.</span></span> <span data-ttu-id="53d0a-106">Puede usar los [contadores disponibles](event-counters.md#available-counters) publicados por diversos paquetes oficiales de .NET Core, proveedores de terceros o crear sus propias métricas para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="53d0a-106">You can use the [available counters](event-counters.md#available-counters) published by various official .NET Core packages, third-party providers, or create your own metrics for monitoring.</span></span>

<span data-ttu-id="53d0a-107">En este tutorial va a:</span><span class="sxs-lookup"><span data-stu-id="53d0a-107">In this tutorial, you will:</span></span>

> [!div class="checklist"]
>
> - <span data-ttu-id="53d0a-108">Implementar un <xref:System.Diagnostics.Tracing.EventSource>.</span><span class="sxs-lookup"><span data-stu-id="53d0a-108">Implement an <xref:System.Diagnostics.Tracing.EventSource>.</span></span>
> - <span data-ttu-id="53d0a-109">Supervisar contadores con [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="53d0a-109">Monitor counters with [dotnet-counters](dotnet-counters.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="53d0a-110">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="53d0a-110">Prerequisites</span></span>

<span data-ttu-id="53d0a-111">En el tutorial se usa:</span><span class="sxs-lookup"><span data-stu-id="53d0a-111">The tutorial uses:</span></span>

- <span data-ttu-id="53d0a-112">[SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior</span><span class="sxs-lookup"><span data-stu-id="53d0a-112">[.NET Core 3.1 SDK](https://dotnet.microsoft.com/download/dotnet-core) or a later version.</span></span>
- <span data-ttu-id="53d0a-113">[dotnet-counters](dotnet-counters.md) para supervisar contadores de eventos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-113">[dotnet-counters](dotnet-counters.md) to monitor event counters.</span></span>
- <span data-ttu-id="53d0a-114">Una aplicación de [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) que se va a diagnosticar.</span><span class="sxs-lookup"><span data-stu-id="53d0a-114">A [sample debug target](/samples/dotnet/samples/diagnostic-scenarios) app to diagnose.</span></span>

## <a name="get-the-source"></a><span data-ttu-id="53d0a-115">Obtención del origen</span><span class="sxs-lookup"><span data-stu-id="53d0a-115">Get the source</span></span>

<span data-ttu-id="53d0a-116">Se va a usar la aplicación de ejemplo como base para la supervisión.</span><span class="sxs-lookup"><span data-stu-id="53d0a-116">The sample application will be used as a basis for monitoring.</span></span> <span data-ttu-id="53d0a-117">El [repositorio de ASP.NET Core de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) está disponible en el explorador de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-117">The [sample ASP.NET Core repository](/samples/dotnet/samples/diagnostic-scenarios) is available from the samples browser.</span></span> <span data-ttu-id="53d0a-118">Descargue el archivo zip, extráigalo una vez descargado y ábralo en el IDE que prefiera.</span><span class="sxs-lookup"><span data-stu-id="53d0a-118">You download the zip file, extract it once downloaded, and open it in your favorite IDE.</span></span> <span data-ttu-id="53d0a-119">Compile y ejecute la aplicación para asegurarse de que funciona correctamente y luego deténgala.</span><span class="sxs-lookup"><span data-stu-id="53d0a-119">Build and run the application to ensure that it works properly, then stop the application.</span></span>

## <a name="implement-an-eventsource"></a><span data-ttu-id="53d0a-120">Implementación de un EventSource</span><span class="sxs-lookup"><span data-stu-id="53d0a-120">Implement an EventSource</span></span>

<span data-ttu-id="53d0a-121">En el caso de los eventos que se producen cada pocos milisegundos, se recomienda que la sobrecarga por evento sea baja (menos de un milisegundo).</span><span class="sxs-lookup"><span data-stu-id="53d0a-121">For events that happen every few milliseconds, you'll want the overhead per event to be low (less than a millisecond).</span></span> <span data-ttu-id="53d0a-122">De lo contrario, el impacto sobre el rendimiento es considerable.</span><span class="sxs-lookup"><span data-stu-id="53d0a-122">Otherwise, the impact on performance will be significant.</span></span> <span data-ttu-id="53d0a-123">El registro de un evento significa que se va a escribir algo en el disco.</span><span class="sxs-lookup"><span data-stu-id="53d0a-123">Logging an event means you're going to write something to disk.</span></span> <span data-ttu-id="53d0a-124">Si el disco no es lo suficientemente rápido, se pierden eventos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-124">If the disk is not fast enough, you will lose events.</span></span> <span data-ttu-id="53d0a-125">Necesita una solución que no sea el registro del propio evento.</span><span class="sxs-lookup"><span data-stu-id="53d0a-125">You need a solution other than logging the event itself.</span></span>

<span data-ttu-id="53d0a-126">Al trabajar con un gran número de eventos, conocer la medida por evento tampoco es útil.</span><span class="sxs-lookup"><span data-stu-id="53d0a-126">When dealing with a large number of events, knowing the measure per event is not useful either.</span></span> <span data-ttu-id="53d0a-127">La mayor parte del tiempo, todo lo que se necesita son algunas estadísticas.</span><span class="sxs-lookup"><span data-stu-id="53d0a-127">Most of the time all you need is just some statistics out of it.</span></span> <span data-ttu-id="53d0a-128">Por lo tanto, podría obtener las estadísticas dentro del propio proceso y luego escribir un evento de vez en cuando para comunicar las estadísticas, que es lo que hace <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="53d0a-128">So you could get the statistics within the process itself and then write an event once in a while to report the statistics, that's what <xref:System.Diagnostics.Tracing.EventCounter> will do.</span></span>

<span data-ttu-id="53d0a-129">A continuación se muestra un ejemplo de cómo implementar un <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="53d0a-129">Below is an example of how to implement an <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>.</span></span> <span data-ttu-id="53d0a-130">Cree un nuevo archivo denominado *MinimalEventCounterSource.cs* y use el fragmento de código como su origen:</span><span class="sxs-lookup"><span data-stu-id="53d0a-130">Create a new file named *MinimalEventCounterSource.cs* and use the code snippet as its source:</span></span>

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

<span data-ttu-id="53d0a-131">La línea <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> es la parte <xref:System.Diagnostics.Tracing.EventSource> y no forma parte de <xref:System.Diagnostics.Tracing.EventCounter>, se ha escrito para mostrar que se puede registrar un mensaje junto con el contador de eventos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-131">The <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> line is the <xref:System.Diagnostics.Tracing.EventSource> part and is not part of <xref:System.Diagnostics.Tracing.EventCounter>, it was written to show that you can log a message together with the event counter.</span></span>

## <a name="add-an-action-filter"></a><span data-ttu-id="53d0a-132">Incorporación de un filtro de acción</span><span class="sxs-lookup"><span data-stu-id="53d0a-132">Add an action filter</span></span>

<span data-ttu-id="53d0a-133">El código fuente de ejemplo es un proyecto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="53d0a-133">The sample source code is an ASP.NET Core project.</span></span> <span data-ttu-id="53d0a-134">Puede agregar un [filtro de acción](/aspnet/core/mvc/controllers/filters#action-filters) globalmente que registre el tiempo total de las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="53d0a-134">You can add an [action filter](/aspnet/core/mvc/controllers/filters#action-filters) globally that will log the total request time.</span></span> <span data-ttu-id="53d0a-135">Cree un nuevo archivo denominado *LogRequestTimeFilterAttribute.cs* y use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="53d0a-135">Create a new file named *LogRequestTimeFilterAttribute.cs*, and use the following code:</span></span>

```csharp
using System.Diagnostics;
using Microsoft.AspNetCore.Http.Extensions;
using Microsoft.AspNetCore.Mvc.Filters;

namespace DiagnosticScenarios
{
    public class LogRequestTimeFilterAttribute : ActionFilterAttribute
    {
        readonly Stopwatch _stopwatch = new Stopwatch();

        public override void OnActionExecuting(ActionExecutingContext context) => _stopwatch.Start();

        public override void OnActionExecuted(ActionExecutedContext context)
        {
            _stopwatch.Stop();

            MinimalEventCounterSource.Log.Request(
                context.HttpContext.Request.GetDisplayUrl(), _stopwatch.ElapsedMilliseconds);
        }
    }
}
```

<span data-ttu-id="53d0a-136">El filtro de acción inicia <xref:System.Diagnostics.Stopwatch> cuando comienza la solicitud y detiene cuando termina, capturando el tiempo transcurrido.</span><span class="sxs-lookup"><span data-stu-id="53d0a-136">The action filter starts a <xref:System.Diagnostics.Stopwatch> as the request begins, and stops after it has completed, capturing the elapsed time.</span></span> <span data-ttu-id="53d0a-137">Los milisegundos totales se registran en la instancia singleton `MinimalEventCounterSource`.</span><span class="sxs-lookup"><span data-stu-id="53d0a-137">The total milliseconds is logged to the `MinimalEventCounterSource` singleton instance.</span></span> <span data-ttu-id="53d0a-138">Para aplicar este filtro, debe agregarlo a la colección de filtros.</span><span class="sxs-lookup"><span data-stu-id="53d0a-138">In order for this filter to be applied, you need to add it to the filters collection.</span></span> <span data-ttu-id="53d0a-139">En el archivo *Startup.cs*, actualice el método `ConfigureServices` al incluir este filtro.</span><span class="sxs-lookup"><span data-stu-id="53d0a-139">In the *Startup.cs* file, update the `ConfigureServices` method in include this filter.</span></span>

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a><span data-ttu-id="53d0a-140">Supervisión del contador de eventos</span><span class="sxs-lookup"><span data-stu-id="53d0a-140">Monitor event counter</span></span>

<span data-ttu-id="53d0a-141">Con la implementación en un <xref:System.Diagnostics.Tracing.EventSource> y el filtro de acción personalizado, compile e inicie la aplicación.</span><span class="sxs-lookup"><span data-stu-id="53d0a-141">With the implementation on an <xref:System.Diagnostics.Tracing.EventSource> and the custom action filter, build and launch the application.</span></span>
<span data-ttu-id="53d0a-142">Ha registrado la métrica en el <xref:System.Diagnostics.Tracing.EventCounter>, pero a menos que acceda a las estadísticas de este, esto no es útil.</span><span class="sxs-lookup"><span data-stu-id="53d0a-142">You logged the metric to the <xref:System.Diagnostics.Tracing.EventCounter>, but unless you access the statistics from of it, it is not useful.</span></span> <span data-ttu-id="53d0a-143">Para obtener las estadísticas, debe habilitar el <xref:System.Diagnostics.Tracing.EventCounter> mediante la creación de un temporizador que se active con la frecuencia con que quiera que los eventos,así como una escucha, capturen los eventos.</span><span class="sxs-lookup"><span data-stu-id="53d0a-143">To get the statistics, you need to enable the <xref:System.Diagnostics.Tracing.EventCounter> by creating a timer that fires as frequently as you want the events, as well as a listener to capture the events.</span></span> <span data-ttu-id="53d0a-144">Para ello, puede usar [dotnet-counters](dotnet-counters.md).</span><span class="sxs-lookup"><span data-stu-id="53d0a-144">To do that, you can use [dotnet-counters](dotnet-counters.md).</span></span>

<span data-ttu-id="53d0a-145">Use el comando [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) para mostrar una lista de procesos de .NET que se pueden supervisar.</span><span class="sxs-lookup"><span data-stu-id="53d0a-145">Use the [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) command to display a list of .NET processes that can be monitored.</span></span>

```console
dotnet-counters ps
```

<span data-ttu-id="53d0a-146">Con el identificador de proceso de la salida del comando `dotnet-counters ps`, puede empezar a supervisar el contador de eventos con el siguiente comando `dotnet-counters monitor`:</span><span class="sxs-lookup"><span data-stu-id="53d0a-146">Using the process identifier from the output of the `dotnet-counters ps` command, you can start monitoring the event counter with the following `dotnet-counters monitor` command:</span></span>

```console
dotnet-counters monitor --process-id 2196 Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

<span data-ttu-id="53d0a-147">Mientras se ejecuta el comando `dotnet-counters monitor`, mantenga presionada la tecla <kbd>F5</kbd> en el explorador para iniciar la emisión de solicitudes continuas al punto de conexión `https://localhost:5001/api/values`.</span><span class="sxs-lookup"><span data-stu-id="53d0a-147">While the `dotnet-counters monitor` command is running, hold <kbd>F5</kbd> on the browser to start issuing continuous requests to the `https://localhost:5001/api/values` endpoint.</span></span> <span data-ttu-id="53d0a-148">Tras unos segundos, detenga al presionar <kbd>q</kbd>.</span><span class="sxs-lookup"><span data-stu-id="53d0a-148">After a few seconds stop by pressing <kbd>q</kbd></span></span>

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Microsoft.AspNetCore.Hosting]
    Request Rate / 1 sec                               9
    Total Requests                                   134
[System.Runtime]
    CPU Usage (%)                                     13
[Sample.EventCounter.Minimal]
    Request Processing Time (ms)                      34.5
```

<span data-ttu-id="53d0a-149">El comando `dotnet-counters monitor` es excelente para la supervisión activa.</span><span class="sxs-lookup"><span data-stu-id="53d0a-149">The `dotnet-counters monitor` command is great for active monitoring.</span></span> <span data-ttu-id="53d0a-150">Pero se recomienda recopilar estas métricas de diagnóstico para el procesamiento y el análisis posteriores.</span><span class="sxs-lookup"><span data-stu-id="53d0a-150">However, you may want to collect these diagnostic metrics for post processing and analysis.</span></span> <span data-ttu-id="53d0a-151">Para ello,use el comando `dotnet-counters collect`.</span><span class="sxs-lookup"><span data-stu-id="53d0a-151">For that, use the `dotnet-counters collect` command.</span></span> <span data-ttu-id="53d0a-152">El comando modificador `collect` es similar al comando `monitor`, pero acepta algunos parámetros adicionales.</span><span class="sxs-lookup"><span data-stu-id="53d0a-152">The `collect` switch command is similar to the `monitor` command, but accepts a few additional parameters.</span></span> <span data-ttu-id="53d0a-153">Puede especificar el nombre de archivo de salida y el formato que quiera.</span><span class="sxs-lookup"><span data-stu-id="53d0a-153">You can specify the desired output file name and format.</span></span> <span data-ttu-id="53d0a-154">En el caso de un archivo JSON denominado *diagnostics.json*, use el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="53d0a-154">For a JSON file named *diagnostics.json* use the following command:</span></span>

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

<span data-ttu-id="53d0a-155">Una vez más, mientras se ejecuta el comando, mantenga presionada la tecla <kbd>F5</kbd> en el explorador para iniciar la emisión de solicitudes continuas al punto de conexión `https://localhost:5001/api/values`.</span><span class="sxs-lookup"><span data-stu-id="53d0a-155">Again, while the command is running, hold <kbd>F5</kbd> on the browser to start issuing continuous requests to the `https://localhost:5001/api/values` endpoint.</span></span> <span data-ttu-id="53d0a-156">Tras unos segundos, detenga al presionar <kbd>q</kbd>.</span><span class="sxs-lookup"><span data-stu-id="53d0a-156">After a few seconds stop by pressing <kbd>q</kbd>.</span></span> <span data-ttu-id="53d0a-157">Se escribe el archivo *diagnostics.json*.</span><span class="sxs-lookup"><span data-stu-id="53d0a-157">The *diagnostics.json* file is written.</span></span> <span data-ttu-id="53d0a-158">Pero no se aplica sangría al archivo JSON escrito; para mejorar la legibilidad, la sangría se aplica aquí.</span><span class="sxs-lookup"><span data-stu-id="53d0a-158">The JSON file that is written is not indented, however; for readability it is indented here.</span></span>

```json
{
  "TargetProcess": "DiagnosticScenarios",
  "StartTime": "8/5/2020 3:02:45 PM",
  "Events": [
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:47Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:48Z",
      "provider": "System.Runtime",
      "name": "CPU Usage (%)",
      "counterType": "Metric",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Request Rate / 1 sec",
      "counterType": "Rate",
      "value": 0
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Microsoft.AspNetCore.Hosting",
      "name": "Total Requests",
      "counterType": "Metric",
      "value": 134
    },
    {
      "timestamp": "2020-08-05 15:02:50Z",
      "provider": "Sample.EventCounter.Minimal",
      "name": "Request Processing Time (ms)",
      "counterType": "Metric",
      "value": 0
    }
  ]
}
```

## <a name="next-steps"></a><span data-ttu-id="53d0a-159">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="53d0a-159">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="53d0a-160">EventCounters</span><span class="sxs-lookup"><span data-stu-id="53d0a-160">EventCounters</span></span>](event-counters.md)
