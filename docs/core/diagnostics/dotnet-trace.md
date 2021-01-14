---
title: 'Herramienta de diagnóstico dotnet-trace: CLI de .NET'
description: Aprenda a instalar y usar la herramienta dotnet-trace de la CLI para recopilar seguimientos de .NET de un proceso en ejecución sin el generador de perfiles nativo, mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: a3b5748cb2a6c2060971fbad0d81ade00dc83087
ms.sourcegitcommit: 35ca2255c6c86968eaef9e3a251c9739ce8e4288
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2020
ms.locfileid: "97753671"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="9bac2-103">Utilidad de análisis de rendimiento dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="9bac2-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="9bac2-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9bac2-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="9bac2-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="9bac2-105">Install</span></span>

<span data-ttu-id="9bac2-106">Hay dos maneras de descargar e instalar `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="9bac2-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="9bac2-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="9bac2-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="9bac2-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="9bac2-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="9bac2-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="9bac2-109">**Direct download:**</span></span>

  <span data-ttu-id="9bac2-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="9bac2-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="9bac2-111">SO</span><span class="sxs-lookup"><span data-stu-id="9bac2-111">OS</span></span>  | <span data-ttu-id="9bac2-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="9bac2-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="9bac2-113">Windows</span><span class="sxs-lookup"><span data-stu-id="9bac2-113">Windows</span></span> | <span data-ttu-id="9bac2-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="9bac2-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="9bac2-115">macOS</span><span class="sxs-lookup"><span data-stu-id="9bac2-115">macOS</span></span>   | [<span data-ttu-id="9bac2-116">x64</span><span class="sxs-lookup"><span data-stu-id="9bac2-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="9bac2-117">Linux</span><span class="sxs-lookup"><span data-stu-id="9bac2-117">Linux</span></span>   | <span data-ttu-id="9bac2-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="9bac2-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

## <a name="synopsis"></a><span data-ttu-id="9bac2-119">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9bac2-119">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="9bac2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bac2-120">Description</span></span>

<span data-ttu-id="9bac2-121">La herramienta `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="9bac2-121">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="9bac2-122">Es una herramienta de .NET Core para varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="9bac2-122">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="9bac2-123">Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.</span><span class="sxs-lookup"><span data-stu-id="9bac2-123">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="9bac2-124">Se basa en [`EventPipe`](./eventpipe.md) del entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="9bac2-124">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="9bac2-125">Ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="9bac2-125">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="9bac2-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="9bac2-126">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="9bac2-127">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="9bac2-127">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="9bac2-128">Muestra la versión de la utilidad dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="9bac2-128">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="9bac2-129">Comandos</span><span class="sxs-lookup"><span data-stu-id="9bac2-129">Commands</span></span>

| <span data-ttu-id="9bac2-130">Comando</span><span class="sxs-lookup"><span data-stu-id="9bac2-130">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="9bac2-131">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="9bac2-131">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="9bac2-132">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="9bac2-132">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="9bac2-133">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="9bac2-133">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="9bac2-134">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="9bac2-134">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="9bac2-135">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="9bac2-135">dotnet-trace collect</span></span>

