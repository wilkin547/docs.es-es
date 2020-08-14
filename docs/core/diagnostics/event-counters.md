---
title: EventCounters de .NET Core
description: En este artículo se aprende qué son los EventCounters, cómo se implementan y cómo se usan.
ms.date: 08/07/2020
ms.openlocfilehash: 68868ff8b4e1393fc3b23af2bc8eef239ac56975
ms.sourcegitcommit: 1e6439ec4d5889fc08cf3bfb4dac2b91931eb827
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2020
ms.locfileid: "88024985"
---
# <a name="eventcounters-in-net-core"></a>EventCounters de .NET Core

**Este artículo se aplica a: ✔️** SDK de .NET Core 3.0 y versiones posteriores

Los EventCounters son las API de .NET Core que se usan para la recopilación ligera, multiplataforma y casi en tiempo real de métricas de rendimiento. Los EventCounters se agregaron como una alternativa multiplataforma a los "contadores de rendimiento" de .NET Framework en Windows. En este artículo se aprende qué son los EventCounters, cómo se implementan y cómo se usan.

El entorno de ejecución de .NET Core y algunas bibliotecas de .NET publican información de diagnóstico básica mediante EventCounters a partir de .NET Core 3.0. Además de los EventCounters proporcionados por el entorno de ejecución de .NET, puede implementar sus propios EventCounters. Los EventCounters se pueden usar para realizar el seguimiento de diversas métricas.

Los EventCounters existen como parte de <xref:System.Diagnostics.Tracing.EventSource> y se insertan automáticamente en las herramientas de escucha de forma periódica. Al igual que todos los demás eventos de <xref:System.Diagnostics.Tracing.EventSource>, se pueden usar en proceso y fuera de proceso mediante <xref:System.Diagnostics.Tracing.EventListener> y EventPipe. Este artículo se centra en las capacidades multiplataforma de los EventCounters y excluye de forma deliberada a PerfView y ETW (seguimiento de eventos para Windows), aunque ambos se pueden usar con los EventCounters.

![Imagen de diagrama de EventCounters en proceso y fuera de proceso](media/event-counters.svg)

[!INCLUDE [available-counters](includes/available-counters.md)]

## <a name="eventcounter-api-overview"></a>Información general sobre la API EventCounter

Hay dos categorías principales de contadores. Algunos contadores son para valores de tipo "tasa", como el número total de excepciones, el número total de GC y el número total de solicitudes. Otros contadores son valores de tipo "instantánea", como el uso del montón, el uso de la CPU y el tamaño del espacio de trabajo. Dentro de cada una de estas categorías de contadores, hay dos tipos de contadores que varían según el modo en que obtienen su valor. Los contadores de sondeo recuperan su valor por medio de una devolución de llamada, mientras que los contadores que no son de sondeo tienen sus valores establecidos directamente en la instancia de contador.

Los contadores se representan mediante las siguientes implementaciones:

* <xref:System.Diagnostics.Tracing.EventCounter>
* <xref:System.Diagnostics.Tracing.IncrementingEventCounter>
* <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>
* <xref:System.Diagnostics.Tracing.PollingCounter>

Una escucha de eventos especifica la duración de los intervalos de medición. Al final de cada intervalo se transmite un valor a la escucha de cada contador. Las implementaciones de un contador determinan las API y los cálculos que se usan para generar el valor de cada intervalo.

1. <xref:System.Diagnostics.Tracing.EventCounter> registra un conjunto de valores. El método <xref:System.Diagnostics.Tracing.EventCounter.WriteMetric%2A?displayProperty=nameWithType> agrega un nuevo valor al conjunto. Con cada intervalo se calcula un resumen estadístico del conjunto, como valor mínimo, máximo y medio. La herramienta [dotnet-counters](dotnet-counters.md) siempre muestra el valor medio. <xref:System.Diagnostics.Tracing.EventCounter> es útil para describir un conjunto discreto de operaciones. Su uso habitual puede incluir la supervisión del tamaño medio en bytes de operaciones de E/S recientes o el valor monetario medio de un conjunto de transacciones financieras.

1. <xref:System.Diagnostics.Tracing.IncrementingEventCounter> registra un total acumulado de cada intervalo de tiempo. El método <xref:System.Diagnostics.Tracing.IncrementingEventCounter.Increment%2A?displayProperty=nameWithType> agrega al total. Por ejemplo, si se llama a `Increment()` tres veces durante un intervalo con valores `1`, `2` y `5`, el total acumulado de `8` se comunica como valor del contador de este intervalo. La herramienta [dotnet-counters](dotnet-counters.md) muestra la tasa como el total / tiempo registrado. <xref:System.Diagnostics.Tracing.IncrementingEventCounter> resulta útil para medir la frecuencia con que se produce una acción, como el número de solicitudes procesadas por segundo.

