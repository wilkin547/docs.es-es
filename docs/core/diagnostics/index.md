---
title: 'Información general de las herramientas de diagnóstico: .NET Core'
description: Información general de las herramientas y técnicas disponibles para diagnosticar las aplicaciones de .NET Core.
ms.date: 07/16/2020
ms.topic: overview
ms.openlocfilehash: 9836ea11e7f17d6ed6e04bcba8bc0ed851bb368f
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105289"
---
# <a name="what-diagnostic-tools-are-available-in-net-core"></a><span data-ttu-id="0cfb5-103">¿Qué herramientas de diagnóstico están disponibles en .NET Core?</span><span class="sxs-lookup"><span data-stu-id="0cfb5-103">What diagnostic tools are available in .NET Core?</span></span>

<span data-ttu-id="0cfb5-104">El comportamiento del software no siempre es el esperado, pero .NET Core tiene herramientas y API que lo ayudarán a diagnosticar estos problemas de manera rápida y eficaz.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-104">Software doesn't always behave as you would expect, but .NET Core has tools and APIs that will help you diagnose these issues quickly and effectively.</span></span>

<span data-ttu-id="0cfb5-105">Este artículo lo ayuda a encontrar las distintas herramientas que necesita.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-105">This article helps you find the various tools you need.</span></span>

## <a name="managed-debuggers"></a><span data-ttu-id="0cfb5-106">Depuradores administrados</span><span class="sxs-lookup"><span data-stu-id="0cfb5-106">Managed debuggers</span></span>

<span data-ttu-id="0cfb5-107">Los [depuradores administrados](managed-debuggers.md) le permiten interactuar con el programa.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-107">[Managed debuggers](managed-debuggers.md) allow you to interact with your program.</span></span> <span data-ttu-id="0cfb5-108">Pausar, ejecutar de manera incremental, examinar y reanudar le proporcionan información sobre el comportamiento del código.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-108">Pausing, incrementally executing, examining,  and resuming gives you insight into the behavior of your code.</span></span> <span data-ttu-id="0cfb5-109">Un depurador es la primera opción para diagnosticar problemas funcionales que se pueden reproducir de manera fácil.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-109">A debugger is the first choice for diagnosing functional problems that can be easily reproduced.</span></span>

## <a name="logging-and-tracing"></a><span data-ttu-id="0cfb5-110">Registro y seguimiento</span><span class="sxs-lookup"><span data-stu-id="0cfb5-110">Logging and tracing</span></span>

<span data-ttu-id="0cfb5-111">El [registro y seguimiento](logging-tracing.md) son técnicas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-111">[Logging and tracing](logging-tracing.md) are related techniques.</span></span> <span data-ttu-id="0cfb5-112">Hacen referencia a la instrumentación del código para crear archivos de registro.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-112">They refer to instrumenting code to create log files.</span></span> <span data-ttu-id="0cfb5-113">Los archivos registran los detalles de lo que hace un programa.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-113">The files record the details of what a program does.</span></span> <span data-ttu-id="0cfb5-114">Estos detalles se pueden usar para diagnosticar los problemas más complejos.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-114">These details can be used to diagnose the most complex problems.</span></span> <span data-ttu-id="0cfb5-115">Cuando se combinan con marcas de tiempo, estas técnicas también son valiosas para investigaciones de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-115">When combined with time stamps, these techniques are also valuable in performance investigations.</span></span>

## <a name="metrics"></a><span data-ttu-id="0cfb5-116">Métricas</span><span class="sxs-lookup"><span data-stu-id="0cfb5-116">Metrics</span></span>

<span data-ttu-id="0cfb5-117">Los elementos [EventCounter](event-counters.md) permiten escribir métricas para identificar y supervisar los problemas de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-117">[EventCounters](event-counters.md) allows you to write metrics to identify and monitor performance issues.</span></span> <span data-ttu-id="0cfb5-118">Las métricas incurren en una carga de rendimiento menor en comparación con el seguimiento, lo que las hace más convenientes para una supervisión de rendimiento permanente.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-118">Metrics incur lower performance overhead compared to tracing, making it more suitable for an always-on performance monitoring.</span></span> <span data-ttu-id="0cfb5-119">El entorno de ejecución y las bibliotecas de .NET publican varios [elementos EventCounter conocidos](available-counters.md) que también puede supervisar.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-119">The .NET runtime and libraries publish several [well-known EventCounters](available-counters.md) that you can monitor as well.</span></span>