<span data-ttu-id="9bac2-136">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bac2-136">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9bac2-137">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9bac2-137">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="9bac2-138">Opciones</span><span class="sxs-lookup"><span data-stu-id="9bac2-138">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="9bac2-139">Establece el tamaño del búfer circular en memoria, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="9bac2-139">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="9bac2-140">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="9bac2-140">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="9bac2-141">Nivel de detalle de los eventos CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="9bac2-141">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="9bac2-142">Lista de eventos de tiempo de ejecución de CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="9bac2-142">List of CLR runtime events to emit.</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="9bac2-143">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-143">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="9bac2-144">De manera predeterminada, es `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-144">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="9bac2-145">Nombre del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-145">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="9bac2-146">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="9bac2-146">The name of the diagnostic port to create.</span></span> <span data-ttu-id="9bac2-147">Vea [Uso del puerto de diagnóstico para recopilar un seguimiento desde el inicio de la aplicación](#use-diagnostic-port-to-collect-a-trace-from-app-startup) para obtener información sobre cómo usar esta opción para recopilar un seguimiento desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9bac2-147">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="9bac2-148">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="9bac2-148">The output path for the collected trace data.</span></span> <span data-ttu-id="9bac2-149">Si no se especifica, el valor predeterminado es `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-149">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="9bac2-150">Identificador del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-150">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="9bac2-151">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="9bac2-151">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="9bac2-152">Hay disponibles los perfiles siguientes:</span><span class="sxs-lookup"><span data-stu-id="9bac2-152">The following profiles are available:</span></span>

 | <span data-ttu-id="9bac2-153">Perfil</span><span class="sxs-lookup"><span data-stu-id="9bac2-153">Profile</span></span> | <span data-ttu-id="9bac2-154">Descripción</span><span class="sxs-lookup"><span data-stu-id="9bac2-154">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="9bac2-155">Resulta útil para realizar el seguimiento del uso de CPU y la información general del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="9bac2-155">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="9bac2-156">Esta es la opción predeterminada si no se especifica ningún perfil o proveedor.</span><span class="sxs-lookup"><span data-stu-id="9bac2-156">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="9bac2-157">Realiza un seguimiento de las recolecciones de elementos no utilizados y las asignaciones de objetos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9bac2-157">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="9bac2-158">Realiza un seguimiento de las recolecciones de elementos no utilizados solo con una sobrecarga muy baja.</span><span class="sxs-lookup"><span data-stu-id="9bac2-158">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="9bac2-159">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="9bac2-159">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="9bac2-160">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-160">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="9bac2-161">Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="9bac2-161">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="9bac2-162">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="9bac2-162">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="9bac2-163">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-163">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="9bac2-164">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-164">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="9bac2-165">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0)**</span><span class="sxs-lookup"><span data-stu-id="9bac2-165">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="9bac2-166">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="9bac2-166">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="9bac2-167">Esto puede resultar útil al diagnosticar problemas que se producen al principio del proceso, como problemas de rendimiento de inicio o de cargador de ensamblados y errores del enlazador.</span><span class="sxs-lookup"><span data-stu-id="9bac2-167">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="9bac2-168">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="9bac2-168">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="9bac2-169">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-169">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

> [!NOTE]
> <span data-ttu-id="9bac2-170">En aplicaciones de gran tamaño, detener el seguimiento puede tardar mucho tiempo (hasta minutos).</span><span class="sxs-lookup"><span data-stu-id="9bac2-170">Stopping the trace may take a long time (up to minutes) for large applications.</span></span> <span data-ttu-id="9bac2-171">El entorno de ejecución debe enviar a través de la memoria caché de tipos todo el código administrado que se capturó en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-171">The runtime needs to send over the type cache for all managed code that was captured in the trace.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="9bac2-172">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="9bac2-172">dotnet-trace convert</span></span>

<span data-ttu-id="9bac2-173">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="9bac2-173">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9bac2-174">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9bac2-174">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="9bac2-175">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9bac2-175">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="9bac2-176">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="9bac2-176">Input trace file to be converted.</span></span> <span data-ttu-id="9bac2-177">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="9bac2-177">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="9bac2-178">Opciones</span><span class="sxs-lookup"><span data-stu-id="9bac2-178">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="9bac2-179">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-179">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="9bac2-180">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="9bac2-180">Output filename.</span></span> <span data-ttu-id="9bac2-181">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="9bac2-181">Extension of target format will be added.</span></span>

> [!NOTE]
> <span data-ttu-id="9bac2-182">La conversión de archivos `nettrace` en archivos `chromium` o `speedscope` es irreversible.</span><span class="sxs-lookup"><span data-stu-id="9bac2-182">Converting `nettrace` files to `chromium` or `speedscope` files is irreversible.</span></span> <span data-ttu-id="9bac2-183">Los archivos `speedscope` y `chromium` no tienen toda la información necesaria para reconstruir los archivos `nettrace`,</span><span class="sxs-lookup"><span data-stu-id="9bac2-183">`speedscope` and `chromium` files don't have all the information necessary to reconstruct `nettrace` files.</span></span> <span data-ttu-id="9bac2-184">pero el comando `convert` conserva el archivo `nettrace` original, por lo que no debe eliminar este archivo si tiene previsto abrirlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="9bac2-184">However, the `convert` command preserves the original `nettrace` file, so don't delete this file if you plan to open it in the future.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="9bac2-185">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="9bac2-185">dotnet-trace ps</span></span>

 <span data-ttu-id="9bac2-186">Enumera los procesos de dotnet de los que se pueden recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="9bac2-186">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9bac2-187">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9bac2-187">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="9bac2-188">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="9bac2-188">dotnet-trace list-profiles</span></span>

