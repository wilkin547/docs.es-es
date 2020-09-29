---
title: 'Application Insights: Aplicaciones sin servidor'
description: Application Insights es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnosticar problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 42791b052ebb068c9b7109291e66b30b47e5821f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173326"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="a481a-103">Telemetría con Application Insights</span><span class="sxs-lookup"><span data-stu-id="a481a-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="a481a-104">[Application Insights](/azure/application-insights) es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnosticar problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.</span><span class="sxs-lookup"><span data-stu-id="a481a-104">[Application Insights](/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="a481a-105">Puede activar Application Insights para las aplicaciones de funciones simplemente activando un conmutador en el portal.</span><span class="sxs-lookup"><span data-stu-id="a481a-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="a481a-106">Application Insights proporciona todas estas funcionalidades sin necesidad de configurar un servidor o de configurar su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="a481a-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="a481a-107">Todas las funcionalidades de Application Insights se proporcionan como un servicio que se integra automáticamente con sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="a481a-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Logotipo de Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="a481a-109">Agregar Application Insights a las aplicaciones existentes es tan sencillo como agregar una clave de instrumentación a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a481a-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="a481a-110">Con Application Insights puede:</span><span class="sxs-lookup"><span data-stu-id="a481a-110">With Application Insights you can:</span></span>

- <span data-ttu-id="a481a-111">Crear gráficos y alertas personalizados basados en métricas como el número de invocaciones de funciones, el tiempo necesario para ejecutar una función y las excepciones</span><span class="sxs-lookup"><span data-stu-id="a481a-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
- <span data-ttu-id="a481a-112">Analizar errores y excepciones de servidor</span><span class="sxs-lookup"><span data-stu-id="a481a-112">Analyze failures and server exceptions</span></span>
- <span data-ttu-id="a481a-113">Analizar en profundidad el rendimiento por operación y medir el tiempo que se tarda en llamar a dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="a481a-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
- <span data-ttu-id="a481a-114">Supervisar el uso de CPU, la memoria y la velocidad en todos los servidores que hospedan las aplicaciones de funciones</span><span class="sxs-lookup"><span data-stu-id="a481a-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
- <span data-ttu-id="a481a-115">Ver un streaming en vivo de métricas que incluya el recuento de solicitudes y la latencia de las aplicaciones de funciones</span><span class="sxs-lookup"><span data-stu-id="a481a-115">View a live stream of metrics including request count and latency for your function apps</span></span>
- <span data-ttu-id="a481a-116">Usar [Analytics](/azure/application-insights/app-insights-analytics) para buscar, consultar y crear gráficos personalizados con los datos de las funciones</span><span class="sxs-lookup"><span data-stu-id="a481a-116">Use [Analytics](/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Explorador de métricas](./media/metrics-explorer.png)

<span data-ttu-id="a481a-118">Además de la telemetría integrada, también es posible generar datos de telemetría personalizados.</span><span class="sxs-lookup"><span data-stu-id="a481a-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="a481a-119">En el fragmento de código siguiente se crea un cliente de telemetría personalizado mediante la clave de instrumentación establecida para la aplicación de funciones:</span><span class="sxs-lookup"><span data-stu-id="a481a-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="a481a-120">El código siguiente mide cuánto tiempo se tarda en insertar una nueva fila en una instancia de [Azure Table Storage](/azure/cosmos-db/table-storage-overview):</span><span class="sxs-lookup"><span data-stu-id="a481a-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="a481a-121">Se muestra el gráfico de rendimiento resultante:</span><span class="sxs-lookup"><span data-stu-id="a481a-121">The resulting performance graph is shown:</span></span>

![Telemetría personalizada](./media/custom-telemetry.png)

<span data-ttu-id="a481a-123">La telemetría personalizada muestra que el tiempo promedio para insertar una nueva fila es de 32,6 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="a481a-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="a481a-124">Application Insights proporciona una forma eficaz y cómoda de registrar la telemetría detallada de las aplicaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="a481a-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="a481a-125">Tiene un control total sobre el nivel de seguimiento y registro que se proporciona.</span><span class="sxs-lookup"><span data-stu-id="a481a-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="a481a-126">Puede realizar un seguimiento de las estadísticas personalizadas como eventos, dependencias y la vista de página.</span><span class="sxs-lookup"><span data-stu-id="a481a-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="a481a-127">Por último, el potente análisis le permite escribir consultas que formulan preguntas importantes y generan gráficos e información avanzada.</span><span class="sxs-lookup"><span data-stu-id="a481a-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="a481a-128">Para más información, consulte [Supervisión de Azure Functions](/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="a481a-128">For more information, see [Monitor Azure Functions](/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a481a-129">[Anterior](azure-functions.md)
>[Siguiente](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="a481a-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>
