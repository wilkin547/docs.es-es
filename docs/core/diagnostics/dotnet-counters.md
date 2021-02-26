---
title: 'Herramienta de diagnóstico dotnet-counters: CLI de .NET'
description: Obtenga información sobre cómo instalar y usar la herramienta dotnet-counter de la CLI para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.
ms.date: 11/17/2020
ms.openlocfilehash: 1c802e33602c2d8f18600b9771a1f68e722d8fdf
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/17/2021
ms.locfileid: "100583305"
---
# <a name="investigate-performance-counters-dotnet-counters"></a><span data-ttu-id="c0990-103">Investigación de los contadores de rendimiento (dotnet-counters)</span><span class="sxs-lookup"><span data-stu-id="c0990-103">Investigate performance counters (dotnet-counters)</span></span>

<span data-ttu-id="c0990-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c0990-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="c0990-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="c0990-105">Install</span></span>

<span data-ttu-id="c0990-106">Hay dos maneras de descargar e instalar `dotnet-counters`:</span><span class="sxs-lookup"><span data-stu-id="c0990-106">There are two ways to download and install `dotnet-counters`:</span></span>

- <span data-ttu-id="c0990-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="c0990-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="c0990-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-counters) de `dotnet-counters`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="c0990-108">To install the latest release version of the `dotnet-counters` [NuGet package](https://www.nuget.org/packages/dotnet-counters), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-counters
  ```

- <span data-ttu-id="c0990-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="c0990-109">**Direct download:**</span></span>

  <span data-ttu-id="c0990-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="c0990-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="c0990-111">SO</span><span class="sxs-lookup"><span data-stu-id="c0990-111">OS</span></span>  | <span data-ttu-id="c0990-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="c0990-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="c0990-113">Windows</span><span class="sxs-lookup"><span data-stu-id="c0990-113">Windows</span></span> | <span data-ttu-id="c0990-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="c0990-114">[x86](https://aka.ms/dotnet-counters/win-x86) \| [x64](https://aka.ms/dotnet-counters/win-x64) \| [arm](https://aka.ms/dotnet-counters/win-arm) \| [arm-x64](https://aka.ms/dotnet-counters/win-arm64)</span></span> |
  | <span data-ttu-id="c0990-115">macOS</span><span class="sxs-lookup"><span data-stu-id="c0990-115">macOS</span></span>   | [<span data-ttu-id="c0990-116">x64</span><span class="sxs-lookup"><span data-stu-id="c0990-116">x64</span></span>](https://aka.ms/dotnet-counters/osx-x64) |
  | <span data-ttu-id="c0990-117">Linux</span><span class="sxs-lookup"><span data-stu-id="c0990-117">Linux</span></span>   | <span data-ttu-id="c0990-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="c0990-118">[x64](https://aka.ms/dotnet-counters/linux-x64) \| [arm](https://aka.ms/dotnet-counters/linux-arm) \| [arm64](https://aka.ms/dotnet-counters/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-counters/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-counters/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="c0990-119">Para usar `dotnet-counters` en una aplicación x86, necesita la versión x86 correspondiente de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="c0990-119">To use `dotnet-counters` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c0990-120">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0990-120">Synopsis</span></span>

```console
dotnet-counters [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="c0990-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0990-121">Description</span></span>

<span data-ttu-id="c0990-122">`dotnet-counters` es una herramienta de supervisión de rendimiento diseñada para la investigación del rendimiento y la supervisión del estado de primer nivel ad hoc.</span><span class="sxs-lookup"><span data-stu-id="c0990-122">`dotnet-counters` is a performance monitoring tool for ad-hoc health monitoring and first-level performance investigation.</span></span> <span data-ttu-id="c0990-123">Puede observar los valores del contador de rendimiento que se publican a través de la API <xref:System.Diagnostics.Tracing.EventCounter>.</span><span class="sxs-lookup"><span data-stu-id="c0990-123">It can observe performance counter values that are published via the <xref:System.Diagnostics.Tracing.EventCounter> API.</span></span> <span data-ttu-id="c0990-124">Por ejemplo, se pueden supervisar rápidamente cosas como el uso de la CPU o la velocidad de las excepciones que se producen en la aplicación .NET Core para ver si hay algo sospechoso antes de profundizar en una investigación de rendimiento más seria mediante `PerfView` o `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="c0990-124">For example, you can quickly monitor things like the CPU usage or the rate of exceptions being thrown in your .NET Core application to see if there's anything suspicious before diving into more serious performance investigation using `PerfView` or `dotnet-trace`.</span></span>

## <a name="options"></a><span data-ttu-id="c0990-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0990-125">Options</span></span>

- **`--version`**

  <span data-ttu-id="c0990-126">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="c0990-126">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="c0990-127">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0990-127">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="c0990-128">Comandos</span><span class="sxs-lookup"><span data-stu-id="c0990-128">Commands</span></span>

| <span data-ttu-id="c0990-129">Comando</span><span class="sxs-lookup"><span data-stu-id="c0990-129">Command</span></span>                                             |
|-----------------------------------------------------|
| [<span data-ttu-id="c0990-130">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="c0990-130">dotnet-counters collect</span></span>](#dotnet-counters-collect) |
| [<span data-ttu-id="c0990-131">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="c0990-131">dotnet-counters list</span></span>](#dotnet-counters-list)       |
| [<span data-ttu-id="c0990-132">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="c0990-132">dotnet-counters monitor</span></span>](#dotnet-counters-monitor) |
| [<span data-ttu-id="c0990-133">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="c0990-133">dotnet-counters ps</span></span>](#dotnet-counters-ps)           |

## <a name="dotnet-counters-collect"></a><span data-ttu-id="c0990-134">dotnet-counters collect</span><span class="sxs-lookup"><span data-stu-id="c0990-134">dotnet-counters collect</span></span>

<span data-ttu-id="c0990-135">Recopila periódicamente los valores de contador seleccionados y los exporta a un formato de archivo especificado para su posterior procesamiento.</span><span class="sxs-lookup"><span data-stu-id="c0990-135">Periodically collect selected counter values and export them into a specified file format for post-processing.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c0990-136">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0990-136">Synopsis</span></span>

```console
dotnet-counters collect [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters <COUNTERS>] [--format] [-o|--output] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="c0990-137">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0990-137">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="c0990-138">Id. del proceso del que se van a recopilar datos de contador.</span><span class="sxs-lookup"><span data-stu-id="c0990-138">The ID of the process to be collect counter data from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="c0990-139">Nombre del proceso del que se van a recopilar datos de contador.</span><span class="sxs-lookup"><span data-stu-id="c0990-139">The name of the process to be collect counter data from.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="c0990-140">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c0990-140">The name of the diagnostic port to create.</span></span> <span data-ttu-id="c0990-141">Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0990-141">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="c0990-142">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="c0990-142">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="c0990-143">Una lista de contadores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="c0990-143">A comma-separated list of counters.</span></span> <span data-ttu-id="c0990-144">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="c0990-144">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="c0990-145">Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c0990-145">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="c0990-146">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="c0990-146">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

- **`--format <csv|json>`**

  <span data-ttu-id="c0990-147">Formato que se va a exportar.</span><span class="sxs-lookup"><span data-stu-id="c0990-147">The format to be exported.</span></span> <span data-ttu-id="c0990-148">Actualmente disponibles: csv, json.</span><span class="sxs-lookup"><span data-stu-id="c0990-148">Currently available: csv, json.</span></span>

- **`-o|--output <output>`**

  <span data-ttu-id="c0990-149">Nombre del archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="c0990-149">The name of the output file.</span></span>

- <span data-ttu-id="c0990-150">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**</span><span class="sxs-lookup"><span data-stu-id="c0990-150">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="c0990-151">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="c0990-151">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="c0990-152">`dotnet-counters` iniciará un proceso con el comando proporcionado y recopilará las métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="c0990-152">`dotnet-counters` will launch a process with the provided command and collect the requested metrics.</span></span> <span data-ttu-id="c0990-153">Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="c0990-153">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0990-154">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="c0990-154">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="c0990-155">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="c0990-155">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0990-156">El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="c0990-156">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="c0990-157">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="c0990-157">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="c0990-158">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="c0990-158">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span> <span data-ttu-id="c0990-159">Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="c0990-159">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="c0990-160">Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="c0990-160">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="c0990-161">En Linux y macOS, este comando espera que la aplicación de destino y `dotnet-counters` compartan la misma variable de entorno `TMPDIR`.</span><span class="sxs-lookup"><span data-stu-id="c0990-161">On Linux and macOS, this command expects the target application and `dotnet-counters` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="c0990-162">De lo contrario, se agotará el tiempo de espera del comando.</span><span class="sxs-lookup"><span data-stu-id="c0990-162">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="c0990-163">Para recopilar métricas mediante `dotnet-counters`, debe ejecutarse como el mismo usuario que el que ejecuta el proceso de destino, o bien como usuario raíz.</span><span class="sxs-lookup"><span data-stu-id="c0990-163">To collect metrics using `dotnet-counters`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="c0990-164">De lo contrario, la herramienta no podrá establecer una conexión con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c0990-164">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

### <a name="examples"></a><span data-ttu-id="c0990-165">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c0990-165">Examples</span></span>

- <span data-ttu-id="c0990-166">Recopilación de todos los contadores en un intervalo de actualización de tres segundos y generación de un archivo CSV como salida:</span><span class="sxs-lookup"><span data-stu-id="c0990-166">Collect all counters at a refresh interval of 3 seconds and generate a csv as output:</span></span>

  ```console
  > dotnet-counters collect --process-id 1902 --refresh-interval 3 --format csv

  counter_list is unspecified. Monitoring all counters by default.
  Starting a counter session. Press Q to quit.
  ```

- <span data-ttu-id="c0990-167">Inicie `dotnet mvc.dll` como un proceso secundario y comience a recopilar contadores de tiempo de ejecución y contadores de hospedaje de ASP.NET Core del inicio, y guárdelo como una salida JSON:</span><span class="sxs-lookup"><span data-stu-id="c0990-167">Start `dotnet mvc.dll` as a child process and start collecting runtime counters and ASP.NET Core Hosting counters from startup and save it as a JSON output:</span></span>

  ```console
  > dotnet-counters collect --format json --counters System.Runtime,Microsoft.AspNetCore.Hosting -- dotnet mvc.dll
  Starting a counter session. Press Q to quit.
  File saved to counter.json
  ```

## <a name="dotnet-counters-list"></a><span data-ttu-id="c0990-168">dotnet-counters list</span><span class="sxs-lookup"><span data-stu-id="c0990-168">dotnet-counters list</span></span>

<span data-ttu-id="c0990-169">Muestra una lista de nombres y descripciones de contador, agrupada por proveedor.</span><span class="sxs-lookup"><span data-stu-id="c0990-169">Displays a list of counter names and descriptions, grouped by provider.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c0990-170">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0990-170">Synopsis</span></span>

```console
dotnet-counters list [-h|--help]
```

### <a name="example"></a><span data-ttu-id="c0990-171">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0990-171">Example</span></span>

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
> <span data-ttu-id="c0990-172">Los contadores de `Microsoft.AspNetCore.Hosting` se muestran cuando hay procesos identificados que admiten estos contadores, por ejemplo, cuando una aplicación ASP.NET Core se está ejecutando en el equipo host.</span><span class="sxs-lookup"><span data-stu-id="c0990-172">The `Microsoft.AspNetCore.Hosting` counters are displayed when there are processes identified that support these counters, for example; when an ASP.NET Core application is running on the host machine.</span></span>

## <a name="dotnet-counters-monitor"></a><span data-ttu-id="c0990-173">dotnet-counters monitor</span><span class="sxs-lookup"><span data-stu-id="c0990-173">dotnet-counters monitor</span></span>

<span data-ttu-id="c0990-174">Muestra la actualización periódica de los valores de los contadores seleccionados.</span><span class="sxs-lookup"><span data-stu-id="c0990-174">Displays periodically refreshing values of selected counters.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c0990-175">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0990-175">Synopsis</span></span>

```console
dotnet-counters monitor [-h|--help] [-p|--process-id] [-n|--name] [--diagnostic-port] [--refresh-interval] [--counters] [-- <command>]
```

### <a name="options"></a><span data-ttu-id="c0990-176">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0990-176">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="c0990-177">Id. del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="c0990-177">The ID of the process to be monitored.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="c0990-178">Nombre del proceso que se va a supervisar.</span><span class="sxs-lookup"><span data-stu-id="c0990-178">The name of the process to be monitored.</span></span>

- **`--diagnostic-port`**

  <span data-ttu-id="c0990-179">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="c0990-179">The name of the diagnostic port to create.</span></span> <span data-ttu-id="c0990-180">Vea [Uso del puerto de diagnóstico](#using-diagnostic-port) para saber cómo usar esta opción a fin de iniciar los contadores de supervisión desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0990-180">See [using diagnostic port](#using-diagnostic-port) for how to use this option to start monitoring counters from app startup.</span></span>

- **`--refresh-interval <SECONDS>`**

  <span data-ttu-id="c0990-181">Número de segundos de retraso entre la actualización de los contadores mostrados.</span><span class="sxs-lookup"><span data-stu-id="c0990-181">The number of seconds to delay between updating the displayed counters</span></span>

- **`--counters <COUNTERS>`**

  <span data-ttu-id="c0990-182">Una lista de contadores separados por comas.</span><span class="sxs-lookup"><span data-stu-id="c0990-182">A comma-separated list of counters.</span></span> <span data-ttu-id="c0990-183">Los contadores pueden ser `provider_name[:counter_name]` especificados.</span><span class="sxs-lookup"><span data-stu-id="c0990-183">Counters can be specified `provider_name[:counter_name]`.</span></span> <span data-ttu-id="c0990-184">Si se usa `provider_name` sin una lista de contadores que cumplan los requisitos, se mostrarán todos los contadores del proveedor.</span><span class="sxs-lookup"><span data-stu-id="c0990-184">If the `provider_name` is used without a qualifying list of counters, then all counters from the provider are shown.</span></span> <span data-ttu-id="c0990-185">Para descubrir los nombres del proveedor y del contador, use el comando [dotnet-counters list](#dotnet-counters-list).</span><span class="sxs-lookup"><span data-stu-id="c0990-185">To discover provider and counter names, use the [dotnet-counters list](#dotnet-counters-list) command.</span></span>

 <span data-ttu-id="c0990-186">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0 o versiones posteriores)**</span><span class="sxs-lookup"><span data-stu-id="c0990-186">**`-- <command>` (for target applications running .NET 5.0 or later only)**</span></span>

  <span data-ttu-id="c0990-187">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="c0990-187">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="c0990-188">`dotnet-counters` iniciará un proceso con el comando proporcionado y supervisará las métricas solicitadas.</span><span class="sxs-lookup"><span data-stu-id="c0990-188">`dotnet-counters` will launch a process with the provided command and monitor the requested metrics.</span></span> <span data-ttu-id="c0990-189">Esto suele ser útil para recopilar métricas de la ruta de acceso de inicio de la aplicación y se puede usar para diagnosticar o supervisar los problemas que se producen antes o poco después del punto de entrada principal.</span><span class="sxs-lookup"><span data-stu-id="c0990-189">This is often useful to collect metrics for the application's startup path and can be used to diagnose or monitor issues that happen early before or shortly after the main entrypoint.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0990-190">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="c0990-190">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="c0990-191">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="c0990-191">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0990-192">El inicio de un archivo ejecutable de .NET por medio de dotnet-counters redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="c0990-192">Launching a .NET executable via dotnet-counters will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span> <span data-ttu-id="c0990-193">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="c0990-193">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span> <span data-ttu-id="c0990-194">Si el proceso secundario termina antes que la herramienta, esta también se cerrará.</span><span class="sxs-lookup"><span data-stu-id="c0990-194">If the child process exits before the tool, the tool will exit as well.</span></span> <span data-ttu-id="c0990-195">Si necesita usar stdin/stdout, puede usar la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="c0990-195">If you need to use stdin/stdout, you can use the `--diagnostic-port` option.</span></span> <span data-ttu-id="c0990-196">Para obtener más información, vea [Uso del puerto de diagnóstico](#using-diagnostic-port).</span><span class="sxs-lookup"><span data-stu-id="c0990-196">See [Using diagnostic port](#using-diagnostic-port) for more information.</span></span>

> [!NOTE]
> <span data-ttu-id="c0990-197">En Linux y macOS, este comando espera que la aplicación de destino y `dotnet-counters` compartan la misma variable de entorno `TMPDIR`.</span><span class="sxs-lookup"><span data-stu-id="c0990-197">On Linux and macOS, this command expects the target application and `dotnet-counters` to share the same `TMPDIR` environment variable.</span></span>

> [!NOTE]
> <span data-ttu-id="c0990-198">Para supervisar métricas mediante `dotnet-counters`, debe ejecutarse como el mismo usuario que el que ejecuta el proceso de destino, o bien como usuario raíz.</span><span class="sxs-lookup"><span data-stu-id="c0990-198">To monitor metrics using `dotnet-counters`, it needs to be run as the same user as the user running target process or as root.</span></span>

> [!NOTE]
> <span data-ttu-id="c0990-199">Si ve un mensaje de error similar al siguiente: `[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`, está intentando usar `dotnet-counters` que tiene un valor de bits no coincidente con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="c0990-199">If you see an error message similar to the following one: `[ERROR] System.ComponentModel.Win32Exception (299): A 32 bit processes cannot access modules of a 64 bit process.`, you are trying to use `dotnet-counters` that has mismatched bitness against the target process.</span></span> <span data-ttu-id="c0990-200">Asegúrese de descargar el valor de bits correcto de la herramienta en el vínculo de [instalación](#install).</span><span class="sxs-lookup"><span data-stu-id="c0990-200">Make sure to download the correct bitness of the tool in the [install](#install) link.</span></span>

### <a name="examples"></a><span data-ttu-id="c0990-201">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c0990-201">Examples</span></span>

- <span data-ttu-id="c0990-202">Supervisión de todos los contadores de `System.Runtime` con un intervalo de actualización de 3 segundos:</span><span class="sxs-lookup"><span data-stu-id="c0990-202">Monitor all counters from `System.Runtime` at a refresh interval of 3 seconds:</span></span>

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

- <span data-ttu-id="c0990-203">Supervisión de únicamente el uso de la CPU y el tamaño del montón de GC de `System.Runtime`:</span><span class="sxs-lookup"><span data-stu-id="c0990-203">Monitor just CPU usage and GC heap size from `System.Runtime`:</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters System.Runtime[cpu-usage,gc-heap-size]

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      CPU Usage (%)                                 24
      GC Heap Size (MB)                            811
  ```

- <span data-ttu-id="c0990-204">Supervisión de los valores `EventCounter` del elemento `EventSource` definido por el usuario.</span><span class="sxs-lookup"><span data-stu-id="c0990-204">Monitor `EventCounter` values from user-defined `EventSource`.</span></span> <span data-ttu-id="c0990-205">Para obtener más información, consulte [Tutorial: Medición del rendimiento mediante EventCounters en .NET Core](event-counter-perf.md).</span><span class="sxs-lookup"><span data-stu-id="c0990-205">For more information, see [Tutorial: Measure performance using EventCounters in .NET Core](event-counter-perf.md).</span></span>

  ```console
  > dotnet-counters monitor --process-id 1902 --counters Samples-EventCounterDemos-Minimal

  Press p to pause, r to resume, q to quit.
      request                                      100
  ```

- <span data-ttu-id="c0990-206">Vea todos los contadores conocidos que están disponibles en `dotnet-counters`:</span><span class="sxs-lookup"><span data-stu-id="c0990-206">View all well-known counters that are available in `dotnet-counters`:</span></span>

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

- <span data-ttu-id="c0990-207">Vea todos los contadores conocidos que están disponibles en `dotnet-counters` para aplicaciones de .NET 5:</span><span class="sxs-lookup"><span data-stu-id="c0990-207">View all well-known counters that are available in `dotnet-counters` for .NET 5 apps:</span></span>

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

- <span data-ttu-id="c0990-208">Inicie `my-aspnet-server.exe` y supervise el número de ensamblados cargados desde su inicio (solo para .NET 5.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c0990-208">Launch `my-aspnet-server.exe` and monitor the # of assemblies loaded from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c0990-209">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c0990-209">This works for apps running .NET 5.0 or later only.</span></span>

  ```console
  > dotnet-counters monitor --counters System.Runtime[assembly-count] -- my-aspnet-server.exe

  Press p to pause, r to resume, q to quit.
    Status: Running

  [System.Runtime]
      Number of Assemblies Loaded                   24
  ```
  
- <span data-ttu-id="c0990-210">Inicie `my-aspnet-server.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y supervise su espacio de trabajo y el tamaño del montón de GC desde su inicio (solo para .NET 5.0 o versiones posteriores):</span><span class="sxs-lookup"><span data-stu-id="c0990-210">Launch `my-aspnet-server.exe` with `arg1` and `arg2` as command-line arguments and monitor its working set and GC heap size from its startup (.NET 5.0 or later only):</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c0990-211">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c0990-211">This works for apps running .NET 5.0 or later only.</span></span>

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

## <a name="dotnet-counters-ps"></a><span data-ttu-id="c0990-212">dotnet-counters ps</span><span class="sxs-lookup"><span data-stu-id="c0990-212">dotnet-counters ps</span></span>

<span data-ttu-id="c0990-213">Muestra una lista de los procesos de dotnet que se pueden supervisar.</span><span class="sxs-lookup"><span data-stu-id="c0990-213">Display a list of dotnet processes that can be monitored.</span></span>

### <a name="synopsis"></a><span data-ttu-id="c0990-214">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0990-214">Synopsis</span></span>

```console
dotnet-counters ps [-h|--help]
```

### <a name="example"></a><span data-ttu-id="c0990-215">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c0990-215">Example</span></span>

```console
> dotnet-counters ps
  
  15683 WebApi     /home/user/repos/WebApi/WebApi
  16324 dotnet     /usr/local/share/dotnet/dotnet
```

## <a name="using-diagnostic-port"></a><span data-ttu-id="c0990-216">Uso del puerto de diagnóstico</span><span class="sxs-lookup"><span data-stu-id="c0990-216">Using diagnostic port</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c0990-217">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c0990-217">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="c0990-218">El puerto de diagnóstico es una característica nueva del entorno de ejecución que se ha agregado en .NET 5 y permite iniciar la supervisión o la recopilación de contadores desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0990-218">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start monitoring or collecting counters from app startup.</span></span> <span data-ttu-id="c0990-219">Para hacer esto con `dotnet-counters`, puede usar `dotnet-counters <collect|monitor> -- <command>`, tal como se describe en los ejemplos anteriores, o bien la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="c0990-219">To do this using `dotnet-counters`, you can either use `dotnet-counters <collect|monitor> -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="c0990-220">El uso de `dotnet-counters <collect|monitor> -- <command>` para iniciar la aplicación como un proceso secundario es la manera más sencilla de realizar una supervisión rápida desde el inicio.</span><span class="sxs-lookup"><span data-stu-id="c0990-220">Using `dotnet-counters <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly monitor it from its startup.</span></span>

<span data-ttu-id="c0990-221">Sin embargo, si quiere obtener un control más preciso sobre la vigencia de la aplicación supervisada (por ejemplo, supervisar la aplicación solo durante los primeros 10 minutos y continuar la ejecución), o si necesita interactuar con la aplicación mediante la CLI, el uso de la opción `--diagnostic-port` le permite controlar la aplicación de destino que se supervisa y `dotnet-counters`.</span><span class="sxs-lookup"><span data-stu-id="c0990-221">However, when you want to gain a finer control over the lifetime of the app being monitored (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-counters`.</span></span>

1. <span data-ttu-id="c0990-222">El comando siguiente hace que dotnet-counters cree un socket de diagnóstico denominado `myport.sock` y que espere a una conexión.</span><span class="sxs-lookup"><span data-stu-id="c0990-222">The command below makes dotnet-counters create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-counters collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="c0990-223">Salida:</span><span class="sxs-lookup"><span data-stu-id="c0990-223">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="c0990-224">En una consola independiente, inicie la aplicación de destino con la variable de entorno `DOTNET_DiagnosticPorts` establecida en el valor de la salida de `dotnet-counters`.</span><span class="sxs-lookup"><span data-stu-id="c0990-224">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-counters` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="c0990-225">Esto debe habilitar `dotnet-counters` para empezar a recopilar contadores en `my-dotnet-app`:</span><span class="sxs-lookup"><span data-stu-id="c0990-225">This should then enable `dotnet-counters` to start collecting counters on `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="c0990-226">Iniciar la aplicación con `dotnet run` puede resultar problemático porque la CLI de dotnet puede generar muchos procesos secundarios que no sean la aplicación. Además, dichos procesos secundarios pueden conectarse a `dotnet-counters` antes que la aplicación, lo que causa que esta se suspenda en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c0990-226">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-counters` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="c0990-227">Se recomienda usar directamente una versión independiente de la aplicación o `dotnet exec` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="c0990-227">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>
