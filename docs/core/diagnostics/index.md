---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: c43e661ad8c9f665151e0240bf6b54e61b9acfef
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031922"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="0f344-103">¿Qué herramientas de diagnóstico están disponibles en .NET Core?</span><span class="sxs-lookup"><span data-stu-id="0f344-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="0f344-104">El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="0f344-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="0f344-105">Este artículo lo ayuda a encontrar las distintas herramientas que necesita.</span><span class="sxs-lookup"><span data-stu-id="0f344-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="0f344-106">Depuradores administrados</span><span class="sxs-lookup"><span data-stu-id="0f344-106">Managed debuggers</span></span>

<span data-ttu-id="0f344-107">Los [depuradores administrados](managed-debuggers.md) le permiten interactuar con el programa.</span><span class="sxs-lookup"><span data-stu-id="0f344-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="0f344-108">Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="0f344-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="0f344-109">Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.</span><span class="sxs-lookup"><span data-stu-id="0f344-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="0f344-110">Registro y seguimiento</span><span class="sxs-lookup"><span data-stu-id="0f344-110">Logging and tracing</span></span>

<span data-ttu-id="0f344-111">El [registro y seguimiento](logging-tracing.md) son técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0f344-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="0f344-112">Hacen referencia a la instrumentación del código para crear archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="0f344-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="0f344-113">Los archivos registran los detalles de lo que hace un programa.</span><span class="sxs-lookup"><span data-stu-id="0f344-113">The files record the details of what a program does.</span></span> <span data-ttu-id="0f344-114">Estos detalles se pueden usar para diagnosticar los problemas más complejos.</span><span class="sxs-lookup"><span data-stu-id="0f344-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="0f344-115">Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0f344-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="0f344-116">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="0f344-116">Unit testing</span></span>

<span data-ttu-id="0f344-117">Las [pruebas unitarias](../testing/index.md) son un componente clave de la integración continua y la implementación de software de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="0f344-117">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="0f344-118">Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.</span><span class="sxs-lookup"><span data-stu-id="0f344-118">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="dumps"></a><span data-ttu-id="0f344-119">Volcados</span><span class="sxs-lookup"><span data-stu-id="0f344-119">Dumps</span></span>

<span data-ttu-id="0f344-120">Un [volcado](./dumps.md) es un archivo que contiene una instantánea del proceso en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="0f344-120">A [dump](./dumps.md) is a file that contains a snapshot of the process at the time of creation.</span></span> <span data-ttu-id="0f344-121">Pueden ser útiles para examinar el estado de la aplicación con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="0f344-121">These can be useful for examining the state of your application for debugging purposes.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="0f344-122">Recopilación de diagnósticos en contenedores</span><span class="sxs-lookup"><span data-stu-id="0f344-122">Collect diagnostics in containers</span></span>

