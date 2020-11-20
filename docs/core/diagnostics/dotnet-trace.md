---
title: 'La herramienta dotnet-trace: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: d4175ccad785b21f860044a4fd5d691624ec495e
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507233"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="d714b-103">Utilidad de análisis de rendimiento dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d714b-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="d714b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d714b-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install-dotnet-trace"></a><span data-ttu-id="d714b-105">Instalación de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d714b-105">Install dotnet-trace</span></span>

<span data-ttu-id="d714b-106">Instale el [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` con el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="d714b-106">Install `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace) with the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a><span data-ttu-id="d714b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d714b-107">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="d714b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d714b-108">Description</span></span>

<span data-ttu-id="d714b-109">La herramienta `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="d714b-109">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="d714b-110">Es una herramienta de .NET Core para varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="d714b-110">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="d714b-111">Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.</span><span class="sxs-lookup"><span data-stu-id="d714b-111">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="d714b-112">Se basa en la tecnología `EventPipe` multiplataforma del entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="d714b-112">Is built around the cross-platform `EventPipe` technology of the .NET Core runtime.</span></span>
* <span data-ttu-id="d714b-113">Ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="d714b-113">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="d714b-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="d714b-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="d714b-115">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d714b-115">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="d714b-116">Muestra la versión de la utilidad dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="d714b-116">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="d714b-117">Comandos</span><span class="sxs-lookup"><span data-stu-id="d714b-117">Commands</span></span>

| <span data-ttu-id="d714b-118">Comando</span><span class="sxs-lookup"><span data-stu-id="d714b-118">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="d714b-119">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="d714b-119">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="d714b-120">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="d714b-120">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="d714b-121">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d714b-121">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="d714b-122">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="d714b-122">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="d714b-123">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="d714b-123">dotnet-trace collect</span></span>

<span data-ttu-id="d714b-124">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="d714b-124">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d714b-125">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d714b-125">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="d714b-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="d714b-126">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="d714b-127">Establece el tamaño del búfer circular en memoria, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="d714b-127">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="d714b-128">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="d714b-128">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="d714b-129">Nivel de detalle de los eventos CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="d714b-129">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="d714b-130">Lista de eventos de tiempo de ejecución de CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="d714b-130">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="d714b-131">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-131">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="d714b-132">De manera predeterminada, es `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="d714b-132">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="d714b-133">Nombre del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-133">The name of the process to collect the trace from.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="d714b-134">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="d714b-134">The output path for the collected trace data.</span></span> <span data-ttu-id="d714b-135">Si no se especifica, el valor predeterminado es `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="d714b-135">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="d714b-136">Identificador del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-136">The process id to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="d714b-137">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="d714b-137">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span>

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="d714b-138">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="d714b-138">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="d714b-139">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="d714b-139">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="d714b-140">Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="d714b-140">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="d714b-141">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="d714b-141">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="d714b-142">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="d714b-142">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="d714b-143">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="d714b-143">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="d714b-144">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0)**</span><span class="sxs-lookup"><span data-stu-id="d714b-144">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="d714b-145">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="d714b-145">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="d714b-146">Esto puede resultar útil al diagnosticar problemas que se producen al principio del proceso, como problemas de rendimiento de inicio o de cargador de ensamblados y errores del enlazador.</span><span class="sxs-lookup"><span data-stu-id="d714b-146">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="d714b-147">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="d714b-147">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="d714b-148">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="d714b-148">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="d714b-149">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="d714b-149">dotnet-trace convert</span></span>

<span data-ttu-id="d714b-150">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="d714b-150">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d714b-151">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d714b-151">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="d714b-152">Argumentos</span><span class="sxs-lookup"><span data-stu-id="d714b-152">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="d714b-153">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="d714b-153">Input trace file to be converted.</span></span> <span data-ttu-id="d714b-154">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="d714b-154">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="d714b-155">Opciones</span><span class="sxs-lookup"><span data-stu-id="d714b-155">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="d714b-156">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-156">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="d714b-157">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="d714b-157">Output filename.</span></span> <span data-ttu-id="d714b-158">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="d714b-158">Extension of target format will be added.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="d714b-159">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d714b-159">dotnet-trace ps</span></span>

 <span data-ttu-id="d714b-160">Enumera los procesos de dotnet de los que se pueden recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="d714b-160">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d714b-161">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d714b-161">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="d714b-162">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="d714b-162">dotnet-trace list-profiles</span></span>