<span data-ttu-id="9bac2-189">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="9bac2-189">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="9bac2-190">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9bac2-190">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="9bac2-191">Recopilación de un seguimiento con dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="9bac2-191">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="9bac2-192">Para recopilar seguimientos mediante `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="9bac2-192">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="9bac2-193">Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="9bac2-193">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="9bac2-194">En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="9bac2-194">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="9bac2-195">En Linux, por ejemplo, el comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-195">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="9bac2-196">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="9bac2-196">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="9bac2-197">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9bac2-197">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="9bac2-198">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bac2-198">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="9bac2-199">Detenga la recolección presionando la tecla `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-199">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="9bac2-200">`dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="9bac2-200">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="9bac2-201">Inicio de una aplicación secundaria y recopilación de un seguimiento de su inicio mediante dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="9bac2-201">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9bac2-202">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="9bac2-202">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="9bac2-203">A veces puede resultar útil recopilar un seguimiento de un proceso desde su inicio.</span><span class="sxs-lookup"><span data-stu-id="9bac2-203">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="9bac2-204">En el caso de las aplicaciones que ejecutan .NET 5.0 o versiones posteriores, es posible hacerlo mediante dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="9bac2-204">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="9bac2-205">Esto iniciará `hello.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y recopilará un seguimiento de su inicio en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="9bac2-205">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="9bac2-206">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bac2-206">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="9bac2-207">Para detener la recopilación del seguimiento, presione `<Enter>` o las teclas `<Ctrl + C>`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-207">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="9bac2-208">Si lo hace, también saldrá de `hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-208">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="9bac2-209">El inicio de `hello.exe` a través de dotnet-trace redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="9bac2-209">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="9bac2-210">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="9bac2-210">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="9bac2-211">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="9bac2-211">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="9bac2-212">Uso del puerto de diagnóstico para recopilar un seguimiento desde el inicio de la aplicación</span><span class="sxs-lookup"><span data-stu-id="9bac2-212">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="9bac2-213">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="9bac2-213">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="9bac2-214">El puerto de diagnóstico es una característica nueva del entorno de ejecución que se ha agregado en .NET 5 y permite realizar un seguimiento desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9bac2-214">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="9bac2-215">Para hacer esto con `dotnet-trace`, puede usar `dotnet-trace collect -- <command>`, tal como se describe en los ejemplos anteriores, o bien la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-215">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="9bac2-216">El uso de `dotnet-trace <collect|monitor> -- <command>` para iniciar la aplicación como un proceso secundario es la manera más sencilla de realizar un seguimiento rápido desde el inicio.</span><span class="sxs-lookup"><span data-stu-id="9bac2-216">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="9bac2-217">Sin embargo, si quiere obtener un control más preciso sobre la vigencia de la aplicación de la que se realiza el seguimiento (por ejemplo, supervisar la aplicación solo durante los primeros 10 minutos y continuar la ejecución), o si necesita interactuar con la aplicación mediante la CLI, el uso de la opción `--diagnostic-port` le permite controlar la aplicación de destino que se supervisa y `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-217">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="9bac2-218">El comando siguiente hace que `dotnet-trace` cree un socket de diagnóstico denominado `myport.sock` y que espere a una conexión.</span><span class="sxs-lookup"><span data-stu-id="9bac2-218">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="9bac2-219">Salida:</span><span class="sxs-lookup"><span data-stu-id="9bac2-219">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="9bac2-220">En una consola independiente, inicie la aplicación de destino con la variable de entorno `DOTNET_DiagnosticPorts` establecida en el valor de la salida de `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-220">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="9bac2-221">Esto debe habilitar `dotnet-trace` para iniciar el seguimiento de `my-dotnet-app`:</span><span class="sxs-lookup"><span data-stu-id="9bac2-221">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="9bac2-222">Iniciar la aplicación con `dotnet run` puede resultar problemático porque la CLI de dotnet puede generar muchos procesos secundarios que no sean la aplicación. Además, dichos procesos secundarios pueden conectarse a `dotnet-trace` antes que la aplicación, lo que causa que esta se suspenda en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9bac2-222">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="9bac2-223">Se recomienda usar directamente una versión independiente de la aplicación o `dotnet exec` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="9bac2-223">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="9bac2-224">Vista del seguimiento capturado de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="9bac2-224">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="9bac2-225">En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="9bac2-225">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="9bac2-226">En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-226">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="9bac2-227">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-227">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="9bac2-228">Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-228">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="9bac2-229">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="9bac2-229">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="9bac2-230">El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-230">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="9bac2-231">Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-231">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="9bac2-232">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="9bac2-232">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="9bac2-233">Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="9bac2-233">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="9bac2-234">`dotnet-trace` puede:</span><span class="sxs-lookup"><span data-stu-id="9bac2-234">`dotnet-trace` can:</span></span>