1. <xref:System.Diagnostics.Tracing.PollingCounter> usa una devolución de llamada para determinar el valor que se comunica. Con cada intervalo de tiempo se invoca a la función de devolución de llamada proporcionada por el usuario y se usa el valor devuelto como valor del contador. <xref:System.Diagnostics.Tracing.PollingCounter> se puede usar para consultar una métrica de un origen externo, por ejemplo, para obtener los bytes libres actuales en un disco. También se puede usar para notificar estadísticas personalizadas que una aplicación puede calcular a petición. Los ejemplos incluyen los informes del percentil 95 de las latencias de solicitud recientes o la proporción de aciertos o errores actual de una caché.

1. <xref:System.Diagnostics.Tracing.IncrementingPollingCounter> usa una devolución de llamada para determinar el valor de incremento comunicado. Con cada intervalo de tiempo se invoca a la devolución de llamada y la diferencia entre la invocación actual y la última es el valor comunicado. La herramienta [dotnet-counters](dotnet-counters.md) siempre muestra la diferencia como una tasa, el valor / tiempo comunicado. Este contador es útil cuando no resulta factible llamar a una API en cada repetición, pero es posible consultar el número total de repeticiones. Por ejemplo, puede notificar el número de bytes escritos en un archivo por segundo, incluso sin una notificación cada vez que se escribe un byte.

## <a name="implement-an-eventsource"></a>Implementación de un EventSource

En el código siguiente se implementa un ejemplo <xref:System.Diagnostics.Tracing.EventSource> expuesto como proveedor `"Sample.EventCounter.Minimal"` con nombre. Este origen contiene un <xref:System.Diagnostics.Tracing.EventCounter> que representa el tiempo de procesamiento de la solicitud. Un contador de este tipo tiene un nombre (es decir, su identificador único en el origen) y un nombre para mostrar, ambos usados por herramientas de escucha como [dotnet-counter](dotnet-counters.md).

:::code language="csharp" source="snippets/EventCounters/MinimalEventCounterSource.cs":::

Use `dotnet-counters ps` para mostrar una lista de los procesos de .NET que se pueden supervisar:

```console
dotnet-counters ps
   1398652 dotnet     C:\Program Files\dotnet\dotnet.exe
   1399072 dotnet     C:\Program Files\dotnet\dotnet.exe
   1399112 dotnet     C:\Program Files\dotnet\dotnet.exe
   1401880 dotnet     C:\Program Files\dotnet\dotnet.exe
   1400180 sample-counters C:\sample-counters\bin\Debug\netcoreapp3.1\sample-counters.exe
```

Pase el nombre del <xref:System.Diagnostics.Tracing.EventSource> al modificador `counter_list` para iniciar la supervisión del contador:

```console
dotnet-counters monitor --process-id 1400180 Sample.EventCounter.Minimal
```

En el siguiente ejemplo se muestra la salida de la supervisión:

```console
Press p to pause, r to resume, q to quit.
    Status: Running

[Samples-EventCounterDemos-Minimal]
    Request Processing Time (ms)                            0.445
```

Presione <kbd>q</kbd> para detener el comando de supervisión.

#### <a name="conditional-counters"></a>Contadores condicionales

Al implementar un <xref:System.Diagnostics.Tracing.EventSource>, se puede crear de forma condicional una instancia de los contadores contenedores al llamar al método <xref:System.Diagnostics.Tracing.EventSource.OnEventCommand%2A?displayProperty=nameWithType> con un valor <xref:System.Diagnostics.Tracing.EventCommandEventArgs.Command> de `EventCommand.Enable`. Para crear una instancia de un contador de forma segura solo si es `null`, use el [operador de asignación de uso combinado de NULL](../../csharp/language-reference/operators/null-coalescing-operator.md). Además, los métodos personalizados pueden evaluar el método <xref:System.Diagnostics.DiagnosticSource.IsEnabled%2A> para determinar si el origen del evento actual está habilitado o no.

:::code language="csharp" source="snippets/EventCounters/ConditionalEventCounterSource.cs":::

> [!TIP]
> Los contadores condicionales son contadores de los que se crean instancias de forma condicional, una microoptimización. El entorno de ejecución adopta este patrón para los escenarios en los que normalmente no se usan contadores, para ahorrar una fracción de un milisegundo.

### <a name="net-core-runtime-example-counters"></a>Contadores de ejemplo del entorno de ejecución de .NET Core

Hay muchas implementaciones de ejemplo excelentes del entorno de ejecución de .NET Core. Esta es la implementación del entorno de ejecución del contador que realiza el seguimiento del tamaño del espacio de trabajo de la aplicación.

