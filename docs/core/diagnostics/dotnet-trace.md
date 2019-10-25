---
title: 'dotnet-trace: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-trace.
author: sdmaclea
ms.author: stmaclea
ms.date: 10/14/2019
ms.openlocfilehash: 6513cf63070bc1984006da75313e9912d76a6c95
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "72321535"
---
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a><span data-ttu-id="26d07-103">Seguimiento de la utilidad de análisis de rendimiento (`dotnet-trace`)</span><span class="sxs-lookup"><span data-stu-id="26d07-103">Trace for performance analysis utility (`dotnet-trace`)</span></span>

<span data-ttu-id="26d07-104">**Este artículo se aplica a:** SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="26d07-104">**This article applies to:** .NET Core 3.0 SDK and later versions</span></span>

## <a name="installing-dotnet-trace"></a><span data-ttu-id="26d07-105">Instalación de `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="26d07-105">Installing `dotnet-trace`</span></span>

<span data-ttu-id="26d07-106">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="26d07-106">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="26d07-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="26d07-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="26d07-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="26d07-108">Description</span></span>

<span data-ttu-id="26d07-109">La herramienta `dotnet-trace` es una herramienta global de CLI multiplataforma que permite la recopilación de seguimientos de .NET Core de un proceso en ejecución sin ningún generador de perfiles nativo implicado.</span><span class="sxs-lookup"><span data-stu-id="26d07-109">The `dotnet-trace` tool is a cross-platform CLI global tool that enables the collection of .NET Core traces of a running process without any native profiler involved.</span></span> <span data-ttu-id="26d07-110">Se basa en la tecnología `EventPipe` multiplataforma del runtime de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="26d07-110">It's built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span> <span data-ttu-id="26d07-111">`dotnet-trace` ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="26d07-111">`dotnet-trace` delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="26d07-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="26d07-112">Options</span></span>

- **`--version`**

<span data-ttu-id="26d07-113">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="26d07-113">Display the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

<span data-ttu-id="26d07-114">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="26d07-114">Show command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="26d07-115">Comandos</span><span class="sxs-lookup"><span data-stu-id="26d07-115">Commands</span></span>