* <span data-ttu-id="9bac2-235">Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-235">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="9bac2-236">Por ejemplo, en producción.</span><span class="sxs-lookup"><span data-stu-id="9bac2-236">For example, in production.</span></span>
* <span data-ttu-id="9bac2-237">Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="9bac2-237">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="9bac2-238">Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="9bac2-238">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="9bac2-239">El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="9bac2-239">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="9bac2-240">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="9bac2-240">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="9bac2-241">El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:</span><span class="sxs-lookup"><span data-stu-id="9bac2-241">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="9bac2-242">El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="9bac2-242">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a><span data-ttu-id="9bac2-243">Uso del archivo. rsp para evitar escribir comandos largos</span><span class="sxs-lookup"><span data-stu-id="9bac2-243">Use .rsp file to avoid typing long commands</span></span>

<span data-ttu-id="9bac2-244">Puede iniciar `dotnet-trace` con un archivo `.rsp` que contenga los argumentos que se van a pasar.</span><span class="sxs-lookup"><span data-stu-id="9bac2-244">You can launch `dotnet-trace` with an `.rsp` file that contains the arguments to pass.</span></span> <span data-ttu-id="9bac2-245">Esto puede ser útil cuando se habilitan proveedores que esperan argumentos largos o cuando se usa un entorno de shell que quita caracteres.</span><span class="sxs-lookup"><span data-stu-id="9bac2-245">This can be useful when enabling providers that expect lengthy arguments or when using a shell environment that strips characters.</span></span>

<span data-ttu-id="9bac2-246">Por ejemplo, el proveedor siguiente puede resultar complicado de escribir cada vez que quiera realizar un seguimiento:</span><span class="sxs-lookup"><span data-stu-id="9bac2-246">For example, the following provider can be cumbersome to type out each time you want to trace:</span></span>

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="9bac2-247">Además, el ejemplo anterior contiene `"` como parte del argumento.</span><span class="sxs-lookup"><span data-stu-id="9bac2-247">In addition, the previous example contains `"` as part of the argument.</span></span> <span data-ttu-id="9bac2-248">Dado que cada shell manipula las comillas de forma diferente, podría experimentar varios problemas al usar diferentes shells.</span><span class="sxs-lookup"><span data-stu-id="9bac2-248">Because quotes are not handled equally by each shell, you may experience various issues when using different shells.</span></span> <span data-ttu-id="9bac2-249">Por ejemplo, el comando que se va a especificar en `zsh` es diferente del comando en `cmd`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-249">For example, the command to enter in `zsh` is different to the command in `cmd`.</span></span>

<span data-ttu-id="9bac2-250">En lugar de escribirlo cada vez, puede guardar el siguiente texto en un archivo denominado `myprofile.rsp`.</span><span class="sxs-lookup"><span data-stu-id="9bac2-250">Instead of typing this each time, you can save the following text into a file called `myprofile.rsp`.</span></span>

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="9bac2-251">Cuando haya guardado `myprofile.rsp`, puede iniciar `dotnet-trace` con esta configuración con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="9bac2-251">Once you've saved `myprofile.rsp`, you can launch `dotnet-trace` with this configuration using the following command:</span></span>

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a><span data-ttu-id="9bac2-252">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9bac2-252">See also</span></span>

- [<span data-ttu-id="9bac2-253">Proveedores de eventos conocidos en.NET</span><span class="sxs-lookup"><span data-stu-id="9bac2-253">Well-known event providers from .NET</span></span>](well-known-event-providers.md)
