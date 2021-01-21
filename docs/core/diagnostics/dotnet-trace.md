---
title: 'Herramienta de diagnóstico dotnet-trace: CLI de .NET'
description: Aprenda a instalar y usar la herramienta dotnet-trace de la CLI para recopilar seguimientos de .NET de un proceso en ejecución sin el generador de perfiles nativo, mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 93698882e94f58eda84abebc277e1eacfe22a3da
ms.sourcegitcommit: a4cecb7389f02c27e412b743f9189bd2a6dea4d6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2021
ms.locfileid: "98189710"
---
# <a name="dotnet-trace-performance-analysis-utility"></a><span data-ttu-id="1128e-103">Utilidad de análisis de rendimiento dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="1128e-103">dotnet-trace performance analysis utility</span></span>

<span data-ttu-id="1128e-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="1128e-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

## <a name="install"></a><span data-ttu-id="1128e-105">Instalar</span><span class="sxs-lookup"><span data-stu-id="1128e-105">Install</span></span>

<span data-ttu-id="1128e-106">Hay dos maneras de descargar e instalar `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="1128e-106">There are two ways to download and install `dotnet-trace`:</span></span>

- <span data-ttu-id="1128e-107">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="1128e-107">**dotnet global tool:**</span></span>

  <span data-ttu-id="1128e-108">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="1128e-108">To install the latest release version of the `dotnet-trace` [NuGet package](https://www.nuget.org/packages/dotnet-trace), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- <span data-ttu-id="1128e-109">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="1128e-109">**Direct download:**</span></span>

  <span data-ttu-id="1128e-110">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="1128e-110">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="1128e-111">SO</span><span class="sxs-lookup"><span data-stu-id="1128e-111">OS</span></span>  | <span data-ttu-id="1128e-112">Plataforma</span><span class="sxs-lookup"><span data-stu-id="1128e-112">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="1128e-113">Windows</span><span class="sxs-lookup"><span data-stu-id="1128e-113">Windows</span></span> | <span data-ttu-id="1128e-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="1128e-114">[x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64)</span></span> |
  | <span data-ttu-id="1128e-115">macOS</span><span class="sxs-lookup"><span data-stu-id="1128e-115">macOS</span></span>   | [<span data-ttu-id="1128e-116">x64</span><span class="sxs-lookup"><span data-stu-id="1128e-116">x64</span></span>](https://aka.ms/dotnet-trace/osx-x64) |
  | <span data-ttu-id="1128e-117">Linux</span><span class="sxs-lookup"><span data-stu-id="1128e-117">Linux</span></span>   | <span data-ttu-id="1128e-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="1128e-118">[x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="1128e-119">Para usar `dotnet-trace` en una aplicación x86, necesita la versión x86 correspondiente de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="1128e-119">To use `dotnet-trace` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="1128e-120">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="1128e-120">Synopsis</span></span>

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="1128e-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="1128e-121">Description</span></span>

<span data-ttu-id="1128e-122">La herramienta `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="1128e-122">The `dotnet-trace` tool:</span></span>

* <span data-ttu-id="1128e-123">Es una herramienta de .NET Core para varias plataformas.</span><span class="sxs-lookup"><span data-stu-id="1128e-123">Is a cross-platform .NET Core tool.</span></span>
* <span data-ttu-id="1128e-124">Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.</span><span class="sxs-lookup"><span data-stu-id="1128e-124">Enables the collection of .NET Core traces of a running process without a native profiler.</span></span>
* <span data-ttu-id="1128e-125">Se basa en [`EventPipe`](./eventpipe.md) del entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1128e-125">Is built on [`EventPipe`](./eventpipe.md) of the .NET Core runtime.</span></span>
* <span data-ttu-id="1128e-126">Ofrece la misma experiencia en Windows, Linux o macOS.</span><span class="sxs-lookup"><span data-stu-id="1128e-126">Delivers the same experience on Windows, Linux, or macOS.</span></span>

## <a name="options"></a><span data-ttu-id="1128e-127">Opciones</span><span class="sxs-lookup"><span data-stu-id="1128e-127">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="1128e-128">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="1128e-128">Shows command-line help.</span></span>

- **`--version`**

  <span data-ttu-id="1128e-129">Muestra la versión de la utilidad dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="1128e-129">Displays the version of the dotnet-trace utility.</span></span>

## <a name="commands"></a><span data-ttu-id="1128e-130">Comandos</span><span class="sxs-lookup"><span data-stu-id="1128e-130">Commands</span></span>

