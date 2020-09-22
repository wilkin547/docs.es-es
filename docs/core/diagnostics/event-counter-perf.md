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
# <a name="tutorial-measure-performance-using-eventcounters-in-net-core"></a>Tutorial: Medición del rendimiento mediante EventCounters en .NET Core

**Este artículo se aplica a: ✔️** SDK de .NET Core 3.0 y versiones posteriores

En este tutorial se aprende a usar un <xref:System.Diagnostics.Tracing.EventCounter> para medir el rendimiento con una alta frecuencia de eventos. Puede usar los [contadores disponibles](event-counters.md#available-counters) publicados por diversos paquetes oficiales de .NET Core, proveedores de terceros o crear sus propias métricas para la supervisión.

En este tutorial va a:

> [!div class="checklist"]
>
> - Implementar un <xref:System.Diagnostics.Tracing.EventSource>.
> - Supervisar contadores con [dotnet-counters](dotnet-counters.md).

## <a name="prerequisites"></a>Requisitos previos

En el tutorial se usa:

- [SDK de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core) o una versión posterior
- [dotnet-counters](dotnet-counters.md) para supervisar contadores de eventos.
- Una aplicación de [destino de depuración de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) que se va a diagnosticar.

## <a name="get-the-source"></a>Obtención del origen

Se va a usar la aplicación de ejemplo como base para la supervisión. El [repositorio de ASP.NET Core de ejemplo](/samples/dotnet/samples/diagnostic-scenarios) está disponible en el explorador de ejemplos. Descargue el archivo zip, extráigalo una vez descargado y ábralo en el IDE que prefiera. Compile y ejecute la aplicación para asegurarse de que funciona correctamente y luego deténgala.

## <a name="implement-an-eventsource"></a>Implementación de un EventSource

En el caso de los eventos que se producen cada pocos milisegundos, se recomienda que la sobrecarga por evento sea baja (menos de un milisegundo). De lo contrario, el impacto sobre el rendimiento es considerable. El registro de un evento significa que se va a escribir algo en el disco. Si el disco no es lo suficientemente rápido, se pierden eventos. Necesita una solución que no sea el registro del propio evento.

Al trabajar con un gran número de eventos, conocer la medida por evento tampoco es útil. La mayor parte del tiempo, todo lo que se necesita son algunas estadísticas. Por lo tanto, podría obtener las estadísticas dentro del propio proceso y luego escribir un evento de vez en cuando para comunicar las estadísticas, que es lo que hace <xref:System.Diagnostics.Tracing.EventCounter>.

A continuación se muestra un ejemplo de cómo implementar un <xref:System.Diagnostics.Tracing.EventSource?displayProperty=fullName>. Cree un nuevo archivo denominado *MinimalEventCounterSource.cs* y use el fragmento de código como su origen:

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

La línea <xref:System.Diagnostics.Tracing.EventSource.WriteEvent%2A?displayProperty=nameWithType> es la parte <xref:System.Diagnostics.Tracing.EventSource> y no forma parte de <xref:System.Diagnostics.Tracing.EventCounter>, se ha escrito para mostrar que se puede registrar un mensaje junto con el contador de eventos.

## <a name="add-an-action-filter"></a>Incorporación de un filtro de acción

El código fuente de ejemplo es un proyecto de ASP.NET Core. Puede agregar un [filtro de acción](/aspnet/core/mvc/controllers/filters#action-filters) globalmente que registre el tiempo total de las solicitudes. Cree un nuevo archivo denominado *LogRequestTimeFilterAttribute.cs* y use el código siguiente:

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

El filtro de acción inicia <xref:System.Diagnostics.Stopwatch> cuando comienza la solicitud y detiene cuando termina, capturando el tiempo transcurrido. Los milisegundos totales se registran en la instancia singleton `MinimalEventCounterSource`. Para aplicar este filtro, debe agregarlo a la colección de filtros. En el archivo *Startup.cs*, actualice el método `ConfigureServices` al incluir este filtro.

```csharp
public void ConfigureServices(IServiceCollection services) =>
    services.AddControllers(options => options.Filters.Add<LogRequestTimeFilterAttribute>())
            .AddNewtonsoftJson();
```

## <a name="monitor-event-counter"></a>Supervisión del contador de eventos

Con la implementación en un <xref:System.Diagnostics.Tracing.EventSource> y el filtro de acción personalizado, compile e inicie la aplicación.
Ha registrado la métrica en el <xref:System.Diagnostics.Tracing.EventCounter>, pero a menos que acceda a las estadísticas de este, esto no es útil. Para obtener las estadísticas, debe habilitar el <xref:System.Diagnostics.Tracing.EventCounter> mediante la creación de un temporizador que se active con la frecuencia con que quiera que los eventos,así como una escucha, capturen los eventos. Para ello, puede usar [dotnet-counters](dotnet-counters.md).

Use el comando [dotnet-counters ps](dotnet-counters.md#dotnet-counters-ps) para mostrar una lista de procesos de .NET que se pueden supervisar.

```console
dotnet-counters ps
```

Con el identificador de proceso de la salida del comando `dotnet-counters ps`, puede empezar a supervisar el contador de eventos con el siguiente comando `dotnet-counters monitor`:

```console
dotnet-counters monitor --process-id 2196 Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

Mientras se ejecuta el comando `dotnet-counters monitor`, mantenga presionada la tecla <kbd>F5</kbd> en el explorador para iniciar la emisión de solicitudes continuas al punto de conexión `https://localhost:5001/api/values`. Tras unos segundos, detenga al presionar <kbd>q</kbd>.

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

El comando `dotnet-counters monitor` es excelente para la supervisión activa. Pero se recomienda recopilar estas métricas de diagnóstico para el procesamiento y el análisis posteriores. Para ello,use el comando `dotnet-counters collect`. El comando modificador `collect` es similar al comando `monitor`, pero acepta algunos parámetros adicionales. Puede especificar el nombre de archivo de salida y el formato que quiera. En el caso de un archivo JSON denominado *diagnostics.json*, use el siguiente comando:

```console
dotnet-counters collect --process-id 2196 --format json -o diagnostics.json Sample.EventCounter.Minimal Microsoft.AspNetCore.Hosting[total-requests,requests-per-second] System.Runtime[cpu-usage]
```

Una vez más, mientras se ejecuta el comando, mantenga presionada la tecla <kbd>F5</kbd> en el explorador para iniciar la emisión de solicitudes continuas al punto de conexión `https://localhost:5001/api/values`. Tras unos segundos, detenga al presionar <kbd>q</kbd>. Se escribe el archivo *diagnostics.json*. Pero no se aplica sangría al archivo JSON escrito; para mejorar la legibilidad, la sangría se aplica aquí.

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

## <a name="next-steps"></a>Pasos siguientes

> [!div class="nextstepaction"]
> [EventCounters](event-counters.md)