```csharp
var workingSetCounter = new PollingCounter(
    "working-set",
    this,
    () => (double)(Environment.WorkingSet / 1_000_000))
{
    DisplayName = "Working Set",
    DisplayUnits = "MB"
};
```

<xref:System.Diagnostics.Tracing.PollingCounter> comunica la cantidad actual de memoria física asignada al proceso (espacio de trabajo) de la aplicación, ya que captura una métrica en un momento dado. La devolución de llamada del sondeo de un valor es la expresión lambda proporcionada, que es simplemente una llamada a la API <xref:System.Environment.WorkingSet?displayProperty=fullName>. <xref:System.Diagnostics.Tracing.DiagnosticCounter.DisplayName> y <xref:System.Diagnostics.Tracing.DiagnosticCounter.DisplayUnits> son propiedades opcionales que se pueden establecer para ayudar al lado del consumidor del contador a mostrar el valor con más claridad. Por ejemplo, [dotnet-counters](dotnet-counters.md) usa estas propiedades para mostrar la versión más descriptiva de los nombres de contador.

> [!IMPORTANT]
> Las propiedades `DisplayName` no están traducidas.

En el caso de <xref:System.Diagnostics.Tracing.PollingCounter> e <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>, no es necesario hacer nada más. Ambos sondean los valores por sí mismos en un intervalo solicitado por el consumidor.

Este es un ejemplo de un contador de entorno de ejecución implementado mediante <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>.

```csharp
var monitorContentionCounter = new IncrementingPollingCounter(
    "monitor-lock-contention-count",
    this,
    () => Monitor.LockContentionCount
)
{
    DisplayName = "Monitor Lock Contention Count",
    DisplayRateTimeScale = TimeSpan.FromSeconds(1)
};
```

<xref:System.Diagnostics.Tracing.IncrementingPollingCounter> usa la API <xref:System.Threading.Monitor.LockContentionCount?displayProperty=nameWithType> para comunicar el incremento del recuento total de contenciones de bloqueo. La propiedad <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale> es opcional pero, cuando se usa, puede proporcionar una sugerencia sobre el intervalo de tiempo en el que se muestra mejor el contador. Por ejemplo, el recuento de contenciones de bloqueo se muestra mejor como _recuento por segundo_, por lo que <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale> se establece en un segundo. La tasa de presentación se puede ajustar a diferentes tipos de contadores de tasa.

> [!NOTE]
> [dotnet-counters](dotnet-counters.md) _no_ usa <xref:System.Diagnostics.Tracing.IncrementingPollingCounter.DisplayRateTimeScale>, y no es necesario que las escuchas de eventos lo usen.

Hay más implementaciones de contador que se pueden usar como referencia en el repositorio del [entorno de ejecución de .NET](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Private.CoreLib/src/System/Diagnostics/Tracing/RuntimeEventSource.cs).

## <a name="concurrency"></a>Simultaneidad

> [!TIP]
> La API de EventCounters no garantiza la seguridad para subprocesos. Cuando varios subprocesos llaman a los delegados pasados a instancias <xref:System.Diagnostics.Tracing.PollingCounter> o <xref:System.Diagnostics.Tracing.IncrementingPollingCounter>, es responsabilidad suya garantizar la seguridad para subprocesos de los delegados.

Por ejemplo, considere el siguiente <xref:System.Diagnostics.Tracing.EventSource> para realizar un seguimiento de las solicitudes.

:::code language="csharp" source="snippets/EventCounters/RequestEventSource.cs":::

Se puede llamar al método `AddRequest()` desde un controlador de solicitudes y `RequestRateCounter` sondea el valor en el intervalo especificado por el consumidor del contador. Pero varios subprocesos pueden llamar al método `AddRequest()` a la vez, con lo que se coloca una condición de carrera sobre `_requestCount`. Una manera alternativa segura para subprocesos de incrementar `_requestCount` es usar <xref:System.Threading.Interlocked.Increment%2A?displayProperty=nameWithType>.

```csharp
public void AddRequest() => Interlocked.Increment(ref _requestCount);
```

## <a name="consume-eventcounters"></a>Uso de EventCounters

Hay dos formas principales de usar EventCounters, en proceso o fuera de proceso. El uso de EventCounters se puede clasificar en tres capas de distintas tecnologías de uso.