## <a name="unit-testing"></a><span data-ttu-id="0cfb5-120">Pruebas unitarias</span><span class="sxs-lookup"><span data-stu-id="0cfb5-120">Unit testing</span></span>

<span data-ttu-id="0cfb5-121">Las [pruebas unitarias](../testing/index.md) son un componente clave de la integración continua y la implementación de software de alta calidad.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-121">[Unit testing](../testing/index.md) is a key component of continuous integration and deployment of high-quality software.</span></span> <span data-ttu-id="0cfb5-122">Las pruebas unitarias están diseñadas para brindarle una advertencia temprana cuando se daña algo.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-122">Unit tests are designed to give you an early warning when you break something.</span></span>

## <a name="dumps"></a><span data-ttu-id="0cfb5-123">Volcados</span><span class="sxs-lookup"><span data-stu-id="0cfb5-123">Dumps</span></span>

<span data-ttu-id="0cfb5-124">Un [volcado](./dumps.md) es un archivo que contiene una instantánea del proceso en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-124">A [dump](./dumps.md) is a file that contains a snapshot of the process at the time of creation.</span></span> <span data-ttu-id="0cfb5-125">Pueden ser útiles para examinar el estado de la aplicación con fines de depuración.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-125">These can be useful for examining the state of your application for debugging purposes.</span></span>

## <a name="symbols"></a><span data-ttu-id="0cfb5-126">Símbolos</span><span class="sxs-lookup"><span data-stu-id="0cfb5-126">Symbols</span></span>

<span data-ttu-id="0cfb5-127">Los [símbolos](./symbols.md) son una asignación entre el código de origen y el binario que produce el compilador.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-127">[Symbols](./symbols.md) are a mapping between the source code and the binary produced by the compiler.</span></span> <span data-ttu-id="0cfb5-128">Los depuradores de .NET suelen usarlos para resolver números de línea de origen, nombres de variables locales y otros tipos de información de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-128">These are commonly used by .NET debuggers to resolve source line numbers, local variable names, and other types of diagnostic information.</span></span>

## <a name="collect-diagnostics-in-containers"></a><span data-ttu-id="0cfb5-129">Recopilación de diagnósticos en contenedores</span><span class="sxs-lookup"><span data-stu-id="0cfb5-129">Collect diagnostics in containers</span></span>

<span data-ttu-id="0cfb5-130">Las herramientas de diagnóstico que se usan en los entornos de Linux que no están en contenedores también se pueden utilizar para [recopilar diagnósticos en contenedores](diagnostics-in-containers.md).</span><span class="sxs-lookup"><span data-stu-id="0cfb5-130">The same diagnostics tools that are used in non-containerized Linux environments can also be used to [collect diagnostics in containers](diagnostics-in-containers.md).</span></span> <span data-ttu-id="0cfb5-131">Solo es necesario realizar algunos cambios en la utilización para asegurarse de que las herramientas funcionan en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-131">There are just a few usage changes needed to make sure the tools work in a Docker container.</span></span>

## <a name="net-core-diagnostic-global-tools"></a><span data-ttu-id="0cfb5-132">Herramientas globales de diagnóstico de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0cfb5-132">.NET Core diagnostic global tools</span></span>

### <a name="dotnet-counters"></a><span data-ttu-id="0cfb5-133">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="0cfb5-133">dotnet-counters</span></span>

<span data-ttu-id="0cfb5-134">[dotnet-counters](dotnet-counters.md) es una herramienta diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-134">[dotnet-counters](dotnet-counters.md) is a performance monitoring tool for first-level health monitoring and performance investigation.</span></span> <span data-ttu-id="0cfb5-135">Permite observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-135">It observes performance counter values published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="0cfb5-136">Por ejemplo, puede supervisar rápidamente elementos como el uso de la CPU o la tasa de excepciones que se generan en su aplicación .NET Core.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-136">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application.</span></span>

### <a name="dotnet-dump"></a><span data-ttu-id="0cfb5-137">dotnet-dump</span><span class="sxs-lookup"><span data-stu-id="0cfb5-137">dotnet-dump</span></span>

<span data-ttu-id="0cfb5-138">La herramienta [dotnet-dump](dotnet-dump.md) permite recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-138">The [dotnet-dump](dotnet-dump.md) tool is a way to collect and analyze Windows and Linux core dumps without a native debugger.</span></span>