<span data-ttu-id="d714b-163">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="d714b-163">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="d714b-164">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d714b-164">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="d714b-165">Recopilación de un seguimiento con dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d714b-165">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="d714b-166">Para recopilar seguimientos mediante `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="d714b-166">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="d714b-167">Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="d714b-167">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="d714b-168">En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d714b-168">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="d714b-169">En Linux, por ejemplo, el comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="d714b-169">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="d714b-170">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="d714b-170">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="d714b-171">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="d714b-171">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="d714b-172">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d714b-172">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="d714b-173">Detenga la recolección presionando la tecla `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="d714b-173">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="d714b-174">`dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="d714b-174">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="d714b-175">Inicio de una aplicación secundaria y recopilación de un seguimiento de su inicio mediante dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d714b-175">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

<span data-ttu-id="d714b-176">NOTA: Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="d714b-176">NOTE: This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="d714b-177">A veces puede resultar útil recopilar un seguimiento de un proceso desde su inicio.</span><span class="sxs-lookup"><span data-stu-id="d714b-177">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="d714b-178">En el caso de las aplicaciones que ejecutan .NET 5.0 o versiones posteriores, es posible hacerlo mediante dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="d714b-178">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="d714b-179">Esto iniciará `hello.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y recopilará un seguimiento de su inicio en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="d714b-179">This will launch `hello.exe` with `arg1` and `arg2` as its command line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="d714b-180">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="d714b-180">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="d714b-181">Para detener la recopilación del seguimiento, presione `<Enter>` o las teclas `<Ctrl + C>`.</span><span class="sxs-lookup"><span data-stu-id="d714b-181">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="d714b-182">Si lo hace, también saldrá de `hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="d714b-182">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="d714b-183">El inicio de `hello.exe` a través de dotnet-trace redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="d714b-183">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="d714b-184">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="d714b-184">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="d714b-185">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="d714b-185">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="d714b-186">Vista del seguimiento capturado de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="d714b-186">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="d714b-187">En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="d714b-187">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="d714b-188">En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="d714b-188">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="d714b-189">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="d714b-189">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="d714b-190">Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="d714b-190">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="d714b-191">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="d714b-191">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="d714b-192">El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="d714b-192">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="d714b-193">Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-193">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="d714b-194">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="d714b-194">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="d714b-195">Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="d714b-195">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="d714b-196">`dotnet-trace` puede:</span><span class="sxs-lookup"><span data-stu-id="d714b-196">`dotnet-trace` can:</span></span>

* <span data-ttu-id="d714b-197">Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="d714b-197">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="d714b-198">Por ejemplo, en producción.</span><span class="sxs-lookup"><span data-stu-id="d714b-198">For example, in production.</span></span>
* <span data-ttu-id="d714b-199">Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="d714b-199">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="d714b-200">Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="d714b-200">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="d714b-201">El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="d714b-201">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="d714b-202">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="d714b-202">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="d714b-203">El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:</span><span class="sxs-lookup"><span data-stu-id="d714b-203">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="d714b-204">El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="d714b-204">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="net-providers"></a><span data-ttu-id="d714b-205">Proveedores .NET</span><span class="sxs-lookup"><span data-stu-id="d714b-205">.NET Providers</span></span>

<span data-ttu-id="d714b-206">El runtime de .NET Core admite los siguientes proveedores .NET.</span><span class="sxs-lookup"><span data-stu-id="d714b-206">The .NET Core runtime supports the following .NET providers.</span></span> <span data-ttu-id="d714b-207">.NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.</span><span class="sxs-lookup"><span data-stu-id="d714b-207">.NET Core uses the same keywords to enable both `Event Tracing for Windows (ETW)` and `EventPipe` traces.</span></span>

| <span data-ttu-id="d714b-208">Nombre del proveedor</span><span class="sxs-lookup"><span data-stu-id="d714b-208">Provider name</span></span>                            | <span data-ttu-id="d714b-209">Información</span><span class="sxs-lookup"><span data-stu-id="d714b-209">Information</span></span> |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [<span data-ttu-id="d714b-210">El proveedor de runtime</span><span class="sxs-lookup"><span data-stu-id="d714b-210">The Runtime Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[<span data-ttu-id="d714b-211">Palabras clave de runtime de CLR</span><span class="sxs-lookup"><span data-stu-id="d714b-211">CLR Runtime Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [<span data-ttu-id="d714b-212">El proveedor de informe detallado</span><span class="sxs-lookup"><span data-stu-id="d714b-212">The Rundown Provider</span></span>](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[<span data-ttu-id="d714b-213">Palabras clave de informe detallado de CLR</span><span class="sxs-lookup"><span data-stu-id="d714b-213">CLR Rundown Keywords</span></span>](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | <span data-ttu-id="d714b-214">Habilita el generador de perfiles de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="d714b-214">Enables the sample profiler.</span></span> |