| <span data-ttu-id="26d07-116">Comando</span><span class="sxs-lookup"><span data-stu-id="26d07-116">Command</span></span>                                                     |
| ----------------------------------------------------------- |
| [<span data-ttu-id="26d07-117">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="26d07-117">dotnet-trace collect</span></span>](#dotnet-trace-collect)               |
| [<span data-ttu-id="26d07-118">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="26d07-118">dotnet-trace convert</span></span>](#dotnet-trace-convert)               |
| [<span data-ttu-id="26d07-119">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="26d07-119">dotnet-trace list-processes</span></span>](#dotnet-trace-list-processes) |
| [<span data-ttu-id="26d07-120">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="26d07-120">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="26d07-121">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="26d07-121">dotnet-trace collect</span></span>

<span data-ttu-id="26d07-122">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="26d07-122">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="26d07-123">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="26d07-123">Synopsis</span></span>

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a><span data-ttu-id="26d07-124">Opciones</span><span class="sxs-lookup"><span data-stu-id="26d07-124">Options</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="26d07-125">Proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="26d07-125">The process to collect the trace from.</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="26d07-126">Establece el tamaño del búfer circular en memoria en megabytes.</span><span class="sxs-lookup"><span data-stu-id="26d07-126">Sets the size of the in-memory circular buffer in megabytes.</span></span> <span data-ttu-id="26d07-127">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="26d07-127">Default 256 MB.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="26d07-128">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="26d07-128">The output path for the collected trace data.</span></span> <span data-ttu-id="26d07-129">Si no se especifica, el valor predeterminado es`trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="26d07-129">If not specified it defaults to `trace.nettrace`.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="26d07-130">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="26d07-130">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="26d07-131">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="26d07-131">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="26d07-132">Si hay alguna incoherencia para un proveedor determinado, la configuración aquí tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="26d07-132">If there's any inconsistency for a particular provider, the configuration here takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="26d07-133">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="26d07-133">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="26d07-134">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="26d07-134">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="26d07-135">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="26d07-135">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="26d07-136">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="26d07-136">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="26d07-137">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="26d07-137">Sets the output format for the trace file conversion.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="26d07-138">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="26d07-138">dotnet-trace convert</span></span>

<span data-ttu-id="26d07-139">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="26d07-139">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="26d07-140">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="26d07-140">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a><span data-ttu-id="26d07-141">Argumentos</span><span class="sxs-lookup"><span data-stu-id="26d07-141">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="26d07-142">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="26d07-142">Input trace file to be converted.</span></span> <span data-ttu-id="26d07-143">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="26d07-143">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="26d07-144">Opciones</span><span class="sxs-lookup"><span data-stu-id="26d07-144">Options</span></span>

- **`--format <NetTrace|Speedscope>`**

  <span data-ttu-id="26d07-145">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="26d07-145">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="26d07-146">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="26d07-146">Output filename.</span></span> <span data-ttu-id="26d07-147">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="26d07-147">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-list-processes"></a><span data-ttu-id="26d07-148">dotnet-trace list-processes</span><span class="sxs-lookup"><span data-stu-id="26d07-148">dotnet-trace list-processes</span></span>

<span data-ttu-id="26d07-149">Muestra los procesos de dotnet en los que se puede realizar un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="26d07-149">Lists dotnet processes that can be traced.</span></span>

### <a name="synopsis"></a><span data-ttu-id="26d07-150">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="26d07-150">Synopsis</span></span>

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="26d07-151">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="26d07-151">dotnet-trace list-profiles</span></span>

<span data-ttu-id="26d07-152">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="26d07-152">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="26d07-153">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="26d07-153">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="26d07-154">Recopilación de un seguimiento con `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="26d07-154">Collect a trace with `dotnet-trace`</span></span>

- <span data-ttu-id="26d07-155">Para recopilar seguimientos mediante `dotnet-trace`, primero debe averiguar el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="26d07-155">To collect traces using `dotnet-trace`, you'll need to first, find out the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="26d07-156">En Windows, hay opciones como el uso del administrador de tareas o el comando `tasklist`.</span><span class="sxs-lookup"><span data-stu-id="26d07-156">On Windows, there are options such as using the task manager or the `tasklist` command.</span></span>
  - <span data-ttu-id="26d07-157">En Linux, la opción trivial podría ser con el uso del comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="26d07-157">On Linux, the trivial option could be using `ps` command.</span></span>

<span data-ttu-id="26d07-158">También puede usar el comando [dotnet-trace list-processes](#dotnet-trace-list-processes) para averiguar qué procesos de .NET Core se están ejecutando, junto con los PID.</span><span class="sxs-lookup"><span data-stu-id="26d07-158">You may also use the [dotnet-trace list-processes](#dotnet-trace-list-processes) command to find out what .NET Core processes are running, along with their PIDs.</span></span>

- <span data-ttu-id="26d07-159">Luego, ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="26d07-159">Then, run the following command:</span></span>

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- <span data-ttu-id="26d07-160">Por último, detenga la recolección presionando la tecla `<Enter>` y `dotnet-trace` terminará de registrar los eventos en el archivo `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="26d07-160">Finally, stop collection by pressing the `<Enter>` key, and `dotnet-trace` will finish logging events to `trace.nettrace` file.</span></span>

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="26d07-161">Vista del seguimiento capturado desde `dotnet-trace`</span><span class="sxs-lookup"><span data-stu-id="26d07-161">Viewing the trace captured from `dotnet-trace`</span></span>

<span data-ttu-id="26d07-162">En Windows, los archivos `.nettrace` se pueden ver en [PerfView](https://github.com/microsoft/perfview) para su análisis, al igual que los seguimientos recopilados con ETW o LTTng.</span><span class="sxs-lookup"><span data-stu-id="26d07-162">On Windows, `.nettrace` files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis, just like traces collected with ETW or LTTng.</span></span> <span data-ttu-id="26d07-163">En el caso de los seguimientos recopilados en Linux, puede trasladar el seguimiento a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="26d07-163">For traces collected on Linux, you can move the trace to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="26d07-164">También puede ver el seguimiento en una máquina Linux cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="26d07-164">You may also view the trace on a Linux machine by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="26d07-165">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="26d07-165">You can change the output file format using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` to produce a `speedscope` file.</span></span> <span data-ttu-id="26d07-166">Actualmente, puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="26d07-166">You can currently choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="26d07-167">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="26d07-167">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="26d07-168">El runtime de .NET Core genera seguimientos en el formato `nettrace` y se convierten a speedscope (si se especifica) una vez completado este seguimiento.</span><span class="sxs-lookup"><span data-stu-id="26d07-168">The .NET Core runtime generates traces in the `nettrace` format, and they're converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="26d07-169">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="26d07-169">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="26d07-170">Uso de `dotnet-trace` para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="26d07-170">Using `dotnet-trace` to collect counter values over time</span></span>

<span data-ttu-id="26d07-171">Si está intentando usar `EventCounter` para la supervisión básica del estado en configuraciones sensibles al rendimiento, como los entornos de producción, y quiere recopilar seguimientos en lugar de verlos en tiempo real, también puede hacerlo con `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="26d07-171">If you're trying to use `EventCounter` for basic health monitoring in  performance-sensitive settings like production environments and you want to collect traces instead of watching them in real time, you can do that with `dotnet-trace` as well.</span></span>

<span data-ttu-id="26d07-172">Por ejemplo, si quiere recopilar valores de contador de rendimiento en runtime, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="26d07-172">For example, if you want to collect runtime performance counter values, you can use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="26d07-173">Este comando indica a los contadores en runtime que se van a notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="26d07-173">This command tells the runtime counters to be reported once every second for lightweight health monitoring.</span></span> <span data-ttu-id="26d07-174">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="26d07-174">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows you to collect a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="26d07-175">Si quiere deshabilitar los eventos en runtime para reducir aún más la sobrecarga (y el tamaño de seguimiento), puede usar el comando siguiente para deshabilitar los eventos en runtime y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="26d07-175">If you want to disable runtime events to reduce the overhead (and trace size) even further, you can use the following command to disable runtime events and managed stack profiler.</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a><span data-ttu-id="26d07-176">Proveedores .NET</span><span class="sxs-lookup"><span data-stu-id="26d07-176">.NET Providers</span></span>

<span data-ttu-id="26d07-177">El runtime de .NET Core admite los siguientes proveedores .NET.</span><span class="sxs-lookup"><span data-stu-id="26d07-177">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="26d07-178">.NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.</span><span class="sxs-lookup"><span data-stu-id="26d07-178">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="26d07-179">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="26d07-179">Provider name</span></span>                            | <span data-ttu-id="26d07-180">Información</span><span class="sxs-lookup"><span data-stu-id="26d07-180">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="26d07-181">El proveedor de runtime</span><span class="sxs-lookup"><span data-stu-id="26d07-181">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="26d07-182">Palabras clave de runtime de CLR</span><span class="sxs-lookup"><span data-stu-id="26d07-182">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="26d07-183">El proveedor de informe detallado</span><span class="sxs-lookup"><span data-stu-id="26d07-183">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="26d07-184">Palabras clave de informe detallado de CLR</span><span class="sxs-lookup"><span data-stu-id="26d07-184">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="26d07-185">Habilita el generador de perfiles de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="26d07-185">Enables the sample profiler.</span></span> |
