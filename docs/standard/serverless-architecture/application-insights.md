---
title: 'Application Insights: aplicaciones sin servidor'
description: Application Insights es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnostique problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: b4884d483de07c1c2077f7280b6b77c6059572c0
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53154267"
---
# <a name="telemetry-with-application-insights"></a><span data-ttu-id="f3907-103">Datos de telemetría con Application Insights</span><span class="sxs-lookup"><span data-stu-id="f3907-103">Telemetry with Application Insights</span></span>

<span data-ttu-id="f3907-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) es una plataforma de diagnóstico sin servidor que permite a los desarrolladores detectar, evaluar las prioridades y diagnostique problemas en aplicaciones web, aplicaciones móviles, aplicaciones de escritorio y microservicios.</span><span class="sxs-lookup"><span data-stu-id="f3907-104">[Application Insights](https://docs.microsoft.com/azure/application-insights) is a serverless diagnostics platform that enables developers to detect, triage, and diagnose issues in web apps, mobile apps, desktop apps, and microservices.</span></span> <span data-ttu-id="f3907-105">Puede activar Application Insights para aplicaciones de función accionando un conmutador en el portal.</span><span class="sxs-lookup"><span data-stu-id="f3907-105">You can turn on Application Insights for function apps simply by flipping a switch in the portal.</span></span> <span data-ttu-id="f3907-106">Application Insights proporciona todas estas funcionalidades sin tener que volver a configurar un servidor o configurar su propia base de datos.</span><span class="sxs-lookup"><span data-stu-id="f3907-106">Application Insights provides all of these capabilities without you having to configure a server or set up your own database.</span></span> <span data-ttu-id="f3907-107">Todas las capacidades de Application Insights se proporcionan como un servicio que automáticamente se integra con las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="f3907-107">All of Application Insights' capabilities are provided as a service that automatically integrates with your apps.</span></span>

![Logotipo de Application Insights](./media/application-insights-logo.png)

<span data-ttu-id="f3907-109">Agregar Application Insights a las aplicaciones existentes es tan fácil como agregar una clave de instrumentación a la configuración de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="f3907-109">Adding Application Insights to existing apps is as easy as adding an instrumentation key to your application's settings.</span></span> <span data-ttu-id="f3907-110">Con Application Insights, puede:</span><span class="sxs-lookup"><span data-stu-id="f3907-110">With Application Insights you can:</span></span>

* <span data-ttu-id="f3907-111">Crear gráficos personalizados y alertas basadas en métricas como el número de invocaciones de función, el tiempo necesario para ejecutar una función y excepciones</span><span class="sxs-lookup"><span data-stu-id="f3907-111">Create custom charts and alerts based on metrics such as number of function invocations, the time it takes to run a function, and exceptions</span></span>
* <span data-ttu-id="f3907-112">Analizar errores y excepciones de servidor</span><span class="sxs-lookup"><span data-stu-id="f3907-112">Analyze failures and server exceptions</span></span>
* <span data-ttu-id="f3907-113">Profundizar en el rendimiento mediante la operación y medir el tiempo necesario para llamar a las dependencias de terceros</span><span class="sxs-lookup"><span data-stu-id="f3907-113">Drill into performance by operation and measure the time it takes to call third-party dependencies</span></span>
* <span data-ttu-id="f3907-114">Supervisar el uso de CPU, memoria y las tasas en todos los servidores que hospedan las aplicaciones de función</span><span class="sxs-lookup"><span data-stu-id="f3907-114">Monitor CPU usage, memory, and rates across all servers that host your function apps</span></span>
* <span data-ttu-id="f3907-115">Ver una secuencia en directo de métricas, incluidos el número de solicitudes y la latencia para las aplicaciones de función</span><span class="sxs-lookup"><span data-stu-id="f3907-115">View a live stream of metrics including request count and latency for your function apps</span></span>
* <span data-ttu-id="f3907-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) para buscar, consultar y crear gráficos personalizados a través de los datos de la función</span><span class="sxs-lookup"><span data-stu-id="f3907-116">Use [Analytics](https://docs.microsoft.com/azure/application-insights/app-insights-analytics) to search, query, and create custom charts over your function data</span></span>

