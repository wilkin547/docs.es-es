---
title: 'Administración del rendimiento de las aplicaciones: gRPC para desarrolladores de WCF'
description: Registro, métricas y seguimiento de ASP.NET Core aplicaciones gRPC.
ms.date: 09/02/2019
ms.openlocfilehash: 8a13d1c4df95768e55c90ac491150bfc78ec2bab
ms.sourcegitcommit: 6d1ae17e60384f3b5953ca7b45ac859ec6d4c3a0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "94982347"
---
# <a name="application-performance-management"></a>Administración del rendimiento de las aplicaciones

En entornos de producción como Kubernetes, es importante supervisar las aplicaciones para asegurarse de que se ejecutan de forma óptima. El registro y las métricas son especialmente importantes. ASP.NET Core, incluido gRPC, proporciona compatibilidad integrada para generar y administrar mensajes de registro y datos de métricas, así como datos de *seguimiento* .

## <a name="the-difference-between-logging-and-metrics"></a>La diferencia entre el registro y las métricas

El *registro* se refiere a los mensajes de texto que registran información detallada sobre las cosas que se han producido en el sistema. Los mensajes de registro pueden incluir datos de excepciones, como seguimientos de la pila o datos estructurados que proporcionan contexto sobre el mensaje. La salida del registro se escribe normalmente en un almacén de texto en el que se pueden realizar búsquedas.

*Métricas* se refiere a los datos numéricos que se diseñan y presentan mediante gráficos y gráficos en un panel. El panel proporciona una vista del estado general y el rendimiento de una aplicación. Los datos de métricas también se pueden usar para desencadenar alertas automatizadas cuando se supera un umbral. Estos son algunos ejemplos de datos de métricas:

- Tiempo necesario para procesar solicitudes.
- Número de solicitudes por segundo controladas por una instancia de un servicio.
- El número de solicitudes con error en una instancia.

## <a name="logging-in-aspnet-core-grpc"></a>Inicio de sesión ASP.NET Core gRPC