### <a name="dotnet-gcdump"></a><span data-ttu-id="0cfb5-139">dotnet-gcdump</span><span class="sxs-lookup"><span data-stu-id="0cfb5-139">dotnet-gcdump</span></span>

<span data-ttu-id="0cfb5-140">La herramienta [dotnet-gcdump](dotnet-gcdump.md) permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-140">The [dotnet-gcdump](dotnet-gcdump.md) tool is a way to collect GC (Garbage Collector) dumps of live .NET processes.</span></span>

### <a name="dotnet-trace"></a><span data-ttu-id="0cfb5-141">dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="0cfb5-141">dotnet-trace</span></span>

<span data-ttu-id="0cfb5-142">.NET Core incluye lo que se denomina `EventPipe`, a través del cual se exponen los datos de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-142">.NET Core includes what is called the `EventPipe` through which diagnostics data is exposed.</span></span> <span data-ttu-id="0cfb5-143">La herramienta [dotnet-trace](dotnet-trace.md) permite consumir datos interesantes sobre la generación de perfiles a partir de su aplicación, lo cual puede resultar útil para analizar la causa principal de que una aplicación se ejecute con lentitud.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-143">The [dotnet-trace](dotnet-trace.md) tool allows you to consume interesting profiling data from your app that can help in scenarios where you need to root cause apps running slow.</span></span>

### <a name="dotnet-symbol"></a><span data-ttu-id="0cfb5-144">dotnet-symbol</span><span class="sxs-lookup"><span data-stu-id="0cfb5-144">dotnet-symbol</span></span>

<span data-ttu-id="0cfb5-145">[dotnet-symbol](dotnet-symbol.md) descarga archivos (símbolos, DAC/DBI, archivos de host, etc.) necesarios para abrir un volcado de núcleo o minivolcado.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-145">[dotnet-symbol](dotnet-symbol.md) downloads files (symbols, DAC/DBI, host files, etc.) needed to open a core dump or minidump.</span></span> <span data-ttu-id="0cfb5-146">Use esta herramienta si necesita símbolos y módulos para depurar un archivo de volcado capturado en otro equipo.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-146">Use this tool if you need symbols and modules to debug a dump file captured on a different machine.</span></span>

### <a name="dotnet-sos"></a><span data-ttu-id="0cfb5-147">dotnet-sos</span><span class="sxs-lookup"><span data-stu-id="0cfb5-147">dotnet-sos</span></span>

