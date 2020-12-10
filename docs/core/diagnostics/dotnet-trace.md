---
title: 'Herramienta de diagnóstico dotnet-trace: CLI de .NET'
description: Aprenda a instalar y usar la herramienta dotnet-trace de la CLI para recopilar seguimientos de .NET de un proceso en ejecución sin el generador de perfiles nativo, mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 6bc5ad449f62ed0080ff6b1f401f1871d90cf5ec
ms.sourcegitcommit: c6de55556add9f92af17e0f8d1da8f356a19a03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "96549337"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="f6304-103">Utilidad de análisis de rendimiento dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="f6304-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="f6304-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="f6304-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="f6304-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="f6304-105">Install</span></span>

<span data-ttu-id="f6304-106">Hay dos maneras de descargar e instalar `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="f6304-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="f6304-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="f6304-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="f6304-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="f6304-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="f6304-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="f6304-109">**Direct download:**</span></span>

  <span data-ttu-id="f6304-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="f6304-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="f6304-111">SO</span><span class="sxs-lookup"><span data-stu-id="f6304-111">OS</span></span>  | <span data-ttu-id="f6304-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="f6304-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="f6304-113">Windows</span><span class="sxs-lookup"><span data-stu-id="f6304-113">Windows</span></span> | <span data-ttu-id="f6304-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="f6304-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="f6304-115">macOS</span><span class="sxs-lookup"><span data-stu-id="f6304-115">macOS</span></span>   | [<span data-ttu-id="f6304-116">x64</span><span class="sxs-lookup"><span data-stu-id="f6304-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="f6304-117">Linux</span><span class="sxs-lookup"><span data-stu-id="f6304-117">Linux</span></span>   | <span data-ttu-id="f6304-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="f6304-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="f6304-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f6304-119">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="f6304-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6304-120">Description</span></span>

<span data-ttu-id="f6304-121">La herramienta `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="f6304-121">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="f6304-122">Es una herramienta de .NET Core para varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="f6304-122">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="f6304-123">Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.</span><span class="sxs-lookup"><span data-stu-id="f6304-123">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="f6304-124">Se basa en [`EventPipe`](./eventpipe.md) del entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f6304-124">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="f6304-125">Ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="f6304-125">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="f6304-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="f6304-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="f6304-127">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="f6304-127">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="f6304-128">Muestra la versión de la utilidad dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="f6304-128">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="f6304-129">Comandos</span><span class="sxs-lookup"><span data-stu-id="f6304-129">Commands</span></span>

| <span data-ttu-id="f6304-130">Comando</span><span class="sxs-lookup"><span data-stu-id="f6304-130">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="f6304-131">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="f6304-131">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="f6304-132">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="f6304-132">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="f6304-133">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="f6304-133">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="f6304-134">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="f6304-134">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="f6304-135">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="f6304-135">dotnet-trace collect</span></span>

<span data-ttu-id="f6304-136">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="f6304-136">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f6304-137">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f6304-137">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="f6304-138">Opciones</span><span class="sxs-lookup"><span data-stu-id="f6304-138">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="f6304-139">Establece el tamaño del búfer circular en memoria, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="f6304-139">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="f6304-140">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="f6304-140">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="f6304-141">Nivel de detalle de los eventos CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="f6304-141">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="f6304-142">Lista de eventos de tiempo de ejecución de CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="f6304-142">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="f6304-143">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-143">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="f6304-144">De manera predeterminada, es `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="f6304-144">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="f6304-145">Nombre del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-145">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="f6304-146">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="f6304-146">The output path for the collected trace data.</span></span> <span data-ttu-id="f6304-147">Si no se especifica, el valor predeterminado es `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="f6304-147">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="f6304-148">Identificador del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-148">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="f6304-149">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="f6304-149">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="f6304-150">Hay disponibles los perfiles siguientes:</span><span class="sxs-lookup"><span data-stu-id="f6304-150">The following profiles are available:</span></span>

 | <span data-ttu-id="f6304-151">Perfil</span><span class="sxs-lookup"><span data-stu-id="f6304-151">Profile</span></span> | <span data-ttu-id="f6304-152">Descripción</span><span class="sxs-lookup"><span data-stu-id="f6304-152">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="f6304-153">Resulta útil para realizar el seguimiento del uso de CPU y la información general del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="f6304-153">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="f6304-154">Esta es la opción predeterminada si no se especifica ningún perfil o proveedor.</span><span class="sxs-lookup"><span data-stu-id="f6304-154">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="f6304-155">Realiza un seguimiento de las recolecciones de elementos no utilizados y las asignaciones de objetos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f6304-155">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="f6304-156">Realiza un seguimiento de las recolecciones de elementos no utilizados solo con una sobrecarga muy baja.</span><span class="sxs-lookup"><span data-stu-id="f6304-156">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="f6304-157">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="f6304-157">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="f6304-158">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="f6304-158">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="f6304-159">Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="f6304-159">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="f6304-160">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="f6304-160">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="f6304-161">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="f6304-161">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="f6304-162">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="f6304-162">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="f6304-163">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0)**</span><span class="sxs-lookup"><span data-stu-id="f6304-163">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="f6304-164">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="f6304-164">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="f6304-165">Esto puede resultar útil al diagnosticar problemas que se producen al principio del proceso, como problemas de rendimiento de inicio o de cargador de ensamblados y errores del enlazador.</span><span class="sxs-lookup"><span data-stu-id="f6304-165">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f6304-166">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="f6304-166">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="f6304-167">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="f6304-167">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="f6304-168">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="f6304-168">dotnet-trace convert</span></span>

<span data-ttu-id="f6304-169">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="f6304-169">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f6304-170">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f6304-170">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="f6304-171">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f6304-171">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="f6304-172">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="f6304-172">Input trace file to be converted.</span></span> <span data-ttu-id="f6304-173">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="f6304-173">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="f6304-174">Opciones</span><span class="sxs-lookup"><span data-stu-id="f6304-174">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="f6304-175">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-175">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="f6304-176">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="f6304-176">Output filename.</span></span> <span data-ttu-id="f6304-177">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="f6304-177">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="f6304-178">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="f6304-178">dotnet-trace ps</span></span>

 <span data-ttu-id="f6304-179">Enumera los procesos de dotnet de los que se pueden recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="f6304-179">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f6304-180">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f6304-180">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="f6304-181">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="f6304-181">dotnet-trace list-profiles</span></span>

<span data-ttu-id="f6304-182">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="f6304-182">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="f6304-183">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f6304-183">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="f6304-184">Recopilación de un seguimiento con dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="f6304-184">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="f6304-185">Para recopilar seguimientos mediante `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="f6304-185">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="f6304-186">Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="f6304-186">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="f6304-187">En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f6304-187">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="f6304-188">En Linux, por ejemplo, el comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="f6304-188">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="f6304-189">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="f6304-189">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="f6304-190">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="f6304-190">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="f6304-191">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6304-191">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="f6304-192">Detenga la recolección presionando la tecla `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="f6304-192">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="f6304-193">`dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="f6304-193">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="f6304-194">Inicio de una aplicación secundaria y recopilación de un seguimiento de su inicio mediante dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="f6304-194">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6304-195">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="f6304-195">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="f6304-196">A veces puede resultar útil recopilar un seguimiento de un proceso desde su inicio.</span><span class="sxs-lookup"><span data-stu-id="f6304-196">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="f6304-197">En el caso de las aplicaciones que ejecutan .NET 5.0 o versiones posteriores, es posible hacerlo mediante dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="f6304-197">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="f6304-198">Esto iniciará `hello.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y recopilará un seguimiento de su inicio en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="f6304-198">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="f6304-199">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6304-199">The preceding command generates output similar to the following:</span></span>