ASP.NET Core proporciona compatibilidad integrada para el registro, en el formato del paquete NuGet [Microsoft. Extensions. Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) . Las partes principales de esta biblioteca se incluyen con el SDK de Web, por lo que no es necesario instalarla manualmente. De forma predeterminada, los mensajes de registro se escriben en la salida estándar ("Console") y en cualquier depurador asociado. Para escribir registros en almacenes de datos externos persistentes, es posible que necesite importar [paquetes de receptores de registro opcionales](/aspnet/core/fundamentals/logging/?view=aspnetcore-3.0#third-party-logging-providers).

El marco de ASP.NET Core gRPC escribe mensajes de registro de diagnóstico detallados en este marco de registro, por lo que se pueden procesar y almacenar junto con los mensajes de la aplicación.

### <a name="produce-log-messages"></a>Generar mensajes de registro

La extensión de registro se registra automáticamente en el sistema de inserción de dependencias de ASP.NET Core, por lo que puede especificar loggers como un parámetro de constructor en los tipos de servicio de gRPC.

```csharp
public class StockData : Stocks.StocksBase
{
    private readonly ILogger<StockData> _logger;

    public StockData(ILogger<StockData> logger)
    {
        _logger = logger;
    }
}
```

Muchos mensajes de registro, como solicitudes y excepciones, los proporcionan los componentes del marco de ASP.NET Core y gRPC. Agregue sus propios mensajes de registro para proporcionar detalles y contexto sobre la lógica de la aplicación, en lugar de preocuparse por los niveles inferiores.

Para obtener más información sobre la escritura de mensajes de registro y los receptores y destinos de registro disponibles, consulte  [Inicio de sesión en .net Core y ASP.net Core](/aspnet/core/fundamentals/logging/).

## <a name="metrics-in-aspnet-core-grpc"></a>Métricas en ASP.NET Core gRPC

El tiempo de ejecución de .NET Core proporciona un conjunto de componentes para emitir y observar métricas. Estas incluyen API como las <xref:System.Diagnostics.Tracing.EventSource> clases y <xref:System.Diagnostics.Tracing.EventCounter> . Estas API pueden emitir datos numéricos básicos que pueden usar los procesos externos, como la [herramienta global dotnet-counters](../../core/diagnostics/dotnet-counters.md)o el seguimiento de eventos para Windows. Para obtener más información sobre `EventCounter` el uso de en su propio código, vea [Introducción a EventCounter](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.Tracing/documentation/EventCounterTutorial.md).

Para obtener métricas más avanzadas y escribir datos de métricas en una gama más amplia de almacenes de datos, puede probar un proyecto de código abierto denominado [métricas](https://www.app-metrics.io)de la aplicación. Este conjunto de bibliotecas proporciona un amplio conjunto de tipos para instrumentar el código. También ofrece paquetes para escribir métricas en diferentes tipos de destinos que incluyen bases de datos de series temporales, como Prometheus y InfluxDB, y [Application Insights](/azure/azure-monitor/app/app-insights-overview). El paquete NuGet [app. Metrics. AspNetCore. Mvc](https://www.nuget.org/packages/App.Metrics.AspNetCore.Mvc/) incluye incluso un conjunto completo de métricas básicas que se generan automáticamente mediante la integración con el marco de ASP.net Core. El sitio web del proyecto proporciona [plantillas](https://www.app-metrics.io/samples/grafana/) para mostrar dichas métricas con la plataforma de visualización [Grafana](https://grafana.com/) .

### <a name="produce-metrics"></a>Generar métricas

La mayoría de las plataformas de métricas admiten los siguientes tipos:

| Tipo de métrica | Descripción |
| ----------- | ----------- |
| Contador     | Realiza un seguimiento de la frecuencia con la que sucede algo, como solicitudes y errores. |
| Indicador       | Registra un valor único que cambia con el tiempo, como las conexiones activas. |
| Histograma   | Mide una distribución de valores a través de límites arbitrarios. Por ejemplo, un histograma puede realizar un seguimiento del tamaño del conjunto de registros, contando cuántos contenían <10 registros, cuántos contenía 11-100 registros, cuántos contenía 101-1000 registros y cuántos contenía >1000 registros. |
| Medidor       | Mide la velocidad a la que se produce un evento en varios intervalos de tiempo. |
| Temporizador       | Realiza un seguimiento de la duración de los eventos y la velocidad a la que se produce, almacenado como histograma. |

Mediante el uso de *métricas* de la aplicación, `IMetrics` se puede obtener una interfaz a través de la inserción de dependencias y se usa para registrar cualquiera de estas métricas para un servicio de gRPC. En el ejemplo siguiente se muestra cómo contar el número de `Get` solicitudes realizadas a lo largo del tiempo:

```csharp
public class StockData : Stocks.StocksBase
{
    private static readonly CounterOptions GetRequestCounter = new CounterOptions
    {
        Name = "StockData_Get_Requests",
        MeasurementUnit = Unit.Calls
    };

    private readonly IStockRepository _repository;
    private readonly IMetrics _metrics;

    public StockData(IStockRepository repository, IMetrics metrics)
    {
        _repository = repository;
        _metrics = metrics;
    }

    public override async Task<GetResponse> Get(GetRequest request, ServerCallContext context)
    {
        _metrics.Measure.Counter.Increment(GetRequestCounter);

        // Serve request...
    }
}
```

### <a name="store-and-visualize-metrics-data"></a>Almacenar y visualizar datos de métricas

La mejor manera de almacenar los datos de métricas es en una base de datos de *serie temporal*, un almacén de datos especializado diseñado para registrar series de datos numéricas marcadas con marcas de tiempo. Las bases de datos más populares son [Prometheus](https://prometheus.io/) y [InfluxDB](https://www.influxdata.com/products/influxdb-overview/). Microsoft Azure también proporciona almacenamiento de métricas dedicadas a través del servicio [Azure monitor](/azure/azure-monitor/overview) .

La solución de "ir a" actual para visualizar datos de métricas es [Grafana](https://grafana.com), que funciona con una amplia gama de proveedores de almacenamiento. En la siguiente imagen se muestra un panel de Grafana de ejemplo que muestra las métricas de la malla de servicio de Linkerd que ejecuta el ejemplo StockData:

![Captura de pantalla del panel de Grafana](media/application-performance-management/grafana-screenshot.png)

### <a name="metrics-based-alerting"></a>Alertas basadas en métricas

La naturaleza numérica de los datos de métricas significa que es ideal para impulsar los sistemas de alerta, notificando a los desarrolladores o ingenieros de soporte cuando un valor está fuera de una tolerancia definida. Las plataformas ya mencionadas proporcionan compatibilidad para las alertas a través de una variedad de opciones, como correos electrónicos, mensajes de texto o visualizaciones en el panel.

## <a name="distributed-tracing"></a>Seguimiento distribuido

La traza distribuida es un desarrollo relativamente reciente en la supervisión, que ha surgido del creciente uso de microservicios y arquitecturas distribuidas. Una única solicitud desde un explorador cliente, una aplicación o un dispositivo se puede dividir en muchos pasos y subsolicitudes, e implicar el uso de muchos servicios a través de una red. Esto hace que sea difícil correlacionar los mensajes de registro y las métricas con la solicitud específica que los desencadenó. El seguimiento distribuido aplica identificadores a las solicitudes, lo que permite correlacionar los registros y las métricas con una operación determinada. Esto es similar al [seguimiento de un extremo a otro de WCF](../../framework/wcf/diagnostics/tracing/end-to-end-tracing.md), pero se aplica en varias plataformas.

La traza distribuida ha crecido rápidamente en popularidad y está empezando a normalizarse. Cloud Native Computing Foundation crea el [estándar de seguimiento abierto](https://opentracing.io), intentando proporcionar bibliotecas independientes del proveedor para trabajar con back-ends como [Jaeger](https://www.jaegertracing.io/) y [APM elástico](https://www.elastic.co/products/apm). Al mismo tiempo, Google creó el [proyecto OpenCensus](https://opencensus.io/) para resolver el mismo conjunto de problemas. Estos dos proyectos se combinan en un nuevo proyecto, [OpenTelemetry](https://opentelemetry.io), que pretende ser el estándar del sector del futuro.

### <a name="how-distributed-tracing-works"></a>Cómo funciona el seguimiento distribuido

La traza distribuida se basa en el concepto de *intervalos*: operaciones con nombre que forman parte de un único *seguimiento*, que pueden implicar el procesamiento en varios nodos de un sistema. Cuando se inicia una nueva operación, se crea un seguimiento con un identificador único. Para cada suboperación, se crea un intervalo con su propio identificador y identificador de seguimiento. A medida que la solicitud pasa por el sistema, varios componentes pueden crear intervalos *secundarios* que incluyen el identificador de su *elemento primario*. Un intervalo tiene un *contexto*, que contiene los identificadores de intervalo y de seguimiento, así como datos útiles en forma de pares de clave y valor (denominado *equipaje*).

### <a name="distributed-tracing-with-diagnosticsource"></a>Seguimiento distribuido con `DiagnosticSource`

.NET Core tiene un módulo interno que se asigna bien a los seguimientos distribuidos y a los intervalos: [DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#diagnosticsource-users-guide). Además de proporcionar una manera sencilla de generar y consumir diagnósticos dentro de un proceso, el `DiagnosticSource` módulo tiene el concepto de una *actividad*. Una actividad es realmente una implementación de un seguimiento distribuido o un intervalo dentro de un seguimiento. Los elementos internos del módulo se encargan de las actividades primarias/secundarias, incluida la asignación de identificadores. Para obtener más información sobre el uso del `Activity` tipo, consulte la [Guía de usuario de la actividad en github](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-user-guide).

Dado `DiagnosticSource` que forma parte del marco de trabajo principal, es compatible con varios componentes principales. Entre ellas se incluyen <xref:System.Net.Http.HttpClient> , Entity Framework Core y ASP.net Core, incluida la compatibilidad explícita en el marco de trabajo de gRPC. Cuando ASP.NET Core recibe una solicitud, busca un par de encabezados HTTP que coincidan con el estándar de [contexto de seguimiento de W3C](https://www.w3.org/TR/trace-context) . Si se encuentran los encabezados, se inicia una actividad utilizando los valores de identidad y el contexto de los encabezados. Si no se encuentra ningún encabezado, se inicia una actividad con los valores de identidad generados que coinciden con el formato estándar. Los diagnósticos generados por el marco de trabajo o por el código de aplicación durante la vigencia de esta actividad se pueden etiquetar con los identificadores de intervalo y seguimiento. La `HttpClient` compatibilidad se amplía aún más comprobando una actividad actual en cada solicitud y agregando automáticamente los encabezados de seguimiento a la solicitud de salida.

Las bibliotecas de cliente y servidor de ASP.NET Core gRPC incluyen compatibilidad explícita para `DiagnosticSource` y `Activity` , y crean actividades y aplican y usan la información de encabezado de forma automática.

> [!NOTE]
> Todo esto sucede solo si un agente de escucha está consumiendo la información de diagnóstico. Si no hay ningún agente de escucha, no se escribe ningún diagnóstico y no se crea ninguna actividad.

### <a name="add-your-own-diagnosticsource-and-activity"></a>Agregue sus propios `DiagnosticSource` y `Activity`

Para agregar sus propios diagnósticos o crear intervalos explícitos dentro del código de la aplicación, consulte la guía de [usuario de DiagnosticSource](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/DiagnosticSourceUsersGuide.md#instrumenting-with-diagnosticsourcediagnosticlistener) y la guía de usuario de la [actividad](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Diagnostics.DiagnosticSource/src/ActivityUserGuide.md#activity-usage).

### <a name="store-distributed-trace-data"></a>Almacenar datos de seguimiento distribuidos

En el momento de escribir este documento, el proyecto OpenTelemetry todavía está en las primeras fases y solo los paquetes de calidad alfa están disponibles para las aplicaciones .NET. El proyecto OpenTracing actualmente ofrece más bibliotecas maduras.

La API de OpenTracing se describe en la sección siguiente. Si desea usar la API de OpenTelemetry en su aplicación en su lugar, consulte el [repositorio del SDK de OpenTelemetry para .net](https://github.com/open-telemetry/opentelemetry-dotnet) en github.

#### <a name="use-the-opentracing-package-to-store-distributed-trace-data"></a>Usar el paquete OpenTracing para almacenar datos de seguimiento distribuidos

El [paquete NuGet OpenTracing](https://www.nuget.org/packages/OpenTracing/) es compatible con todos los back-ends compatibles con OpenTracing (que se pueden usar independientemente de `DiagnosticSource` ). Hay un paquete adicional del proyecto de contribuciones de API de OpenTracing, [OpenTracing. comtrib. NetCore](https://www.nuget.org/packages/OpenTracing.Contrib.NetCore/). Este paquete agrega un `DiagnosticSource` agente de escucha y escribe automáticamente los eventos y las actividades en un back-end. Habilitar este paquete es tan sencillo como instalarlo desde NuGet y agregarlo como un servicio en la `Startup` clase.

```csharp
public class Startup
{
    public void ConfigureServices(IServiceCollection services)
    {
        services.AddOpenTracing();
    }
}
```

El paquete OpenTracing es una capa de abstracción y, como tal, requiere una implementación específica para el back-end. Las implementaciones de la API de OpenTracing están disponibles para los siguientes back-ends de código abierto.

| Nombre | Paquete | El sitio web |
| ---- | ------- | -------- |
| Jaeger | [Jaeger](https://www.nuget.org/packages/Jaeger/) | [jaegertracing.io](https://jaegertracing.io) |
| APM elástica | [Elástico. APM. NetCoreAll](https://www.nuget.org/packages/Elastic.Apm.NetCoreAll/) | [elastic.co/products/apm](https://www.elastic.co/products/apm) |

Para obtener más información sobre la API de OpenTracing para .NET, vea los repositorios [OpenTracing para c#](https://github.com/opentracing/opentracing-csharp) y [OpenTracing de c#/.net Core](https://github.com/opentracing-contrib/csharp-netcore) en github.

>[!div class="step-by-step"]
>[Anterior](load-balancing.md)
>[Siguiente](appendix.md)