![Explorador de métricas](./media/metrics-explorer.png)

<span data-ttu-id="f3907-118">Además de telemetría integrada, también es posible generar datos de telemetría personalizados.</span><span class="sxs-lookup"><span data-stu-id="f3907-118">In addition to built-in telemetry, it's also possible to generate custom telemetry.</span></span> <span data-ttu-id="f3907-119">El siguiente fragmento de código crea a un cliente de telemetría personalizada mediante la clave de instrumentación establecido para la aplicación de función:</span><span class="sxs-lookup"><span data-stu-id="f3907-119">The following code snippet creates a custom telemetry client using the instrumentation key set for the function app:</span></span>

```csharp
public static TelemetryClient telemetry = new TelemetryClient()
{
    InstrumentationKey = Environment.GetEnvironmentVariable("APPINSIGHTS_INSTRUMENTATIONKEY")
};
```

<span data-ttu-id="f3907-120">El código siguiente mide cuánto tarda en Insertar una fila nueva en un [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instancia:</span><span class="sxs-lookup"><span data-stu-id="f3907-120">The following code measures how long it takes to insert a new row into an [Azure Table Storage](https://docs.microsoft.com/azure/cosmos-db/table-storage-overview) instance:</span></span>

```csharp
var operation = TableOperation.Insert(entry);
var startTime = DateTime.UtcNow;
var timer = System.Diagnostics.Stopwatch.StartNew();
await table.ExecuteAsync(operation);
telemetry.TrackDependency("AzureTableStorageInsert", "Insert", startTime, timer.Elapsed, true);
```

<span data-ttu-id="f3907-121">Se muestra el gráfico de rendimiento resultante:</span><span class="sxs-lookup"><span data-stu-id="f3907-121">The resulting performance graph is shown:</span></span>

![Telemetría personalizada](./media/custom-telemetry.png)

<span data-ttu-id="f3907-123">La telemetría personalizada, se muestra el tiempo medio para insertar una fila nueva es 32.6 milisegundos.</span><span class="sxs-lookup"><span data-stu-id="f3907-123">The custom telemetry reveals the average time to insert a new row is 32.6 milliseconds.</span></span>

<span data-ttu-id="f3907-124">Application Insights proporciona una manera eficaz y fácil para registrar la telemetría detallada acerca de las aplicaciones sin servidor.</span><span class="sxs-lookup"><span data-stu-id="f3907-124">Application Insights provides a powerful, convenient way to log detailed telemetry about your serverless applications.</span></span> <span data-ttu-id="f3907-125">Tiene control total sobre el nivel de seguimiento y registro se proporciona.</span><span class="sxs-lookup"><span data-stu-id="f3907-125">You have full control over the level of tracing and logging that is provided.</span></span> <span data-ttu-id="f3907-126">Puede realizar un seguimiento de estadísticas personalizadas, como la vista de página, dependencias y eventos.</span><span class="sxs-lookup"><span data-stu-id="f3907-126">You can track custom statistics such as events, dependencies, and page view.</span></span> <span data-ttu-id="f3907-127">Por último, el análisis eficaces le permiten escribir consultas que formular preguntas importantes y generan gráficos e información avanzada.</span><span class="sxs-lookup"><span data-stu-id="f3907-127">Finally, the powerful analytics enable you to write queries that ask important questions and generate charts and advanced insights.</span></span>

<span data-ttu-id="f3907-128">Para obtener más información, consulte [supervisión de Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span><span class="sxs-lookup"><span data-stu-id="f3907-128">For more information, see [Monitor Azure Functions](https://docs.microsoft.com/azure/azure-functions/functions-monitoring).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f3907-129">[Anterior](azure-functions.md)
>[Siguiente](logic-apps.md)</span><span class="sxs-lookup"><span data-stu-id="f3907-129">[Previous](azure-functions.md)
[Next](logic-apps.md)</span></span>