- Transporte de eventos en una secuencia sin formato a través de ETW o EventPipe:
  - Las API de ETW están incluidas en el sistema operativo Windows y se puede acceder a EventPipe como una [API de .NET](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/diagnostics-client-library.md#1-attaching-to-a-process-and-dumping-out-all-the-runtime-gc-events-in-real-time-to-the-console) o el [protocolo IPC](https://github.com/dotnet/diagnostics/blob/master/documentation/design-docs/ipc-protocol.md) de diagnóstico.
- Descodificación del flujo de eventos binario en eventos:
  - La [biblioteca TraceEvent](https://www.nuget.org/packages/Microsoft.Diagnostics.Tracing.TraceEvent) controla los formatos de flujo de ETW y EventPipe.
- Herramientas de línea de comandos y GUI:
  - Herramientas como PerfView (ETW o EventPipe), dotnet-counters (solo EventPipe) y dotnet-monitor (solo EventPipe).

### <a name="consume-out-of-proc"></a>Uso fuera de proceso

El uso de EventCounters fuera de proceso es un enfoque muy común. Puede usar [dotnet-counters](dotnet-counters.md) para consumirlos a modo multiplataforma a través de un EventPipe. La herramienta `dotnet-counters` es una herramienta global de CLI de dotnet multiplataforma que se puede usar para supervisar los valores de los contadores. Para obtener información sobre cómo usar `dotnet-counters` para supervisar los contadores, vea [dotnet-counters](dotnet-counters.md) o trabaje con el tutorial [Medición del rendimiento mediante EventCounters](event-counter-perf.md).

#### <a name="dotnet-trace"></a>dotnet-trace

La herramienta `dotnet-trace` se puede usar para consumir los datos del contador a través de EventPipe. Este es un ejemplo de uso de `dotnet-trace` para recopilar datos del contador.

```console
dotnet-trace collect --process-id <pid> Sample.EventCounter.Minimal:0:0:EventCounterIntervalSec=1
```

Para obtener más información sobre cómo recopilar valores de un contador a lo largo del tiempo, vea la documentación de [dotnet-trace](dotnet-trace.md#use-dotnet-trace-to-collect-counter-values-over-time).

#### <a name="azure-application-insights"></a>Azure Application Insights

Azure Monitor puede usar EventCounters, en concreto Azure Application Insights. Los contadores se pueden agregar y quitar; además, el usuario puede especificar contadores personalizados o contadores conocidos. Para obtener más información, vea [Personalización de los contadores que se van a recopilar](/azure/azure-monitor/app/eventcounters#customizing-counters-to-be-collected).

#### <a name="dotnet-monitor"></a>dotnet-monitor

La herramienta `dotnet-monitor` es una herramienta experimental que facilita el acceso a la información de diagnóstico de un proceso de .NET. Para obtener más información, vea [Presentación de dotnet-monitor, una herramienta experimental](https://devblogs.microsoft.com/dotnet/introducing-dotnet-monitor).

### <a name="consume-in-proc"></a>Uso en proceso

Puede usar los valores de un contador por medio de la API <xref:System.Diagnostics.Tracing.EventListener>. <xref:System.Diagnostics.Tracing.EventListener> es una forma en proceso de usar los eventos escritos por todas las instancias de un <xref:System.Diagnostics.Tracing.EventSource> en la aplicación. Para obtener más información sobre cómo usar la API `EventListener`, vea <xref:System.Diagnostics.Tracing.EventListener>.

En primer lugar, es necesario habilitar el <xref:System.Diagnostics.Tracing.EventSource> que genera el valor del contador. Invalide el método <xref:System.Diagnostics.Tracing.EventListener.OnEventSourceCreated%2A?displayProperty=nameWithType> para obtener una notificación cuando se cree un <xref:System.Diagnostics.Tracing.EventSource> y, si es el <xref:System.Diagnostics.Tracing.EventSource> correcto con los EventCounters, puede llamar a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%2A?displayProperty=nameWithType> en él. Esta es una invalidación de ejemplo:

:::code language="csharp" source="snippets/EventCounters/SimpleEventListener.cs" range="16-27":::

#### <a name="sample-code"></a>Código de ejemplo

Esta es una clase <xref:System.Diagnostics.Tracing.EventListener> de ejemplo que imprime todos los nombres y valores de contador del <xref:System.Diagnostics.Tracing.EventSource> del entorno de ejecución de .NET, para publicar sus contadores internos (`System.Runtime`) en algún intervalo.

:::code language="csharp" source="snippets/EventCounters/SimpleEventListener.cs":::

Como se ha mostrado anteriormente, _debe_ asegurarse de que el argumento `"EventCounterIntervalSec"` esté establecido en el argumento `filterPayload` al llamar a <xref:System.Diagnostics.Tracing.EventListener.EnableEvents%2A>. De lo contrario, los contadores no pueden vaciar valores, ya que no saben en qué intervalo se debe hacer.

## <a name="see-also"></a>Consulte también

- [dotnet-counters](dotnet-counters.md)
- [dotnet-trace](dotnet-trace.md)
- <xref:System.Diagnostics.Tracing.EventCounter>
- <xref:System.Diagnostics.Tracing.EventListener>
- <xref:System.Diagnostics.Tracing.EventSource>