```console
No profile or providers specified, defaulting to trace profile 'cpu-sampling'

Provider Name                           Keywords            Level               Enabled By
Microsoft-DotNETCore-SampleProfiler     0x0000F00000000000  Informational(4)    --profile
Microsoft-Windows-DotNETRuntime         0x00000014C14FCCBD  Informational(4)    --profile

Process        : E:\temp\gcperfsim\bin\Debug\net5.0\gcperfsim.exe
Output File    : E:\temp\gcperfsim\trace.nettrace


[00:00:00:05]   Recording trace 122.244  (KB)
Press <Enter> or <Ctrl+C> to exit...
```

<span data-ttu-id="f6304-200">Para detener la recopilación del seguimiento, presione `<Enter>` o las teclas `<Ctrl + C>`.</span><span class="sxs-lookup"><span data-stu-id="f6304-200">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="f6304-201">Si lo hace, también saldrá de `hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="f6304-201">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="f6304-202">El inicio de `hello.exe` a través de dotnet-trace redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="f6304-202">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="f6304-203">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="f6304-203">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="f6304-204">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="f6304-204">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="f6304-205">Vista del seguimiento capturado de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="f6304-205">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="f6304-206">En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="f6304-206">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="f6304-207">En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="f6304-207">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="f6304-208">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="f6304-208">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="f6304-209">Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="f6304-209">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="f6304-210">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="f6304-210">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="f6304-211">El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="f6304-211">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="f6304-212">Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-212">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="f6304-213">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="f6304-213">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="f6304-214">Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="f6304-214">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="f6304-215">`dotnet-trace` puede:</span><span class="sxs-lookup"><span data-stu-id="f6304-215">`dotnet-trace` can:</span></span>

* <span data-ttu-id="f6304-216">Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="f6304-216">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="f6304-217">Por ejemplo, en producción.</span><span class="sxs-lookup"><span data-stu-id="f6304-217">For example, in production.</span></span>
* <span data-ttu-id="f6304-218">Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="f6304-218">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="f6304-219">Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="f6304-219">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="f6304-220">El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="f6304-220">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="f6304-221">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="f6304-221">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="f6304-222">El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:</span><span class="sxs-lookup"><span data-stu-id="f6304-222">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="f6304-223">El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="f6304-223">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="f6304-224">Proveedores .NET</span><span class="sxs-lookup"><span data-stu-id="f6304-224">.NET Providers</span></span>

<span data-ttu-id="f6304-225">El runtime de .NET Core admite los siguientes proveedores .NET.</span><span class="sxs-lookup"><span data-stu-id="f6304-225">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="f6304-226">.NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.</span><span class="sxs-lookup"><span data-stu-id="f6304-226">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="f6304-227">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="f6304-227">Provider name</span></span>                            | <span data-ttu-id="f6304-228">Información</span><span class="sxs-lookup"><span data-stu-id="f6304-228">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="f6304-229">El proveedor de runtime</span><span class="sxs-lookup"><span data-stu-id="f6304-229">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="f6304-230">Palabras clave de runtime de CLR</span><span class="sxs-lookup"><span data-stu-id="f6304-230">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="f6304-231">El proveedor de informe detallado</span><span class="sxs-lookup"><span data-stu-id="f6304-231">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="f6304-232">Palabras clave de informe detallado de CLR</span><span class="sxs-lookup"><span data-stu-id="f6304-232">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="f6304-233">Habilita el generador de perfiles de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="f6304-233">Enables the sample profiler.</span></span> |