<span data-ttu-id="0cfb5-148">[dotnet-sos](dotnet-sos.md) instala la [extensión de depuración de SOS](sos-debugging-extension.md) en Linux y macOS (también en Windows si usa [Windbg/cdb](/windows-hardware/drivers/debugger/debugger-download-tools)).</span><span class="sxs-lookup"><span data-stu-id="0cfb5-148">[dotnet-sos](dotnet-sos.md) installs the [SOS debugging extension](sos-debugging-extension.md) on Linux and macOS (and on Windows if you're using [Windbg/cdb](/windows-hardware/drivers/debugger/debugger-download-tools)).</span></span>

### <a name="perfcollect"></a><span data-ttu-id="0cfb5-149">PerfCollect</span><span class="sxs-lookup"><span data-stu-id="0cfb5-149">PerfCollect</span></span>

<span data-ttu-id="0cfb5-150">[PerfCollect](trace-perfcollect-lttng.md) es un script de bash que se puede usar para recopilar seguimientos con `perf` y `LTTng` para un análisis de rendimiento más detallado de las aplicaciones .NET que se ejecutan en distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-150">[PerfCollect](trace-perfcollect-lttng.md) is a bash script you can use to collect traces with `perf` and `LTTng` for a more in-depth performance analysis of .NET apps running on Linux distributions.</span></span>

## <a name="net-core-diagnostics-tutorials"></a><span data-ttu-id="0cfb5-151">Tutoriales de diagnóstico de .NET Core</span><span class="sxs-lookup"><span data-stu-id="0cfb5-151">.NET Core diagnostics tutorials</span></span>

### <a name="debug-a-memory-leak"></a><span data-ttu-id="0cfb5-152">Depuración de una fuga de memoria</span><span class="sxs-lookup"><span data-stu-id="0cfb5-152">Debug a memory leak</span></span>

<span data-ttu-id="0cfb5-153">[Tutorial: Depuración de una fuga de memoria](debug-memory-leak.md) le guía a través de la búsqueda de una fuga de memoria.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-153">[Tutorial: Debug a memory leak](debug-memory-leak.md) walks through finding a memory leak.</span></span> <span data-ttu-id="0cfb5-154">La herramienta [dotnet-counters](dotnet-counters.md) se usa para confirmar la fuga, y la herramienta [dotnet-dump](dotnet-dump.md), para diagnosticarla.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-154">The [dotnet-counters](dotnet-counters.md) tool is used to confirm the leak and the [dotnet-dump](dotnet-dump.md) tool is used to diagnose the leak.</span></span>

### <a name="debug-high-cpu-usage"></a><span data-ttu-id="0cfb5-155">Depuración del uso elevado de CPU</span><span class="sxs-lookup"><span data-stu-id="0cfb5-155">Debug high CPU usage</span></span>

<span data-ttu-id="0cfb5-156">[Tutorial: Depuración del uso elevado de CPU](debug-highcpu.md) le guía a través de la investigación del uso elevado de CPU.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-156">[Tutorial: Debug high CPU usage](debug-highcpu.md) walks you through investigating high CPU usage.</span></span> <span data-ttu-id="0cfb5-157">Utiliza la herramienta [dotnet-counters](dotnet-counters.md) para confirmar ese uso elevado.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-157">It uses the [dotnet-counters](dotnet-counters.md) tool to confirm the high CPU usage.</span></span> <span data-ttu-id="0cfb5-158">A continuación, se explica el uso del [seguimiento de la utilidad de análisis del rendimiento (`dotnet-trace`)](dotnet-trace.md) o de Linux `perf` para recopilar y ver el perfil de uso de la CPU.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-158">It then walks you through using [Trace for performance analysis utility (`dotnet-trace`)](dotnet-trace.md) or Linux `perf` to collect and view CPU usage profile.</span></span>

### <a name="debug-deadlock"></a><span data-ttu-id="0cfb5-159">Depuración de interbloqueo</span><span class="sxs-lookup"><span data-stu-id="0cfb5-159">Debug deadlock</span></span>

<span data-ttu-id="0cfb5-160">[Tutorial: Depuración de interbloqueo](debug-deadlock.md) muestra cómo usar la herramienta [dotnet-dump](dotnet-dump.md) para investigar los subprocesos y bloqueos.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-160">[Tutorial: Debug deadlock](debug-deadlock.md) shows you how to use the [dotnet-dump](dotnet-dump.md) tool to investigate threads and locks.</span></span>

### <a name="debug-a-stackoverflow"></a><span data-ttu-id="0cfb5-161">Depuración de StackOverflow</span><span class="sxs-lookup"><span data-stu-id="0cfb5-161">Debug a StackOverflow</span></span>

<span data-ttu-id="0cfb5-162">[Tutorial: Depuración de StackOverflow](debug-stackoverflow.md) muestra cómo depurar un elemento <xref:System.StackOverflowException> en Linux.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-162">[Tutorial: Debug a StackOverflow](debug-stackoverflow.md) demonstrates how to debug a <xref:System.StackOverflowException> on Linux.</span></span>

### <a name="debug-linux-dumps"></a><span data-ttu-id="0cfb5-163">Depuración de volcados de Linux</span><span class="sxs-lookup"><span data-stu-id="0cfb5-163">Debug Linux dumps</span></span>

<span data-ttu-id="0cfb5-164">[Depuración de volcados de Linux](debug-linux-dumps.md) explica cómo recopilar y analizar volcados en Linux.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-164">[Debug Linux dumps](debug-linux-dumps.md) explains how to collect and analyze dumps on Linux.</span></span>

### <a name="measure-performance-using-eventcounters"></a><span data-ttu-id="0cfb5-165">Medición del rendimiento mediante EventCounters</span><span class="sxs-lookup"><span data-stu-id="0cfb5-165">Measure performance using EventCounters</span></span>

<span data-ttu-id="0cfb5-166">[Tutorial: Medición del rendimiento mediante EventCounters en .NET](event-counter-perf.md) muestra cómo usar la API <xref:System.Diagnostics.Tracing.EventCounter> para medir el rendimiento de la aplicación .NET.</span><span class="sxs-lookup"><span data-stu-id="0cfb5-166">[Tutorial: Measure performance using EventCounters in .NET](event-counter-perf.md) shows you how to use the <xref:System.Diagnostics.Tracing.EventCounter> API to measure performance in your .NET app.</span></span>