| <span data-ttu-id="1128e-131">Comando</span><span class="sxs-lookup"><span data-stu-id="1128e-131">Command</span></span>                                                   |
|-----------------------------------------------------------|
| [<span data-ttu-id="1128e-132">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="1128e-132">dotnet-trace collect</span></span>](#dotnet-trace-collect)             |
| [<span data-ttu-id="1128e-133">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="1128e-133">dotnet-trace convert</span></span>](#dotnet-trace-convert)             |
| [<span data-ttu-id="1128e-134">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="1128e-134">dotnet-trace ps</span></span>](#dotnet-trace-ps)                       |
| [<span data-ttu-id="1128e-135">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="1128e-135">dotnet-trace list-profiles</span></span>](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a><span data-ttu-id="1128e-136">dotnet-trace collect</span><span class="sxs-lookup"><span data-stu-id="1128e-136">dotnet-trace collect</span></span>

<span data-ttu-id="1128e-137">Recopila un seguimiento de diagnóstico de un proceso en ejecución.</span><span class="sxs-lookup"><span data-stu-id="1128e-137">Collects a diagnostic trace from a running process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1128e-138">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="1128e-138">Synopsis</span></span>

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>] [--diagnostic-port] [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a><span data-ttu-id="1128e-139">Opciones</span><span class="sxs-lookup"><span data-stu-id="1128e-139">Options</span></span>

- **`--buffersize <size>`**

  <span data-ttu-id="1128e-140">Establece el tamaño del búfer circular en memoria, en megabytes.</span><span class="sxs-lookup"><span data-stu-id="1128e-140">Sets the size of the in-memory circular buffer, in megabytes.</span></span> <span data-ttu-id="1128e-141">Valor predeterminado de 256 MB.</span><span class="sxs-lookup"><span data-stu-id="1128e-141">Default 256 MB.</span></span>

- **`--clreventlevel <clreventlevel>`**

  <span data-ttu-id="1128e-142">Nivel de detalle de los eventos CLR que se van a emitir.</span><span class="sxs-lookup"><span data-stu-id="1128e-142">Verbosity of CLR events to be emitted.</span></span>

- **`--clrevents <clrevents>`**

  <span data-ttu-id="1128e-143">Lista de palabras clave del proveedor del entorno de ejecución de CLR para habilitación separadas por signos `+`.</span><span class="sxs-lookup"><span data-stu-id="1128e-143">A list of CLR runtime provider keywords to enable separated by `+` signs.</span></span> <span data-ttu-id="1128e-144">Se trata de una asignación simple que le permite especificar palabras clave de eventos mediante alias de cadenas en lugar de sus valores hexadecimales.</span><span class="sxs-lookup"><span data-stu-id="1128e-144">This is a simple mapping that lets you specify event keywords via string aliases rather than their hex values.</span></span> <span data-ttu-id="1128e-145">Por ejemplo, `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` solicita el mismo conjunto de eventos que `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`.</span><span class="sxs-lookup"><span data-stu-id="1128e-145">For example, `dotnet-trace collect --providers Microsoft-Windows-DotNETRuntime:3:4` requests the same set of events as `dotnet-trace collect --clrevents gc+gchandle --clreventlevel informational`.</span></span> <span data-ttu-id="1128e-146">En la tabla siguiente, se muestra la lista de palabras clave disponibles:</span><span class="sxs-lookup"><span data-stu-id="1128e-146">The table below shows the list of available keywords:</span></span>

  | <span data-ttu-id="1128e-147">Alias de cadena de palabra clave</span><span class="sxs-lookup"><span data-stu-id="1128e-147">Keyword String Alias</span></span> | <span data-ttu-id="1128e-148">Valor hexadecimal de palabra clave</span><span class="sxs-lookup"><span data-stu-id="1128e-148">Keyword Hex Value</span></span> |
  | ------------ | ------------------- |
  | `gc` | `0x1` |
  | `gchandle` | `0x2` |
  | `fusion` | `0x4` |
  | `loader` | `0x8` |
  | `jit` | `0x10` |
  | `ngen` | `0x20` |
  | `startenumeration` | `0x40` |
  | `endenumeration` | `0x80` |
  | `security` | `0x400` |
  | `appdomainresourcemanagement` | `0x800` |
  | `jittracing` | `0x1000` |
  | `interop` | `0x2000` |
  | `contention` | `0x4000` |
  | `exception` | `0x8000` |
  | `threading` | `0x10000` |
  | `jittedmethodiltonativemap` | `0x20000` |
  | `overrideandsuppressngenevents` | `0x40000` |
  | `type` | `0x80000` |
  | `gcheapdump` | `0x100000` |
  | `gcsampledobjectallocationhigh` | `0x200000` |
  | `gcheapsurvivalandmovement` | `0x400000` |
  | `gcheapcollect` | `0x800000` |
  | `gcheapandtypenames` | `0x1000000` |
  | `gcsampledobjectallocationlow` | `0x2000000` |
  | `perftrack` | `0x20000000` |
  | `stack` | `0x40000000` |
  | `threadtransfer` | `0x80000000` |
  | `debugger` | `0x100000000` |
  | `monitoring` | `0x200000000` |
  | `codesymbols` | `0x400000000` |
  | `eventsource` | `0x800000000` |
  | `compilation` | `0x1000000000` |
  | `compilationdiagnostic` | `0x2000000000` |
  | `methoddiagnostic` | `0x4000000000` |
  | `typediagnostic` | `0x8000000000` |

  <span data-ttu-id="1128e-149">Puede obtener información más detallada sobre el proveedor de CLR en la [documentación de referencia del proveedor del entorno de ejecución de .NET](../../fundamentals/diagnostics/runtime-events.md).</span><span class="sxs-lookup"><span data-stu-id="1128e-149">You can read about the CLR provider more in detail on the [.NET runtime provider reference documentation](../../fundamentals/diagnostics/runtime-events.md).</span></span>

- **`--format {Chromium|NetTrace|Speedscope}`**

  <span data-ttu-id="1128e-150">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-150">Sets the output format for the trace file conversion.</span></span> <span data-ttu-id="1128e-151">De manera predeterminada, es `NetTrace`.</span><span class="sxs-lookup"><span data-stu-id="1128e-151">The default is `NetTrace`.</span></span>

- **`-n, --name <name>`**

  <span data-ttu-id="1128e-152">Nombre del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-152">The name of the process to collect the trace from.</span></span>

- **`--diagnostic-port <path-to-port>`**

  <span data-ttu-id="1128e-153">Nombre del puerto de diagnóstico que se va a crear.</span><span class="sxs-lookup"><span data-stu-id="1128e-153">The name of the diagnostic port to create.</span></span> <span data-ttu-id="1128e-154">Vea [Uso del puerto de diagnóstico para recopilar un seguimiento desde el inicio de la aplicación](#use-diagnostic-port-to-collect-a-trace-from-app-startup) para obtener información sobre cómo usar esta opción para recopilar un seguimiento desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1128e-154">See [Use diagnostic port to collect a trace from app startup](#use-diagnostic-port-to-collect-a-trace-from-app-startup) to learn how to use this option to collect a trace from app startup.</span></span>

- **`-o|--output <trace-file-path>`**

  <span data-ttu-id="1128e-155">Ruta de acceso de salida para los datos de seguimiento recopilados.</span><span class="sxs-lookup"><span data-stu-id="1128e-155">The output path for the collected trace data.</span></span> <span data-ttu-id="1128e-156">Si no se especifica, el valor predeterminado es `trace.nettrace`.</span><span class="sxs-lookup"><span data-stu-id="1128e-156">If not specified, it defaults to `trace.nettrace`.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="1128e-157">Identificador del proceso del que se va a recopilar el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-157">The process ID to collect the trace from.</span></span>

- **`--profile <profile-name>`**

  <span data-ttu-id="1128e-158">Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.</span><span class="sxs-lookup"><span data-stu-id="1128e-158">A named pre-defined set of provider configurations that allows common tracing scenarios to be specified succinctly.</span></span> <span data-ttu-id="1128e-159">Hay disponibles los perfiles siguientes:</span><span class="sxs-lookup"><span data-stu-id="1128e-159">The following profiles are available:</span></span>

 | <span data-ttu-id="1128e-160">Perfil</span><span class="sxs-lookup"><span data-stu-id="1128e-160">Profile</span></span> | <span data-ttu-id="1128e-161">Descripción</span><span class="sxs-lookup"><span data-stu-id="1128e-161">Description</span></span> |
 |---------|-------------|
 |`cpu-sampling`|<span data-ttu-id="1128e-162">Resulta útil para realizar el seguimiento del uso de CPU y la información general del entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="1128e-162">Useful for tracking CPU usage and general .NET runtime information.</span></span> <span data-ttu-id="1128e-163">Esta es la opción predeterminada si no se especifica ningún perfil o proveedor.</span><span class="sxs-lookup"><span data-stu-id="1128e-163">This is the default option if no profile or providers are specified.</span></span>|
 |`gc-verbose`|<span data-ttu-id="1128e-164">Realiza un seguimiento de las recolecciones de elementos no utilizados y las asignaciones de objetos de ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1128e-164">Tracks GC collections and samples object allocations.</span></span>|
 |`gc-collect`|<span data-ttu-id="1128e-165">Realiza un seguimiento de las recolecciones de elementos no utilizados solo con una sobrecarga muy baja.</span><span class="sxs-lookup"><span data-stu-id="1128e-165">Tracks GC collections only at very low overhead.</span></span>|

- **`--providers <list-of-comma-separated-providers>`**

  <span data-ttu-id="1128e-166">Lista separada por comas de proveedores de `EventPipe` que se van a habilitar.</span><span class="sxs-lookup"><span data-stu-id="1128e-166">A comma-separated list of `EventPipe` providers to be enabled.</span></span> <span data-ttu-id="1128e-167">Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`.</span><span class="sxs-lookup"><span data-stu-id="1128e-167">These providers supplement any providers implied by `--profile <profile-name>`.</span></span> <span data-ttu-id="1128e-168">Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.</span><span class="sxs-lookup"><span data-stu-id="1128e-168">If there's any inconsistency for a particular provider, this configuration takes precedence over the implicit configuration from the profile.</span></span>

  <span data-ttu-id="1128e-169">Esta lista de proveedores tiene el siguiente formato:</span><span class="sxs-lookup"><span data-stu-id="1128e-169">This list of providers is in the form:</span></span>

  - `Provider[,Provider]`
  - <span data-ttu-id="1128e-170">`Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span><span class="sxs-lookup"><span data-stu-id="1128e-170">`Provider` is in the form: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.</span></span>
  - <span data-ttu-id="1128e-171">`KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.</span><span class="sxs-lookup"><span data-stu-id="1128e-171">`KeyValueArgs` is in the form: `[key1=value1][;key2=value2]`.</span></span>

- <span data-ttu-id="1128e-172">**`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0)**</span><span class="sxs-lookup"><span data-stu-id="1128e-172">**`-- <command>` (for target applications running .NET 5.0 only)**</span></span>

  <span data-ttu-id="1128e-173">Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo.</span><span class="sxs-lookup"><span data-stu-id="1128e-173">After the collection configuration parameters, the user can append `--` followed by a command to start a .NET application with at least a 5.0 runtime.</span></span> <span data-ttu-id="1128e-174">Esto puede resultar útil al diagnosticar problemas que se producen al principio del proceso, como problemas de rendimiento de inicio o de cargador de ensamblados y errores del enlazador.</span><span class="sxs-lookup"><span data-stu-id="1128e-174">This may be helpful when diagnosing issues that happen early in the process, such as startup performance issue or assembly loader and binder errors.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1128e-175">El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera.</span><span class="sxs-lookup"><span data-stu-id="1128e-175">Using this option monitors the first .NET 5.0 process that communicates back to the tool, which means if your command launches multiple .NET applications, it will only collect the first app.</span></span> <span data-ttu-id="1128e-176">Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.</span><span class="sxs-lookup"><span data-stu-id="1128e-176">Therefore, it is recommended you use this option on self-contained applications, or using the `dotnet exec <app.dll>` option.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-177">En aplicaciones de gran tamaño, detener el seguimiento puede tardar mucho tiempo (hasta minutos).</span><span class="sxs-lookup"><span data-stu-id="1128e-177">Stopping the trace may take a long time (up to minutes) for large applications.</span></span> <span data-ttu-id="1128e-178">El entorno de ejecución debe enviar a través de la memoria caché de tipos todo el código administrado que se capturó en el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-178">The runtime needs to send over the type cache for all managed code that was captured in the trace.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-179">En Linux y macOS, este comando espera que la aplicación de destino y `dotnet-trace` compartan la misma variable de entorno `TMPDIR`.</span><span class="sxs-lookup"><span data-stu-id="1128e-179">On Linux and macOS, this command expects the target application and `dotnet-trace` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="1128e-180">De lo contrario, se agotará el tiempo de espera del comando.</span><span class="sxs-lookup"><span data-stu-id="1128e-180">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-181">Para recopilar un seguimiento mediante `dotnet-trace`, debe ejecutarse como el mismo usuario que el que ejecuta el proceso de destino, o bien como usuario raíz.</span><span class="sxs-lookup"><span data-stu-id="1128e-181">To collect a trace using `dotnet-trace`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="1128e-182">De lo contrario, la herramienta no podrá establecer una conexión con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="1128e-182">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

## <a name="dotnet-trace-convert"></a><span data-ttu-id="1128e-183">dotnet-trace convert</span><span class="sxs-lookup"><span data-stu-id="1128e-183">dotnet-trace convert</span></span>

<span data-ttu-id="1128e-184">Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.</span><span class="sxs-lookup"><span data-stu-id="1128e-184">Converts `nettrace` traces to alternate formats for use with alternate trace analysis tools.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1128e-185">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="1128e-185">Synopsis</span></span>

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a><span data-ttu-id="1128e-186">Argumentos</span><span class="sxs-lookup"><span data-stu-id="1128e-186">Arguments</span></span>

- **`<input-filename>`**

  <span data-ttu-id="1128e-187">Archivo de seguimiento de entrada que se va a convertir.</span><span class="sxs-lookup"><span data-stu-id="1128e-187">Input trace file to be converted.</span></span> <span data-ttu-id="1128e-188">El valor predeterminado es *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="1128e-188">Defaults to *trace.nettrace*.</span></span>

### <a name="options"></a><span data-ttu-id="1128e-189">Opciones</span><span class="sxs-lookup"><span data-stu-id="1128e-189">Options</span></span>

- **`--format <Chromium|NetTrace|Speedscope>`**

  <span data-ttu-id="1128e-190">Establece el formato de salida para la conversión del archivo de seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-190">Sets the output format for the trace file conversion.</span></span>

- **`-o|--output <output-filename>`**

  <span data-ttu-id="1128e-191">Nombre de archivo de salida.</span><span class="sxs-lookup"><span data-stu-id="1128e-191">Output filename.</span></span> <span data-ttu-id="1128e-192">Se agregará la extensión del formato de destino.</span><span class="sxs-lookup"><span data-stu-id="1128e-192">Extension of target format will be added.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-193">La conversión de archivos `nettrace` en archivos `chromium` o `speedscope` es irreversible.</span><span class="sxs-lookup"><span data-stu-id="1128e-193">Converting `nettrace` files to `chromium` or `speedscope` files is irreversible.</span></span> <span data-ttu-id="1128e-194">Los archivos `speedscope` y `chromium` no tienen toda la información necesaria para reconstruir los archivos `nettrace`,</span><span class="sxs-lookup"><span data-stu-id="1128e-194">`speedscope` and `chromium` files don't have all the information necessary to reconstruct `nettrace` files.</span></span> <span data-ttu-id="1128e-195">pero el comando `convert` conserva el archivo `nettrace` original, por lo que no debe eliminar este archivo si tiene previsto abrirlo en el futuro.</span><span class="sxs-lookup"><span data-stu-id="1128e-195">However, the `convert` command preserves the original `nettrace` file, so don't delete this file if you plan to open it in the future.</span></span>

## <a name="dotnet-trace-ps"></a><span data-ttu-id="1128e-196">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="1128e-196">dotnet-trace ps</span></span>

 <span data-ttu-id="1128e-197">Enumera los procesos de dotnet de los que se pueden recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="1128e-197">Lists the dotnet processes that traces can be collected from.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1128e-198">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="1128e-198">Synopsis</span></span>

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a><span data-ttu-id="1128e-199">dotnet-trace list-profiles</span><span class="sxs-lookup"><span data-stu-id="1128e-199">dotnet-trace list-profiles</span></span>

<span data-ttu-id="1128e-200">Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.</span><span class="sxs-lookup"><span data-stu-id="1128e-200">Lists pre-built tracing profiles with a description of what providers and filters are in each profile.</span></span>

### <a name="synopsis"></a><span data-ttu-id="1128e-201">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="1128e-201">Synopsis</span></span>

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a><span data-ttu-id="1128e-202">Recopilación de un seguimiento con dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="1128e-202">Collect a trace with dotnet-trace</span></span>

<span data-ttu-id="1128e-203">Para recopilar seguimientos mediante `dotnet-trace`:</span><span class="sxs-lookup"><span data-stu-id="1128e-203">To collect traces using `dotnet-trace`:</span></span>

- <span data-ttu-id="1128e-204">Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.</span><span class="sxs-lookup"><span data-stu-id="1128e-204">Get the process identifier (PID) of the .NET Core application to collect traces from.</span></span>

  - <span data-ttu-id="1128e-205">En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="1128e-205">On Windows, you can use Task Manager or the `tasklist` command, for example.</span></span>
  - <span data-ttu-id="1128e-206">En Linux, por ejemplo, el comando `ps`.</span><span class="sxs-lookup"><span data-stu-id="1128e-206">On Linux, for example, the `ps` command.</span></span>
  - [<span data-ttu-id="1128e-207">dotnet-trace ps</span><span class="sxs-lookup"><span data-stu-id="1128e-207">dotnet-trace ps</span></span>](#dotnet-trace-ps)

- <span data-ttu-id="1128e-208">Ejecute el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1128e-208">Run the following command:</span></span>

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  <span data-ttu-id="1128e-209">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1128e-209">The preceding command generates output similar to the following:</span></span>

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- <span data-ttu-id="1128e-210">Detenga la recolección presionando la tecla `<Enter>`.</span><span class="sxs-lookup"><span data-stu-id="1128e-210">Stop collection by pressing the `<Enter>` key.</span></span> <span data-ttu-id="1128e-211">`dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.</span><span class="sxs-lookup"><span data-stu-id="1128e-211">`dotnet-trace` will finish logging events to the *trace.nettrace* file.</span></span>

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a><span data-ttu-id="1128e-212">Inicio de una aplicación secundaria y recopilación de un seguimiento de su inicio mediante dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="1128e-212">Launch a child application and collect a trace from its startup using dotnet-trace</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1128e-213">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="1128e-213">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="1128e-214">A veces puede resultar útil recopilar un seguimiento de un proceso desde su inicio.</span><span class="sxs-lookup"><span data-stu-id="1128e-214">Sometimes it may be useful to collect a trace of a process from its startup.</span></span> <span data-ttu-id="1128e-215">En el caso de las aplicaciones que ejecutan .NET 5.0 o versiones posteriores, es posible hacerlo mediante dotnet-trace.</span><span class="sxs-lookup"><span data-stu-id="1128e-215">For apps running .NET 5.0 or later, it is possible to do this by using dotnet-trace.</span></span>

<span data-ttu-id="1128e-216">Esto iniciará `hello.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y recopilará un seguimiento de su inicio en tiempo de ejecución:</span><span class="sxs-lookup"><span data-stu-id="1128e-216">This will launch `hello.exe` with `arg1` and `arg2` as its command-line arguments and collect a trace from its runtime startup:</span></span>

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

<span data-ttu-id="1128e-217">El comando anterior genera una salida similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="1128e-217">The preceding command generates output similar to the following:</span></span>

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

<span data-ttu-id="1128e-218">Para detener la recopilación del seguimiento, presione `<Enter>` o las teclas `<Ctrl + C>`.</span><span class="sxs-lookup"><span data-stu-id="1128e-218">You can stop collecting the trace by pressing `<Enter>` or `<Ctrl + C>` key.</span></span> <span data-ttu-id="1128e-219">Si lo hace, también saldrá de `hello.exe`.</span><span class="sxs-lookup"><span data-stu-id="1128e-219">Doing this will also exit `hello.exe`.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-220">El inicio de `hello.exe` a través de dotnet-trace redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.</span><span class="sxs-lookup"><span data-stu-id="1128e-220">Launching `hello.exe` via dotnet-trace will make its input/output to be redirected and you won't be able to interact with its stdin/stdout.</span></span>
> <span data-ttu-id="1128e-221">La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.</span><span class="sxs-lookup"><span data-stu-id="1128e-221">Exiting the tool via CTRL+C or SIGTERM will safely end both the tool and the child process.</span></span>
> <span data-ttu-id="1128e-222">Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.</span><span class="sxs-lookup"><span data-stu-id="1128e-222">If the child process exits before the tool, the tool will exit as well and the trace should be safely viewable.</span></span>

## <a name="use-diagnostic-port-to-collect-a-trace-from-app-startup"></a><span data-ttu-id="1128e-223">Uso del puerto de diagnóstico para recopilar un seguimiento desde el inicio de la aplicación</span><span class="sxs-lookup"><span data-stu-id="1128e-223">Use diagnostic port to collect a trace from app startup</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1128e-224">Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="1128e-224">This works for apps running .NET 5.0 or later only.</span></span>

<span data-ttu-id="1128e-225">El puerto de diagnóstico es una característica nueva del entorno de ejecución que se ha agregado en .NET 5 y permite realizar un seguimiento desde el inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1128e-225">Diagnostic port is a new runtime feature that was added in .NET 5 that allows you to start tracing from app startup.</span></span> <span data-ttu-id="1128e-226">Para hacer esto con `dotnet-trace`, puede usar `dotnet-trace collect -- <command>`, tal como se describe en los ejemplos anteriores, o bien la opción `--diagnostic-port`.</span><span class="sxs-lookup"><span data-stu-id="1128e-226">To do this using `dotnet-trace`, you can either use `dotnet-trace collect -- <command>` as described in the examples above, or use the `--diagnostic-port` option.</span></span>

<span data-ttu-id="1128e-227">El uso de `dotnet-trace <collect|monitor> -- <command>` para iniciar la aplicación como un proceso secundario es la manera más sencilla de realizar un seguimiento rápido desde el inicio.</span><span class="sxs-lookup"><span data-stu-id="1128e-227">Using `dotnet-trace <collect|monitor> -- <command>` to launch the application as a child process is the simplest way to quickly trace it from its startup.</span></span>

<span data-ttu-id="1128e-228">Sin embargo, si quiere obtener un control más preciso sobre la vigencia de la aplicación de la que se realiza el seguimiento (por ejemplo, supervisar la aplicación solo durante los primeros 10 minutos y continuar la ejecución), o si necesita interactuar con la aplicación mediante la CLI, el uso de la opción `--diagnostic-port` le permite controlar la aplicación de destino que se supervisa y `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="1128e-228">However, when you want to gain a finer control over the lifetime of the app being traced (for example, monitor the app for the first 10 minutes only and continue executing) or if you need to interact with the app using the CLI, using `--diagnostic-port` option allows you to control both the target app being monitored and `dotnet-trace`.</span></span>

1. <span data-ttu-id="1128e-229">El comando siguiente hace que `dotnet-trace` cree un socket de diagnóstico denominado `myport.sock` y que espere a una conexión.</span><span class="sxs-lookup"><span data-stu-id="1128e-229">The command below makes `dotnet-trace` create a diagnostics socket named `myport.sock` and wait for a connection.</span></span>

    > ```dotnet-cli
    > dotnet-trace collect --diagnostic-port myport.sock
    > ```

    <span data-ttu-id="1128e-230">Salida:</span><span class="sxs-lookup"><span data-stu-id="1128e-230">Output:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ```

2. <span data-ttu-id="1128e-231">En una consola independiente, inicie la aplicación de destino con la variable de entorno `DOTNET_DiagnosticPorts` establecida en el valor de la salida de `dotnet-trace`.</span><span class="sxs-lookup"><span data-stu-id="1128e-231">In a separate console, launch the target application with the environment variable `DOTNET_DiagnosticPorts` set to the value in the `dotnet-trace` output.</span></span>

    > ```bash
    > export DOTNET_DiagnosticPorts=/home/user/myport.sock
    > ./my-dotnet-app arg1 arg2
    > ```

    <span data-ttu-id="1128e-232">Esto debe habilitar `dotnet-trace` para iniciar el seguimiento de `my-dotnet-app`:</span><span class="sxs-lookup"><span data-stu-id="1128e-232">This should then enable `dotnet-trace` to start tracing `my-dotnet-app`:</span></span>

    > ```bash
    > Waiting for connection on myport.sock
    > Start an application with the following environment variable: DOTNET_DiagnosticPorts=myport.sock
    > Starting a counter session. Press Q to quit.
    > ```

    > [!IMPORTANT]
    > <span data-ttu-id="1128e-233">Iniciar la aplicación con `dotnet run` puede resultar problemático porque la CLI de dotnet puede generar muchos procesos secundarios que no sean la aplicación. Además, dichos procesos secundarios pueden conectarse a `dotnet-trace` antes que la aplicación, lo que causa que esta se suspenda en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1128e-233">Launching your app with `dotnet run` can be problematic because the dotnet CLI may spawn many child processes that are not your app and they can connect to `dotnet-trace` before your app, leaving your app to be suspended at runtime.</span></span> <span data-ttu-id="1128e-234">Se recomienda usar directamente una versión independiente de la aplicación o `dotnet exec` para iniciar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="1128e-234">It is recommended you directly use a self-contained version of the app or use `dotnet exec` to launch the application.</span></span>

## <a name="view-the-trace-captured-from-dotnet-trace"></a><span data-ttu-id="1128e-235">Vista del seguimiento capturado de dotnet-trace</span><span class="sxs-lookup"><span data-stu-id="1128e-235">View the trace captured from dotnet-trace</span></span>

<span data-ttu-id="1128e-236">En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.</span><span class="sxs-lookup"><span data-stu-id="1128e-236">On Windows, *.nettrace* files can be viewed on [PerfView](https://github.com/microsoft/perfview) for analysis: For traces collected on other platforms, the trace file can be moved to a Windows machine to be viewed on PerfView.</span></span>

<span data-ttu-id="1128e-237">En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="1128e-237">On Linux, the trace can be viewed by changing the output format of `dotnet-trace` to `speedscope`.</span></span> <span data-ttu-id="1128e-238">Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="1128e-238">The output file format can be changed using the `-f|--format` option - `-f speedscope` will make `dotnet-trace` produce a `speedscope` file.</span></span> <span data-ttu-id="1128e-239">Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`.</span><span class="sxs-lookup"><span data-stu-id="1128e-239">You can choose between `nettrace` (the default option) and `speedscope`.</span></span> <span data-ttu-id="1128e-240">Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.</span><span class="sxs-lookup"><span data-stu-id="1128e-240">`Speedscope` files can be opened at <https://www.speedscope.app>.</span></span>

> [!NOTE]
> <span data-ttu-id="1128e-241">El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`.</span><span class="sxs-lookup"><span data-stu-id="1128e-241">The .NET Core runtime generates traces in the `nettrace` format.</span></span> <span data-ttu-id="1128e-242">Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-242">The traces are converted to speedscope (if specified) after the trace is completed.</span></span> <span data-ttu-id="1128e-243">Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.</span><span class="sxs-lookup"><span data-stu-id="1128e-243">Since some conversions may result in loss of data, the original `nettrace` file is preserved next to the converted file.</span></span>

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a><span data-ttu-id="1128e-244">Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo</span><span class="sxs-lookup"><span data-stu-id="1128e-244">Use dotnet-trace to collect counter values over time</span></span>

<span data-ttu-id="1128e-245">`dotnet-trace` puede:</span><span class="sxs-lookup"><span data-stu-id="1128e-245">`dotnet-trace` can:</span></span>

* <span data-ttu-id="1128e-246">Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento.</span><span class="sxs-lookup"><span data-stu-id="1128e-246">Use `EventCounter` for basic health monitoring in performance-sensitive environments.</span></span> <span data-ttu-id="1128e-247">Por ejemplo, en producción.</span><span class="sxs-lookup"><span data-stu-id="1128e-247">For example, in production.</span></span>
* <span data-ttu-id="1128e-248">Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.</span><span class="sxs-lookup"><span data-stu-id="1128e-248">Collect traces so they don't need to be viewed in real time.</span></span>

<span data-ttu-id="1128e-249">Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:</span><span class="sxs-lookup"><span data-stu-id="1128e-249">For example, to collect runtime performance counter values, use the following command:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

<span data-ttu-id="1128e-250">El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado.</span><span class="sxs-lookup"><span data-stu-id="1128e-250">The preceding command tells the runtime counters to report once every second for lightweight health monitoring.</span></span> <span data-ttu-id="1128e-251">Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.</span><span class="sxs-lookup"><span data-stu-id="1128e-251">Replacing `EventCounterIntervalSec=1` with a higher value (for example, 60) allows collection of a smaller trace with less granularity in the counter data.</span></span>

<span data-ttu-id="1128e-252">El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:</span><span class="sxs-lookup"><span data-stu-id="1128e-252">The following command reduces overhead and trace size more than the preceding one:</span></span>

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

<span data-ttu-id="1128e-253">El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.</span><span class="sxs-lookup"><span data-stu-id="1128e-253">The preceding command disables runtime events and the managed stack profiler.</span></span>

## <a name="use-rsp-file-to-avoid-typing-long-commands"></a><span data-ttu-id="1128e-254">Uso del archivo. rsp para evitar escribir comandos largos</span><span class="sxs-lookup"><span data-stu-id="1128e-254">Use .rsp file to avoid typing long commands</span></span>

<span data-ttu-id="1128e-255">Puede iniciar `dotnet-trace` con un archivo `.rsp` que contenga los argumentos que se van a pasar.</span><span class="sxs-lookup"><span data-stu-id="1128e-255">You can launch `dotnet-trace` with an `.rsp` file that contains the arguments to pass.</span></span> <span data-ttu-id="1128e-256">Esto puede ser útil cuando se habilitan proveedores que esperan argumentos largos o cuando se usa un entorno de shell que quita caracteres.</span><span class="sxs-lookup"><span data-stu-id="1128e-256">This can be useful when enabling providers that expect lengthy arguments or when using a shell environment that strips characters.</span></span>

<span data-ttu-id="1128e-257">Por ejemplo, el proveedor siguiente puede resultar complicado de escribir cada vez que quiera realizar un seguimiento:</span><span class="sxs-lookup"><span data-stu-id="1128e-257">For example, the following provider can be cumbersome to type out each time you want to trace:</span></span>

```cmd
dotnet-trace collect --providers Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="1128e-258">Además, el ejemplo anterior contiene `"` como parte del argumento.</span><span class="sxs-lookup"><span data-stu-id="1128e-258">In addition, the previous example contains `"` as part of the argument.</span></span> <span data-ttu-id="1128e-259">Dado que cada shell manipula las comillas de forma diferente, podría experimentar varios problemas al usar diferentes shells.</span><span class="sxs-lookup"><span data-stu-id="1128e-259">Because quotes are not handled equally by each shell, you may experience various issues when using different shells.</span></span> <span data-ttu-id="1128e-260">Por ejemplo, el comando que se va a especificar en `zsh` es diferente del comando en `cmd`.</span><span class="sxs-lookup"><span data-stu-id="1128e-260">For example, the command to enter in `zsh` is different to the command in `cmd`.</span></span>

<span data-ttu-id="1128e-261">En lugar de escribirlo cada vez, puede guardar el siguiente texto en un archivo denominado `myprofile.rsp`.</span><span class="sxs-lookup"><span data-stu-id="1128e-261">Instead of typing this each time, you can save the following text into a file called `myprofile.rsp`.</span></span>

```txt
--providers
Microsoft-Diagnostics-DiagnosticSource:0x3:5:FilterAndPayloadSpecs="SqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandBefore@Activity1Start:-Command;Command.CommandText;ConnectionId;Operation;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nSqlClientDiagnosticListener/System.Data.SqlClient.WriteCommandAfter@Activity1Stop:\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuting@Activity2Start:-Command;Command.CommandText;ConnectionId;IsAsync;Command.Connection.ClientConnectionId;Command.Connection.ServerVersion;Command.CommandTimeout;Command.CommandType;Command.Connection.ConnectionString;Command.Connection.Database;Command.Connection.DataSource;Command.Connection.PacketSize\r\nMicrosoft.EntityFrameworkCore/Microsoft.EntityFrameworkCore.Database.Command.CommandExecuted@Activity2Stop:",OtherProvider,AnotherProvider
```

<span data-ttu-id="1128e-262">Cuando haya guardado `myprofile.rsp`, puede iniciar `dotnet-trace` con esta configuración con el siguiente comando:</span><span class="sxs-lookup"><span data-stu-id="1128e-262">Once you've saved `myprofile.rsp`, you can launch `dotnet-trace` with this configuration using the following command:</span></span>

```bash
dotnet-trace @myprofile.rsp
```

## <a name="see-also"></a><span data-ttu-id="1128e-263">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1128e-263">See also</span></span>

- [<span data-ttu-id="1128e-264">Proveedores de eventos conocidos en.NET</span><span class="sxs-lookup"><span data-stu-id="1128e-264">Well-known event providers from .NET</span></span>](well-known-event-providers.md)
