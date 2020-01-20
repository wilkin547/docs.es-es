---
title: 'La herramienta dotnet-trace: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 64c931db5a18659707e832aaca910cfbbd6823c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714433"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="77ed6-103">Utilidad de análisis de rendimiento dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="77ed6-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="77ed6-104">**Este artículo se aplica a:** ✓ SDK de .NET Core 3.0.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="77ed6-104">**This article applies to:** ✓ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="77ed6-105">Instalación de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="77ed6-105">Install dotnet-trace</span></span>

<span data-ttu-id="77ed6-106">Instale el [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` con el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="77ed6-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="77ed6-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="77ed6-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="77ed6-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="77ed6-108">Description</span></span>

<span data-ttu-id="77ed6-109">La herramienta `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="77ed6-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="77ed6-110">Es una herramienta de .NET Core para varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="77ed6-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="77ed6-111">Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.</span><span class="sxs-lookup"><span data-stu-id="77ed6-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="77ed6-112">Se basa en la tecnología `EventPipe` multiplataforma del entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="77ed6-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="77ed6-113">Ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="77ed6-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="77ed6-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="77ed6-114">Options</span></span>

- **`--version`**  

  <span data-ttu-id="77ed6-115">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="77ed6-115">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="77ed6-116">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="77ed6-116">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="77ed6-117">Comandos</span><span class="sxs-lookup"><span data-stu-id="77ed6-117">Commands</span></span>

| <span data-ttu-id="77ed6-118">Comando</span><span class="sxs-lookup"><span data-stu-id="77ed6-118">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="77ed6-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="77ed6-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="77ed6-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="77ed6-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="77ed6-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="77ed6-121">dotnet-trace ps</span></span>](#dotnet-trace-ps) |
| [<span data-ttu-id="77ed6-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="77ed6-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="77ed6-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="77ed6-123">dotnet-trace collect</span></span>

<span data-ttu-id="77ed6-124">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="77ed6-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="77ed6-125">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="77ed6-125">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="77ed6-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="77ed6-126">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="77ed6-127">Proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="77ed6-127">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="77ed6-128">Establece el tamaño del búfer circular en memoria, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="77ed6-128">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="77ed6-129">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="77ed6-129">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="77ed6-130">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="77ed6-130">The output path for the collected trace data.</span></span> <span data-ttu-id="77ed6-131">Si no se especifica, el valor predeterminado es`trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-131">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="77ed6-132">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="77ed6-132">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="77ed6-133">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-133">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="77ed6-134">Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="77ed6-134">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="77ed6-135">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="77ed6-135">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="77ed6-136">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-136">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="77ed6-137">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-137">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="77ed6-138">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="77ed6-138">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format {NetTrace|Speedscope}`**

  <span data-ttu-id="77ed6-139">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="77ed6-139">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="77ed6-140">De manera predeterminada, es `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-140">The default is `NetTrace`.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="77ed6-141">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="77ed6-141">dotnet-trace convert</span></span>

<span data-ttu-id="77ed6-142">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="77ed6-142">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="77ed6-143">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="77ed6-143">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="77ed6-144">Argumentos</span><span class="sxs-lookup"><span data-stu-id="77ed6-144">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="77ed6-145">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="77ed6-145">Input trace file to be converted.</span></span> <span data-ttu-id="77ed6-146">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="77ed6-146">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="77ed6-147">Opciones</span><span class="sxs-lookup"><span data-stu-id="77ed6-147">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="77ed6-148">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="77ed6-148">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="77ed6-149">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="77ed6-149">Output filename.</span></span> <span data-ttu-id="77ed6-150">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="77ed6-150">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="77ed6-151">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="77ed6-151">dotnet-trace ps</span></span>

<span data-ttu-id="77ed6-152">Muestra los procesos de dotnet a los cuales se puede adjuntar.</span><span class="sxs-lookup"><span data-stu-id="77ed6-152">Lists dotnet processes that can be attached to.</span></span>

### <a name="synopsis"></a><span data-ttu-id="77ed6-153">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="77ed6-153">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="77ed6-154">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="77ed6-154">dotnet-trace list-profiles</span></span>

<span data-ttu-id="77ed6-155">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="77ed6-155">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="77ed6-156">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="77ed6-156">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="77ed6-157">Recopilación de un seguimiento con dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="77ed6-157">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="77ed6-158">Para recopilar seguimientos mediante `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="77ed6-158">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="77ed6-159">Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="77ed6-159">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="77ed6-160">En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="77ed6-160">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="77ed6-161">En Linux, por ejemplo, el comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-161">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="77ed6-162">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="77ed6-162">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="77ed6-163">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="77ed6-163">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="77ed6-164">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="77ed6-164">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="77ed6-165">Detenga la recolección presionando la tecla `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-165">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="77ed6-166">`dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="77ed6-166">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="77ed6-167">Vista del seguimiento capturado de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="77ed6-167">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="77ed6-168">En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="77ed6-168">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="77ed6-169">En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-169">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="77ed6-170">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-170">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="77ed6-171">Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-171">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="77ed6-172">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="77ed6-172">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="77ed6-173">El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-173">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="77ed6-174">Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="77ed6-174">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="77ed6-175">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="77ed6-175">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="77ed6-176">Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="77ed6-176">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="77ed6-177">`dotnet-trace` puede:</span><span class="sxs-lookup"><span data-stu-id="77ed6-177">`dotnet-trace` can:</span></span>

* <span data-ttu-id="77ed6-178">Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="77ed6-178">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="77ed6-179">Por ejemplo, en producción.</span><span class="sxs-lookup"><span data-stu-id="77ed6-179">For example, in production.</span></span>
* <span data-ttu-id="77ed6-180">Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="77ed6-180">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="77ed6-181">Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="77ed6-181">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="77ed6-182">El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="77ed6-182">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="77ed6-183">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="77ed6-183">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="77ed6-184">El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:</span><span class="sxs-lookup"><span data-stu-id="77ed6-184">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="77ed6-185">El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="77ed6-185">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="77ed6-186">Proveedores .NET</span><span class="sxs-lookup"><span data-stu-id="77ed6-186">.NET Providers</span></span>

<span data-ttu-id="77ed6-187">El runtime de .NET Core admite los siguientes proveedores .NET.</span><span class="sxs-lookup"><span data-stu-id="77ed6-187">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="77ed6-188">.NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.</span><span class="sxs-lookup"><span data-stu-id="77ed6-188">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="77ed6-189">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="77ed6-189">Provider name</span></span>                            | <span data-ttu-id="77ed6-190">Información</span><span class="sxs-lookup"><span data-stu-id="77ed6-190">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="77ed6-191">El proveedor de runtime</span><span class="sxs-lookup"><span data-stu-id="77ed6-191">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="77ed6-192">Palabras clave de runtime de CLR</span><span class="sxs-lookup"><span data-stu-id="77ed6-192">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="77ed6-193">El proveedor de informe detallado</span><span class="sxs-lookup"><span data-stu-id="77ed6-193">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="77ed6-194">Palabras clave de informe detallado de CLR</span><span class="sxs-lookup"><span data-stu-id="77ed6-194">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="77ed6-195">Habilita el generador de perfiles de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="77ed6-195">Enables the sample profiler.</span></span> |
