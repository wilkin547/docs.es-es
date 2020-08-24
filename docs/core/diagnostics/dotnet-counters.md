---
title: 'dotnet-counters: .Net Core'
description: Obtenga información sobre cómo instalar y usar la herramienta de línea de comandos dotnet-counter.
ms.date: 02/26/2020
ms.openlocfilehash: 6a4fd92540dbc16173dfa3a10ff9dfaa1f31f7d0
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062904"
---
# <a name="dotnet-counters"></a><span data-ttu-id="5400e-103">dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5400e-103">dotnet-counters</span></span>

<span data-ttu-id="5400e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="5400e-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-counters"></a><span data-ttu-id="5400e-105">Instalación de dotnet-counters</span><span class="sxs-lookup"><span data-stu-id="5400e-105">Install dotnet-counters</span></span>

<span data-ttu-id="5400e-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="5400e-106">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-counters
```

## <a name="synopsis"></a><span data-ttu-id="5400e-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5400e-107">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="5400e-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="5400e-108">Description</span></span>

<span data-ttu-id="5400e-109">`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.</span><span class="sxs-lookup"><span data-stu-id="5400e-109">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="5400e-110">Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="5400e-110">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="5400e-111">Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="5400e-111">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="5400e-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="5400e-112">Options</span></span>

- **`--version`**

  <span data-ttu-id="5400e-113">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="5400e-113">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="5400e-114">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="5400e-114">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="5400e-115">Comandos</span><span class="sxs-lookup"><span data-stu-id="5400e-115">Commands</span></span>

| <span data-ttu-id="5400e-116">Comando</span><span class="sxs-lookup"><span data-stu-id="5400e-116">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="5400e-117">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="5400e-117">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="5400e-118">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="5400e-118">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="5400e-119">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="5400e-119">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="5400e-120">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="5400e-120">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="5400e-121">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="5400e-121">dotnet-counters collect</span></span>

<span data-ttu-id="5400e-122">Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="5400e-122">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5400e-123">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5400e-123">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list] [--format] [-o|--output]
```

### <a name="options"></a><span data-ttu-id="5400e-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="5400e-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="5400e-125">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="5400e-125">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="5400e-126">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="5400e-126">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="5400e-127">Una lista de contadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="5400e-127">A space separated list of counters.</span></span> <span data-ttu-id="5400e-128">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="5400e-128">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="5400e-129">Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores.</span><span class="sxs-lookup"><span data-stu-id="5400e-129">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="5400e-130">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="5400e-130">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="5400e-131">Formato que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="5400e-131">The format to be exported.</span></span> <span data-ttu-id="5400e-132">Actualmente disponibles: csv, json.</span><span class="sxs-lookup"><span data-stu-id="5400e-132">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="5400e-133">Nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="5400e-133">The name of the output file.</span></span>

### <a name="examples"></a><span data-ttu-id="5400e-134">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5400e-134">Examples</span></span>

- <span data-ttu-id="5400e-135">Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:</span><span class="sxs-lookup"><span data-stu-id="5400e-135">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="5400e-136">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="5400e-136">dotnet-counters list</span></span>

<span data-ttu-id="5400e-137">Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.</span><span class="sxs-lookup"><span data-stu-id="5400e-137">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5400e-138">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5400e-138">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="5400e-139">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5400e-139">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs / min
    gen-1-gc-count                               Number of Gen 1 GCs / min
    gen-2-gc-count                               Number of Gen 2 GCs / min
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions / sec
    threadpool-thread-count                      Number of ThreadPool Threads
    monitor-lock-contention-count                Monitor Lock Contention Count
    threadpool-queue-length                      ThreadPool Work Items Queue Length
    threadpool-completed-items-count             ThreadPool Completed Work Items Count
    active-timer-count                           Active Timers Count

Microsoft.AspNetCore.Hosting
    requests-per-second                  Request rate
    total-requests                       Total number of requests
    current-requests                     Current number of requests
    failed-requests                      Failed number of requests
```

> [!NOTE]
> <span data-ttu-id="5400e-140">Los contadores de `Microsoft.AspNetCore.Hosting` se muestran cuando hay procesos identificados que admiten estos contadores, por ejemplo, cuando una aplicación ASP.NET Core se está ejecutando en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="5400e-140">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="5400e-141">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="5400e-141">dotnet-counters monitor</span></span>

<span data-ttu-id="5400e-142">Muestra la actualización periódica de los valores de los contadores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="5400e-142">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5400e-143">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5400e-143">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [--refreshInterval] [counter_list]
```

### <a name="options"></a><span data-ttu-id="5400e-144">Opciones</span><span class="sxs-lookup"><span data-stu-id="5400e-144">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="5400e-145">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="5400e-145">The ID of the process to be monitored.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="5400e-146">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="5400e-146">The number of seconds to delay between updating the displayed counters</span></span>

- **`counter_list <COUNTERS>`**

  <span data-ttu-id="5400e-147">Una lista de contadores separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="5400e-147">A space separated list of counters.</span></span> <span data-ttu-id="5400e-148">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="5400e-148">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="5400e-149">Si `provider_name` se usa sin un elemento `counter_name` calificado, se mostrarán todos los contadores.</span><span class="sxs-lookup"><span data-stu-id="5400e-149">If the `provider_name` is used without a qualifying `counter_name`, then all counters are shown.</span></span> <span data-ttu-id="5400e-150">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="5400e-150">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

### <a name="examples"></a><span data-ttu-id="5400e-151">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="5400e-151">Examples</span></span>

- <span data-ttu-id="5400e-152">Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="5400e-152">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 System.Runtime

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      Working Set (MB)                            1982
      GC Heap Size (MB)                            811
      Gen 0 GC / second                             20
      Gen 1 GC / second                              4
      Gen 2 GC / second                              1
      Number of Exceptions / sec                     4
  ```

- <span data-ttu-id="5400e-153">Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="5400e-153">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    System.Runtime:
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="5400e-154">Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="5400e-154">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="5400e-155">Para obtener más información, consulte [Tutorial: Medición del rendimiento mediante EventCounters en .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="5400e-155">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```
  
## <a name="dotnet-counters-ps"></a><span data-ttu-id="5400e-156">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="5400e-156">dotnet-counters ps</span></span>

<span data-ttu-id="5400e-157">Muestra una lista de los procesos de dotnet que se pueden supervisar.</span><span class="sxs-lookup"><span data-stu-id="5400e-157">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="5400e-158">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="5400e-158">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="5400e-159">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="5400e-159">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/suwhang/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```
