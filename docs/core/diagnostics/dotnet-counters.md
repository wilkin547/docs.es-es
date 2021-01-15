---
title: 'Herramienta de diagnóstico dotnet-counters: CLI de .NET'
description: Obtenga información sobre cómo instalar y usar la herramienta dotnet-counter de la CLI para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.
ms.date: 11/17/2020
ms.openlocfilehash: 44d74cfaca7483b1506fe7ad762818e9b9ed7d63
ms.sourcegitcommit: 0273f8845eb1ea8de64086bef2271b4f22182c91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2021
ms.locfileid: "98058096"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="339b0-103">Investigación de los contadores de rendimiento (dotnet-counters)</span><span class="sxs-lookup"><span data-stu-id="339b0-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="339b0-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="339b0-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="339b0-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="339b0-105">Install</span></span>

<span data-ttu-id="339b0-106">Hay dos maneras de descargar e instalar `dotnet-counters`:</span><span class="sxs-lookup"><span data-stu-id="339b0-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="339b0-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="339b0-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="339b0-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="339b0-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="339b0-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="339b0-109">**Direct download:**</span></span>

  <span data-ttu-id="339b0-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="339b0-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="339b0-111">SO</span><span class="sxs-lookup"><span data-stu-id="339b0-111">OS</span></span>  | <span data-ttu-id="339b0-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="339b0-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="339b0-113">Windows</span><span class="sxs-lookup"><span data-stu-id="339b0-113">Windows</span></span> | <span data-ttu-id="339b0-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="339b0-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="339b0-115">macOS</span><span class="sxs-lookup"><span data-stu-id="339b0-115">macOS</span></span>   | [<span data-ttu-id="339b0-116">x64</span><span class="sxs-lookup"><span data-stu-id="339b0-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="339b0-117">Linux</span><span class="sxs-lookup"><span data-stu-id="339b0-117">Linux</span></span>   | <span data-ttu-id="339b0-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="339b0-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="339b0-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="339b0-119">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="339b0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="339b0-120">Description</span></span>

<span data-ttu-id="339b0-121">`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.</span><span class="sxs-lookup"><span data-stu-id="339b0-121">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="339b0-122">Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="339b0-122">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="339b0-123">Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="339b0-123">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="339b0-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="339b0-124">Options</span></span>

- **`--version`**

  <span data-ttu-id="339b0-125">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="339b0-125">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="339b0-126">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="339b0-126">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="339b0-127">Comandos</span><span class="sxs-lookup"><span data-stu-id="339b0-127">Commands</span></span>

| <span data-ttu-id="339b0-128">Comando</span><span class="sxs-lookup"><span data-stu-id="339b0-128">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="339b0-129">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="339b0-129">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="339b0-130">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="339b0-130">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="339b0-131">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="339b0-131">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="339b0-132">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="339b0-132">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="339b0-133">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="339b0-133">dotnet-counters collect</span></span>

<span data-ttu-id="339b0-134">Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="339b0-134">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="339b0-135">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="339b0-135">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="339b0-136">Opciones</span><span class="sxs-lookup"><span data-stu-id="339b0-136">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="339b0-137">Id. del proceso del que se van a recopilar datos de contador.</span><span class="sxs-lookup"><span data-stu-id="339b0-137">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="339b0-138">Nombre del proceso del que se van a recopilar datos de contador.</span><span class="sxs-lookup"><span data-stu-id="339b0-138">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="339b0-139">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="339b0-139">The name of the diagnostic port to create.</span></span> <span data-ttu-id="339b0-140">Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="339b0-140">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="339b0-141">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="339b0-141">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="339b0-142">Una lista de contadores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="339b0-142">A comma-separated list of counters.</span></span> <span data-ttu-id="339b0-143">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="339b0-143">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="339b0-144">Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor.</span><span class="sxs-lookup"><span data-stu-id="339b0-144">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="339b0-145">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="339b0-145">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="339b0-146">Formato que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="339b0-146">The format to be exported.</span></span> <span data-ttu-id="339b0-147">Actualmente disponibles: csv, json.</span><span class="sxs-lookup"><span data-stu-id="339b0-147">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="339b0-148">Nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="339b0-148">The name of the output file.</span></span>

- <span data-ttu-id="339b0-149">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**</span><span class="sxs-lookup"><span data-stu-id="339b0-149">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="339b0-150">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="339b0-150">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="339b0-151">`dotnet-counters` iniciará un proceso con el comando proporcionado y recopilará las métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="339b0-151">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="339b0-152">Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="339b0-152">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="339b0-153">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="339b0-153">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="339b0-154">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="339b0-154">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="339b0-155">El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="339b0-155">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="339b0-156">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="339b0-156">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="339b0-157">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="339b0-157">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="339b0-158">Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="339b0-158">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="339b0-159">Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="339b0-159">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="339b0-160">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="339b0-160">Examples</span></span>

- <span data-ttu-id="339b0-161">Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:</span><span class="sxs-lookup"><span data-stu-id="339b0-161">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="339b0-162">Inicie `dotnet mvc.dll` como un proceso secundario y comience a recopilar contadores de tiempo de ejecución y contadores de hospedaje de ASP.NET Core del inicio, y guárdelo como una salida JSON:</span><span class="sxs-lookup"><span data-stu-id="339b0-162">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="339b0-163">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="339b0-163">dotnet-counters list</span></span>

<span data-ttu-id="339b0-164">Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.</span><span class="sxs-lookup"><span data-stu-id="339b0-164">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="339b0-165">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="339b0-165">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="339b0-166">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="339b0-166">Example</span></span>

```console
> dotnet-counters list
Showing well-known counters only. Specific processes may support additional counters.

System.Runtime
    cpu-usage                                    Amount of time the process has utilized the CPU (ms)
    working-set                                  Amount of working set used by the process (MB)
    gc-heap-size                                 Total heap size reported by the GC (MB)
    gen-0-gc-count                               Number of Gen 0 GCs per interval
    gen-1-gc-count                               Number of Gen 1 GCs per interval
    gen-2-gc-count                               Number of Gen 2 GCs per interval
    time-in-gc                                   % time in GC since the last GC
    gen-0-size                                   Gen 0 Heap Size
    gen-1-size                                   Gen 1 Heap Size
    gen-2-size                                   Gen 2 Heap Size
    loh-size                                     LOH Heap Size
    alloc-rate                                   Allocation Rate
    assembly-count                               Number of Assemblies Loaded
    exception-count                              Number of Exceptions per interval
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
> <span data-ttu-id="339b0-167">Los contadores de `Microsoft.AspNetCore.Hosting` se muestran cuando hay procesos identificados que admiten estos contadores, por ejemplo, cuando una aplicación ASP.NET Core se está ejecutando en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="339b0-167">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="339b0-168">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="339b0-168">dotnet-counters monitor</span></span>

<span data-ttu-id="339b0-169">Muestra la actualización periódica de los valores de los contadores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="339b0-169">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="339b0-170">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="339b0-170">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="339b0-171">Opciones</span><span class="sxs-lookup"><span data-stu-id="339b0-171">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="339b0-172">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="339b0-172">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="339b0-173">Nombre del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="339b0-173">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="339b0-174">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="339b0-174">The name of the diagnostic port to create.</span></span> <span data-ttu-id="339b0-175">Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="339b0-175">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="339b0-176">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="339b0-176">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="339b0-177">Una lista de contadores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="339b0-177">A comma-separated list of counters.</span></span> <span data-ttu-id="339b0-178">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="339b0-178">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="339b0-179">Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor.</span><span class="sxs-lookup"><span data-stu-id="339b0-179">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="339b0-180">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="339b0-180">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="339b0-181">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**</span><span class="sxs-lookup"><span data-stu-id="339b0-181">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="339b0-182">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="339b0-182">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="339b0-183">`dotnet-counters` iniciará un proceso con el comando proporcionado y supervisará las métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="339b0-183">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="339b0-184">Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="339b0-184">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="339b0-185">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="339b0-185">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="339b0-186">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="339b0-186">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="339b0-187">El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="339b0-187">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="339b0-188">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="339b0-188">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="339b0-189">Si el proceso secundario termina antes que la herramienta, esta también se cerrará.</span><span class="sxs-lookup"><span data-stu-id="339b0-189">If the child process exits before the tool, the tool will exit as well.</span></span> <span data-ttu-id="339b0-190">Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="339b0-190">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="339b0-191">Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="339b0-191">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

### <a name="examples"></a><span data-ttu-id="339b0-192">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="339b0-192">Examples</span></span>

- <span data-ttu-id="339b0-193">Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="339b0-193">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902  --refresh-interval 3 --counters System.Runtime
  Press p to pause, r to resume, q to quit.
      Status: Running

  [System.Runtime]
      % Time in GC since last GC (%)                                 0
      Allocation Rate (B / 1 sec)                                5,376
      CPU Usage (%)                                                  0
      Exception Count (Count / 1 sec)                                0
      GC Fragmentation (%)                                          48.467
      GC Heap Size (MB)                                              0
      Gen 0 GC Count (Count / 1 sec)                                 1
      Gen 0 Size (B)                                                24
      Gen 1 GC Count (Count / 1 sec)                                 1
      Gen 1 Size (B)                                                24
      Gen 2 GC Count (Count / 1 sec)                                 1
      Gen 2 Size (B)                                           272,000
      IL Bytes Jitted (B)                                       19,449
      LOH Size (B)                                              19,640
      Monitor Lock Contention Count (Count / 1 sec)                  0
      Number of Active Timers                                        0
      Number of Assemblies Loaded                                    7
      Number of Methods Jitted                                     166
      POH (Pinned Object Heap) Size (B)                             24
      ThreadPool Completed Work Item Count (Count / 1 sec)           0
      ThreadPool Queue Length                                        0
      ThreadPool Thread Count                                        2
      Working Set (MB)                                              19
  ```

- <span data-ttu-id="339b0-194">Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="339b0-194">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="339b0-195">Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="339b0-195">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="339b0-196">Para obtener más información, consulte [Tutorial: Medición del rendimiento mediante EventCounters en .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="339b0-196">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="339b0-197">Vea todos los contadores conocidos que están disponibles en `dotnet-counters`:</span><span class="sxs-lookup"><span data-stu-id="339b0-197">View all well-known counters that are available in `dotnet-counters`:</span></span>

  ```console
  > dotnet-counters list

  Showing well-known counters for .NET (Core) version 3.1 only. Specific processes may support additional counters.
  System.Runtime              
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active

  Microsoft.AspNetCore.Hosting
      requests-per-second                Number of requests between update intervals
      total-requests                     Total number of requests
      current-requests                   Current number of requests
      failed-requests                    Failed number of requests
  ```

- <span data-ttu-id="339b0-198">Vea todos los contadores conocidos que están disponibles en `dotnet-counters` para aplicaciones de .NET 5:</span><span class="sxs-lookup"><span data-stu-id="339b0-198">View all well-known counters that are available in `dotnet-counters` for .NET 5 apps:</span></span>

  ```console
  > dotnet-counters list --runtime-version 5.0

  Showing well-known counters for .NET (Core) version 5.0 only. Specific processes may support additional counters.
  System.Runtime                     
      cpu-usage                          The percent of process' CPU usage relative to all of the system CPU resources [0-100]
      working-set                        Amount of working set used by the process (MB)
      gc-heap-size                       Total heap size reported by the GC (MB)
      gen-0-gc-count                     Number of Gen 0 GCs between update intervals
      gen-1-gc-count                     Number of Gen 1 GCs between update intervals
      gen-2-gc-count                     Number of Gen 2 GCs between update intervals
      time-in-gc                         % time in GC since the last GC
      gen-0-size                         Gen 0 Heap Size
      gen-1-size                         Gen 1 Heap Size
      gen-2-size                         Gen 2 Heap Size
      loh-size                           LOH Size
      poh-size                           POH (Pinned Object Heap) Size
      alloc-rate                         Number of bytes allocated in the managed heap between update intervals
      gc-fragmentation                   GC Heap Fragmentation
      assembly-count                     Number of Assemblies Loaded
      exception-count                    Number of Exceptions / sec
      threadpool-thread-count            Number of ThreadPool Threads
      monitor-lock-contention-count      Number of times there were contention when trying to take the monitor lock between update intervals
      threadpool-queue-length            ThreadPool Work Items Queue Length
      threadpool-completed-items-count   ThreadPool Completed Work Items Count
      active-timer-count                 Number of timers that are currently active
      il-bytes-jitted                    Total IL bytes jitted
      methods-jitted-count               Number of methods jitted

  Microsoft.AspNetCore.Hosting       
      requests-per-second   Number of requests between update intervals
      total-requests        Total number of requests
      current-requests      Current number of requests
      failed-requests       Failed number of requests

  Microsoft-AspNetCore-Server-Kestrel
      connections-per-second      Number of connections between update intervals
      total-connections           Total Connections
      tls-handshakes-per-second   Number of TLS Handshakes made between update intervals
      total-tls-handshakes        Total number of TLS handshakes made
      current-tls-handshakes      Number of currently active TLS handshakes
      failed-tls-handshakes       Total number of failed TLS handshakes
      current-connections         Number of current connections
      connection-queue-length     Length of Kestrel Connection Queue
      request-queue-length        Length total HTTP request queue

  System.Net.Http                    
      requests-started        Total Requests Started
      requests-started-rate   Number of Requests Started between update intervals
      requests-aborted        Total Requests Aborted
      requests-aborted-rate   Number of Requests Aborted between update intervals
      current-requests        Current Requests
  ```

- <span data-ttu-id="339b0-199">Inicie `my-aspnet-server.exe` y supervise el número de ensamblados cargados desde su inicio (solo para .NET 5.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="339b0-199">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="339b0-200">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="339b0-200">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="339b0-201">Inicie `my-aspnet-server.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y supervise su espacio de trabajo y el tamaño del montón de GC desde su inicio (solo para .NET 5.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="339b0-201">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="339b0-202">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="339b0-202">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[working-set,gc-heap-size] -- my-aspnet-server.exe arg1 arg2
  ```

  ```console
  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      GC Heap Size (MB)                                 39
      Working Set (MB)                                  59
  ```

## <a name="dotnet-counters-ps"></a><span data-ttu-id="339b0-203">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="339b0-203">dotnet-counters ps</span></span>

<span data-ttu-id="339b0-204">Muestra una lista de los procesos de dotnet que se pueden supervisar.</span><span class="sxs-lookup"><span data-stu-id="339b0-204">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="339b0-205">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="339b0-205">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="339b0-206">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="339b0-206">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="339b0-207">Uso del puerto de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="339b0-207">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="339b0-208">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="339b0-208">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="339b0-209">El puerto de diagnóstico es una característica nueva del entorno de ejecución que se ha agregado en .NET 5 y permite iniciar la supervisión o la recopilación de contadores desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="339b0-209">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="339b0-210">Para hacer esto con `dotnet-counters`, puede usar `dotnet-counters <collect|monitor> -- <command>`, tal como se describe en los ejemplos anteriores, o bien la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="339b0-210">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="339b0-211">El uso de `dotnet-counters <collect|monitor> -- <command>` para iniciar la aplicación como un proceso secundario es la manera más sencilla de realizar una supervisión rápida desde el inicio.</span><span class="sxs-lookup"><span data-stu-id="339b0-211">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="339b0-212">Sin embargo, si quiere obtener un control más preciso sobre la vigencia de la aplicación supervisada (por ejemplo, supervisar la aplicación solo durante los primeros 10 minutos y continuar la ejecución), o si necesita interactuar con la aplicación mediante la CLI, el uso de la opción `--diagnostic-port` le permite controlar la aplicación de destino que se supervisa y `dotnet-counters`.</span><span class="sxs-lookup"><span data-stu-id="339b0-212">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="339b0-213">El comando siguiente hace que dotnet-counters cree un socket de diagnóstico denominado `myport.sock` y que espere a una conexión.</span><span class="sxs-lookup"><span data-stu-id="339b0-213">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="339b0-214">Salida:</span><span class="sxs-lookup"><span data-stu-id="339b0-214">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="339b0-215">En una consola independiente, inicie la aplicación de destino con la variable de entorno `DOTNET_DiagnosticPorts` establecida en el valor de la salida de `dotnet-counters`.</span><span class="sxs-lookup"><span data-stu-id="339b0-215">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="339b0-216">Esto debe habilitar `dotnet-counters` para empezar a recopilar contadores en `my-dotnet-app`:</span><span class="sxs-lookup"><span data-stu-id="339b0-216">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="339b0-217">Iniciar la aplicación con `dotnet run` puede resultar problemático porque la CLI de dotnet puede generar muchos procesos secundarios que no sean la aplicación. Además, dichos procesos secundarios pueden conectarse a `dotnet-counters` antes que la aplicación, lo que causa que esta se suspenda en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="339b0-217">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="339b0-218">Se recomienda usar directamente una versión independiente de la aplicación o `dotnet exec` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="339b0-218">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