<span data-ttu-id="0f344-123">Las herramientas de diagnóstico que se usan en los entornos de Linux que no están en contenedores también se pueden utilizar para [recopilar diagnósticos en contenedores](diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="0f344-123">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="0f344-124">Solo es necesario realizar algunos cambios en la utilización para asegurarse de que las herramientas funcionan en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="0f344-124">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="debug-linux-dumps"></a><span data-ttu-id="0f344-125">Depuración de volcados de Linux</span><span class="sxs-lookup"><span data-stu-id="0f344-125">Debug Linux dumps</span></span>

<span data-ttu-id="0f344-126">[Depuración de volcados de Linux](debug-linux-dumps.md) explica cómo recopilar y analizar volcados en Linux.</span><span class="sxs-lookup"><span data-stu-id="0f344-126">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="0f344-127">Herramientas globales de diagnóstico de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0f344-127">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="0f344-128">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="0f344-128">dotnet-counters</span></span>

<span data-ttu-id="0f344-129">[dotnet-counters](dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel.</span><span class="sxs-lookup"><span data-stu-id="0f344-129">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="0f344-130">Permite observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="0f344-130">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="0f344-131">Por ejemplo, puede supervisar rápidamente elementos como el uso de la CPU o la tasa de excepciones que se generan en su aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0f344-131">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="0f344-132">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="0f344-132">dotnet-dump</span></span>

<span data-ttu-id="0f344-133">La herramienta [dotnet-dump](dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="0f344-133">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="0f344-134">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="0f344-134">dotnet-gcdump</span></span>

<span data-ttu-id="0f344-135">La herramienta [dotnet-gcdump](dotnet-gcdump.md) permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos.</span><span class="sxs-lookup"><span data-stu-id="0f344-135">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="0f344-136">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="0f344-136">dotnet-trace</span></span>

<span data-ttu-id="0f344-137">.NET Core incluye lo que se denomina `EventPipe`, a través del cual se exponen los datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="0f344-137">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="0f344-138">La herramienta [dotnet-trace](dotnet-trace.md) permite consumir datos interesantes sobre la generación de perfiles a partir de su aplicación, lo cual puede resultar útil para analizar la causa principal de que una aplicación se ejecute con lentitud.</span><span class="sxs-lookup"><span data-stu-id="0f344-138">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="0f344-139">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="0f344-139">dotnet-symbol</span></span>

<span data-ttu-id="0f344-140">[dotnet-symbol](dotnet-symbol.md) descarga archivos (símbolos, DAC/DBI, archivos de host, etc.) necesarios para abrir un volcado de núcleo o minivolcado.</span><span class="sxs-lookup"><span data-stu-id="0f344-140">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="0f344-141">Use esta herramienta si necesita símbolos y módulos para depurar un archivo de volcado capturado en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="0f344-141">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="0f344-142">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="0f344-142">dotnet-sos</span></span>

<span data-ttu-id="0f344-143">[dotnet-SOS](dotnet-sos.md) se usa para instalar la [extensión de depuración de SOS](../../framework/tools/sos-dll-sos-debugging-extension.md) en Linux o MacOS (o en Windows si se usan herramientas de depuración anteriores).</span><span class="sxs-lookup"><span data-stu-id="0f344-143">[dotnet-sos](dotnet-sos.md) is used to install the [SOS debugging extension](../../framework/tools/sos-dll-sos-debugging-extension.md) on Linux or MacOS (or on Windows if using older debugging tools).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="0f344-144">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="0f344-144">PerfCollect</span></span>

<span data-ttu-id="0f344-145">[PerfCollect](trace-perfcollect-lttng.md) es un script de bash que se puede usar para recopilar seguimientos con `perf` y `LTTng` para un análisis de rendimiento más detallado de las aplicaciones .NET que se ejecutan en distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="0f344-145">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="0f344-146">Tutoriales de diagnóstico de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0f344-146">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="0f344-147">Depuración de una fuga de memoria</span><span class="sxs-lookup"><span data-stu-id="0f344-147">Debug a memory leak</span></span>

<span data-ttu-id="0f344-148">[Tutorial: Depuración de una fuga de memoria](debug-memory-leak.md) le guía a través de la búsqueda de una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="0f344-148">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="0f344-149">La herramienta [dotnet-counters](dotnet-counters.md) se usa para confirmar la fuga, y la herramienta [dotnet-dump](dotnet-dump.md), para diagnosticarla.</span><span class="sxs-lookup"><span data-stu-id="0f344-149">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="0f344-150">Depuración del uso elevado de CPU</span><span class="sxs-lookup"><span data-stu-id="0f344-150">Debug high CPU usage</span></span>

<span data-ttu-id="0f344-151">[Tutorial: Depuración del uso elevado de CPU](debug-highcpu.md) le guía a través de la investigación del uso elevado de CPU.</span><span class="sxs-lookup"><span data-stu-id="0f344-151">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="0f344-152">Utiliza la herramienta [dotnet-counters](dotnet-counters.md) para confirmar ese uso elevado.</span><span class="sxs-lookup"><span data-stu-id="0f344-152">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="0f344-153">A continuación, se explica el uso del [seguimiento de la utilidad de análisis del rendimiento (`dotnet-trace`)](dotnet-trace.md) o de Linux `perf` para recopilar y ver el perfil de uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0f344-153">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="0f344-154">Depuración de interbloqueo</span><span class="sxs-lookup"><span data-stu-id="0f344-154">Debug deadlock</span></span>

<span data-ttu-id="0f344-155">[Tutorial: Depuración de interbloqueo](debug-deadlock.md) muestra cómo usar la herramienta [dotnet-dump](dotnet-dump.md) para investigar los subprocesos y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="0f344-155">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="0f344-156">Medición del rendimiento mediante EventCounters</span><span class="sxs-lookup"><span data-stu-id="0f344-156">Measure performance using EventCounters</span></span>

<span data-ttu-id="0f344-157">[Tutorial: Medición del rendimiento mediante EventCounters en .NET](event-counter-perf.md) muestra cómo usar la API <xref:System.Diagnostics.Tracing.EventCounter> para medir el rendimiento de la aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="0f344-157">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
