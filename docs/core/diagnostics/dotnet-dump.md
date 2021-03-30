---
title: 'Herramienta de diagnóstico dotnet-dump: CLI de .NET'
description: Obtenga información sobre cómo instalar y usar la herramienta dotnet-dump de la CLI para recopilar y analizar volcados de Windows y Linux sin ningún depurador nativo.
ms.date: 11/17/2020
ms.openlocfilehash: 6e9edbc8075691784028f3293750c92fe53d3782
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104874178"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="01286-103">Utilidad de recopilación y análisis de volcado de memoria (dotnet-dump)</span><span class="sxs-lookup"><span data-stu-id="01286-103">Dump collection and analysis utility (dotnet-dump)</span></span>

<span data-ttu-id="01286-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="01286-104">**This article applies to:** ✔️ .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="01286-105">`dotnet-dump` para macOS solo se admite con .NET 5.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="01286-105">`dotnet-dump` for macOS is only supported with .NET 5.0 and later versions.</span></span>

## <a name="install"></a><span data-ttu-id="01286-106">Instalar</span><span class="sxs-lookup"><span data-stu-id="01286-106">Install</span></span>

<span data-ttu-id="01286-107">Hay dos maneras de descargar e instalar `dotnet-dump`:</span><span class="sxs-lookup"><span data-stu-id="01286-107">There are two ways to download and install `dotnet-dump`:</span></span>

- <span data-ttu-id="01286-108">**Herramienta global dotnet:**</span><span class="sxs-lookup"><span data-stu-id="01286-108">**dotnet global tool:**</span></span>

  <span data-ttu-id="01286-109">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-dump) de `dotnet-dump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="01286-109">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

  ```dotnetcli
  dotnet tool install --global dotnet-dump
  ```

- <span data-ttu-id="01286-110">**Descarga directa:**</span><span class="sxs-lookup"><span data-stu-id="01286-110">**Direct download:**</span></span>

  <span data-ttu-id="01286-111">descargue el archivo ejecutable de la herramienta que coincida con la plataforma:</span><span class="sxs-lookup"><span data-stu-id="01286-111">Download the tool executable that matches your platform:</span></span>

  | <span data-ttu-id="01286-112">SO</span><span class="sxs-lookup"><span data-stu-id="01286-112">OS</span></span>  | <span data-ttu-id="01286-113">Plataforma</span><span class="sxs-lookup"><span data-stu-id="01286-113">Platform</span></span> |
  | --- | -------- |
  | <span data-ttu-id="01286-114">Windows</span><span class="sxs-lookup"><span data-stu-id="01286-114">Windows</span></span> | <span data-ttu-id="01286-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span><span class="sxs-lookup"><span data-stu-id="01286-115">[x86](https://aka.ms/dotnet-dump/win-x86) \| [x64](https://aka.ms/dotnet-dump/win-x64) \| [arm](https://aka.ms/dotnet-dump/win-arm) \| [arm-x64](https://aka.ms/dotnet-dump/win-arm64)</span></span> |
  | <span data-ttu-id="01286-116">macOS</span><span class="sxs-lookup"><span data-stu-id="01286-116">macOS</span></span>   | [<span data-ttu-id="01286-117">x64</span><span class="sxs-lookup"><span data-stu-id="01286-117">x64</span></span>](https://aka.ms/dotnet-dump/osx-x64) |
  | <span data-ttu-id="01286-118">Linux</span><span class="sxs-lookup"><span data-stu-id="01286-118">Linux</span></span>   | <span data-ttu-id="01286-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span><span class="sxs-lookup"><span data-stu-id="01286-119">[x64](https://aka.ms/dotnet-dump/linux-x64) \| [arm](https://aka.ms/dotnet-dump/linux-arm) \| [arm64](https://aka.ms/dotnet-dump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-dump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-dump/linux-musl-arm64)</span></span> |

> [!NOTE]
> <span data-ttu-id="01286-120">Para usar `dotnet-dump` en una aplicación x86, necesita la versión x86 correspondiente de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="01286-120">To use `dotnet-dump` on an x86 app, you need a corresponding x86 version of the tool.</span></span>

## <a name="synopsis"></a><span data-ttu-id="01286-121">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="01286-121">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="01286-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="01286-122">Description</span></span>

<span data-ttu-id="01286-123">La herramienta global `dotnet-dump` es una forma de recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo implicado, como `lldb` en Linux.</span><span class="sxs-lookup"><span data-stu-id="01286-123">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="01286-124">Esta herramienta es importante en plataformas como Alpine Linux, donde no está disponible una versión de `lldb` totalmente operativa.</span><span class="sxs-lookup"><span data-stu-id="01286-124">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="01286-125">La herramienta `dotnet-dump` permite ejecutar comandos SOS para analizar bloqueos y el recolector de elementos no utilizados (GC), pero no es un depurador nativo, por lo que no se admiten elementos como la visualización de marcos de pila nativos.</span><span class="sxs-lookup"><span data-stu-id="01286-125">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="01286-126">Opciones</span><span class="sxs-lookup"><span data-stu-id="01286-126">Options</span></span>

- **`--version`**

  <span data-ttu-id="01286-127">Muestra la versión de la utilidad dotnet-dump.</span><span class="sxs-lookup"><span data-stu-id="01286-127">Displays the version of the dotnet-dump utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="01286-128">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="01286-128">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="01286-129">Comandos</span><span class="sxs-lookup"><span data-stu-id="01286-129">Commands</span></span>

| <span data-ttu-id="01286-130">Comando</span><span class="sxs-lookup"><span data-stu-id="01286-130">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="01286-131">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="01286-131">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="01286-132">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="01286-132">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="01286-133">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="01286-133">dotnet-dump collect</span></span>

<span data-ttu-id="01286-134">Captura un volcado de un proceso.</span><span class="sxs-lookup"><span data-stu-id="01286-134">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="01286-135">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="01286-135">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [-n|--name] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="01286-136">Opciones</span><span class="sxs-lookup"><span data-stu-id="01286-136">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="01286-137">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="01286-137">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="01286-138">Especifica el número de id. de proceso del que se va a recopilar un volcado.</span><span class="sxs-lookup"><span data-stu-id="01286-138">Specifies the process ID number to collect a dump from.</span></span>

- **`-n|--name <name>`**

  <span data-ttu-id="01286-139">Especifica el nombre del proceso del que se va a recopilar un volcado.</span><span class="sxs-lookup"><span data-stu-id="01286-139">Specifies the name of the process to collect a dump from.</span></span>

- **`--type <Full|Heap|Mini>`**

  <span data-ttu-id="01286-140">Especifica el tipo de volcado, que determina los tipos de información que se recopilan del proceso.</span><span class="sxs-lookup"><span data-stu-id="01286-140">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="01286-141">Existen tres tipos:</span><span class="sxs-lookup"><span data-stu-id="01286-141">There are three types:</span></span>

  - <span data-ttu-id="01286-142">`Full`: el volcado más grande que contiene toda la memoria, incluidas las imágenes de los módulos.</span><span class="sxs-lookup"><span data-stu-id="01286-142">`Full` - The largest dump containing all memory including the module images.</span></span>
  - <span data-ttu-id="01286-143">`Heap`: un volcado grande y relativamente completo que contiene listas de módulos, listas de subprocesos, todas las pilas, información de excepción, información de control y toda la memoria excepto las imágenes asignadas.</span><span class="sxs-lookup"><span data-stu-id="01286-143">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="01286-144">`Mini`: un volcado pequeño que contiene listas de módulos, listas de subprocesos, información de excepción y todas las pilas.</span><span class="sxs-lookup"><span data-stu-id="01286-144">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="01286-145">Si no se especifica, el valor predeterminado es `Full`.</span><span class="sxs-lookup"><span data-stu-id="01286-145">If not specified, `Full` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="01286-146">La ruta de acceso completa y el nombre de archivo donde se debe escribir el volcado recopilado.</span><span class="sxs-lookup"><span data-stu-id="01286-146">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="01286-147">Si no se especifica:</span><span class="sxs-lookup"><span data-stu-id="01286-147">If not specified:</span></span>

  - <span data-ttu-id="01286-148">El valor predeterminado es *.\dump_AAAAMMDD_HHMMSS.dmp* en Windows.</span><span class="sxs-lookup"><span data-stu-id="01286-148">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="01286-149">El valor predeterminado es *./core_AAAAMMDD_HHMMSS* en Linux.</span><span class="sxs-lookup"><span data-stu-id="01286-149">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="01286-150">AAAAMMDD es año/mes/día y HHMMSS es hora/minuto/segundo.</span><span class="sxs-lookup"><span data-stu-id="01286-150">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="01286-151">Habilita el registro de diagnóstico de la recopilación de volcado.</span><span class="sxs-lookup"><span data-stu-id="01286-151">Enables dump collection diagnostic logging.</span></span>

> [!NOTE]
> <span data-ttu-id="01286-152">En Linux y macOS, este comando espera que la aplicación de destino y `dotnet-dump` compartan la misma variable de entorno `TMPDIR`.</span><span class="sxs-lookup"><span data-stu-id="01286-152">On Linux and macOS, this command expects the target application and `dotnet-dump` to share the same `TMPDIR` environment variable.</span></span> <span data-ttu-id="01286-153">De lo contrario, se agotará el tiempo de espera del comando.</span><span class="sxs-lookup"><span data-stu-id="01286-153">Otherwise, the command will time out.</span></span>

> [!NOTE]
> <span data-ttu-id="01286-154">Para recopilar un volcado mediante `dotnet-dump`, debe ejecutarse como el mismo usuario que el que ejecuta el proceso de destino, o bien como usuario raíz.</span><span class="sxs-lookup"><span data-stu-id="01286-154">To collect a dump using `dotnet-dump`, it needs to be run as the same user as the user running target process or as root.</span></span> <span data-ttu-id="01286-155">De lo contrario, la herramienta no podrá establecer una conexión con el proceso de destino.</span><span class="sxs-lookup"><span data-stu-id="01286-155">Otherwise, the tool will fail to establish a connection with the target process.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="01286-156">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="01286-156">dotnet-dump analyze</span></span>

<span data-ttu-id="01286-157">Inicia un shell interactivo para explorar un volcado.</span><span class="sxs-lookup"><span data-stu-id="01286-157">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="01286-158">El shell acepta varios [comandos SOS](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="01286-158">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="01286-159">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="01286-159">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="01286-160">Argumentos</span><span class="sxs-lookup"><span data-stu-id="01286-160">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="01286-161">Especifica la ruta de acceso al archivo de volcado que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="01286-161">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="01286-162">Opciones</span><span class="sxs-lookup"><span data-stu-id="01286-162">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="01286-163">Especifica el [comando](#analyze-sos-commands) que se va a ejecutar en el shell al inicio.</span><span class="sxs-lookup"><span data-stu-id="01286-163">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="01286-164">Análisis de comandos SOS</span><span class="sxs-lookup"><span data-stu-id="01286-164">Analyze SOS commands</span></span>

| <span data-ttu-id="01286-165">Comando</span><span class="sxs-lookup"><span data-stu-id="01286-165">Command</span></span>                             | <span data-ttu-id="01286-166">Función</span><span class="sxs-lookup"><span data-stu-id="01286-166">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="01286-167">Muestra todos los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="01286-167">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="01286-168">Muestra el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="01286-168">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="01286-169">Sale del modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="01286-169">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="01286-170">Proporciona un seguimiento de pila del código administrado únicamente.</span><span class="sxs-lookup"><span data-stu-id="01286-170">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="01286-171">Enumera los subprocesos administrados que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="01286-171">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="01286-172">Muestra información sobre las máquinas de estado asincrónicas en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="01286-172">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="01286-173">Muestra detalles sobre el ensamblado en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-173">Displays details about the assembly at the specified address.</span></span>                                 |
| `dumpclass <arguments>`             | <span data-ttu-id="01286-174">Muestra información sobre la estructura `EEClass` en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-174">Displays information about the `EEClass` structure at the specified address.</span></span>                  |
| `dumpdelegate <arguments>`          | <span data-ttu-id="01286-175">Muestra información sobre el delegado en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-175">Displays information about the delegate at the specified address.</span></span>                             |
| `dumpdomain <arguments>`            | <span data-ttu-id="01286-176">Muestra información sobre todos los dominios de aplicación y sobre todos los ensamblados en el dominio especificado.</span><span class="sxs-lookup"><span data-stu-id="01286-176">Displays information all the AppDomains and all assemblies within the specified domain.</span></span>       |
| `dumpheap <arguments>`              | <span data-ttu-id="01286-177">Muestra información sobre el montón de recolección de elementos no utilizados y estadísticas de recolección de los objetos.</span><span class="sxs-lookup"><span data-stu-id="01286-177">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="01286-178">Muestra el Lenguaje intermedio de Microsoft (MSIL) que está asociado a un método administrado.</span><span class="sxs-lookup"><span data-stu-id="01286-178">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="01286-179">Escribe el contenido de un registro de esfuerzo existente en memoria en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="01286-179">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="01286-180">Muestra información sobre la estructura `MethodDesc` en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-180">Displays information about the `MethodDesc` structure at the specified address.</span></span>               |
| `dumpmodule <arguments>`            | <span data-ttu-id="01286-181">Muestra información sobre el módulo en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-181">Displays information about the module at the specified address.</span></span>                               |
| `dumpmt <arguments>`                | <span data-ttu-id="01286-182">Muestra información sobre la estructura `MethodTable` en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-182">Displays information about the `MethodTable` at the specified address.</span></span>                        |
| `dumpobj <arguments>`               | <span data-ttu-id="01286-183">Muestra información sobre el objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-183">Displays info about the object at the specified address.</span></span>                                      |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="01286-184">Muestra todos los objetos administrados que se han encontrado dentro de los límites de la pila actual.</span><span class="sxs-lookup"><span data-stu-id="01286-184">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="01286-185">Muestra información sobre la memoria de proceso que usan las estructuras de datos internas del runtime.</span><span class="sxs-lookup"><span data-stu-id="01286-185">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="01286-186">Muestra todos los objetos registrados para su finalización.</span><span class="sxs-lookup"><span data-stu-id="01286-186">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="01286-187">Muestra información sobre las referencias (o raíces) al objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-187">Displays info about references (or roots) to the object at the specified address.</span></span>             |
| `gcwhere <arguments>`               | <span data-ttu-id="01286-188">Muestra la ubicación en el montón de recolección de elementos no utilizados del argumento que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="01286-188">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="01286-189">Muestra la estructura `MethodDesc` en la dirección especificada en código JIT.</span><span class="sxs-lookup"><span data-stu-id="01286-189">Displays the `MethodDesc` structure at the specified address in JIT code.</span></span>                     |
| `histclear <arguments>`             | <span data-ttu-id="01286-190">Libera los recursos usados por la familia de comandos `hist*`.</span><span class="sxs-lookup"><span data-stu-id="01286-190">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="01286-191">Inicializa las estructuras SOS del registro de esfuerzo guardado en el código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="01286-191">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="01286-192">Muestra las reubicaciones de registro de esfuerzo de la recolección de elementos no utilizados relacionadas con `<arguments>`.</span><span class="sxs-lookup"><span data-stu-id="01286-192">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="01286-193">Muestra todas las entradas de registro que hacen referencia al objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-193">Displays all the log entries that reference the object at the specified address.</span></span>              |
| `histroot <arguments>`              | <span data-ttu-id="01286-194">Muestra información relacionada con las promociones y las reubicaciones de la raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="01286-194">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="01286-195">Muestra los módulos nativos del proceso.</span><span class="sxs-lookup"><span data-stu-id="01286-195">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="01286-196">Muestra las estructuras `MethodTable` y `EEClass` para `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="01286-196">Displays the `MethodTable` and `EEClass` structures for the `<argument>`.</span></span>                     |
| `pe|printexception <arguments>`     | <span data-ttu-id="01286-197">Muestra cualquier objeto derivado de la clase <xref:System.Exception> para `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="01286-197">Displays any object derived from the <xref:System.Exception> class for the `<argument>`.</span></span>      |
| `setsymbolserver <arguments>`       | <span data-ttu-id="01286-198">Habilita la compatibilidad con el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="01286-198">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="01286-199">Muestra la información del contenedor de SyncBlock.</span><span class="sxs-lookup"><span data-stu-id="01286-199">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="01286-200">Establece o muestra el identificador del subproceso actual para los comandos SOS.</span><span class="sxs-lookup"><span data-stu-id="01286-200">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

> [!NOTE]
> <span data-ttu-id="01286-201">Puede encontrar más detalles en [Extensión de depuración de SOS para .NET](sos-debugging-extension.md).</span><span class="sxs-lookup"><span data-stu-id="01286-201">Additional details can be found in [SOS Debugging Extension for .NET](sos-debugging-extension.md).</span></span>

## <a name="using-dotnet-dump"></a><span data-ttu-id="01286-202">Uso de `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="01286-202">Using `dotnet-dump`</span></span>

<span data-ttu-id="01286-203">El primer paso es recopilar un volcado.</span><span class="sxs-lookup"><span data-stu-id="01286-203">The first step is to collect a dump.</span></span> <span data-ttu-id="01286-204">Este paso se puede omitir si ya se ha generado un volcado principal.</span><span class="sxs-lookup"><span data-stu-id="01286-204">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="01286-205">El sistema operativo o la [característica de generación de volcado](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/botr/xplat-minidump-generation.md) integrada del runtime de .NET Core pueden crear volcados principales.</span><span class="sxs-lookup"><span data-stu-id="01286-205">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/main/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="01286-206">Ahora analice el volcado principal con el comando `analyze`:</span><span class="sxs-lookup"><span data-stu-id="01286-206">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="01286-207">Esta acción abre una sesión interactiva que acepta comandos como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="01286-207">This action brings up an interactive session that accepts commands like:</span></span>

```console
> clrstack
OS Thread Id: 0x573d (0)
    Child SP               IP Call Site
00007FFD28B42C58 00007fb22c1a8ed9 [HelperMethodFrame_PROTECTOBJ: 00007ffd28b42c58] System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo) [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.Program.Foo4(System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.Program.Foo2(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.Program.Foo1(Int32, System.String) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.Program.Main(System.String[]) [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]
00007FFD28B43210 00007fb22aa9cedf [GCFrame: 00007ffd28b43210]
00007FFD28B43610 00007fb22aa9cedf [GCFrame: 00007ffd28b43610]
```

<span data-ttu-id="01286-208">Para ver una excepción no controlada que ha terminado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="01286-208">To see an unhandled exception that killed your app:</span></span>

```console
> pe -lines
Exception object: 00007fb18c038590
Exception type:   System.Reflection.TargetInvocationException
Message:          Exception has been thrown by the target of an invocation.
InnerException:   System.Exception, Use !PrintException 00007FB18C038368 to see more.
StackTrace (generated):
SP               IP               Function
00007FFD28B42DD0 0000000000000000 System.Private.CoreLib.dll!System.RuntimeMethodHandle.InvokeMethod(System.Object, System.Object[], System.Signature, Boolean, Boolean)
00007FFD28B42DD0 00007FB1B1334F67 System.Private.CoreLib.dll!System.Reflection.RuntimeMethodInfo.Invoke(System.Object, System.Reflection.BindingFlags, System.Reflection.Binder, System.Object[], System.Globalization.CultureInfo)+0xa7 [/root/coreclr/src/mscorlib/src/System/Reflection/RuntimeMethodInfo.cs @ 472]
00007FFD28B42E20 00007FB1B18D33ED SymbolTestApp.dll!SymbolTestApp.Program.Foo4(System.String)+0x15d [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 54]
00007FFD28B42ED0 00007FB1B18D2FC4 SymbolTestApp.dll!SymbolTestApp.Program.Foo2(Int32, System.String)+0x34 [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 29]
00007FFD28B42F00 00007FB1B18D2F5A SymbolTestApp.dll!SymbolTestApp.Program.Foo1(Int32, System.String)+0x3a [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 24]
00007FFD28B42F30 00007FB1B18D168E SymbolTestApp.dll!SymbolTestApp.Program.Main(System.String[])+0x6e [/home/mikem/builds/SymbolTestApp/SymbolTestApp/SymbolTestApp.cs @ 19]

StackTraceString: <none>
HResult: 80131604
```

## <a name="special-instructions-for-docker"></a><span data-ttu-id="01286-209">Instrucciones especiales para Docker</span><span class="sxs-lookup"><span data-stu-id="01286-209">Special instructions for Docker</span></span>

<span data-ttu-id="01286-210">Si ejecuta en Docker, la recopilación de volcados requiere capacidades de `SYS_PTRACE` (`--cap-add=SYS_PTRACE` o `--privileged`).</span><span class="sxs-lookup"><span data-stu-id="01286-210">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="01286-211">En Microsoft SDK de .NET Core imágenes de Docker de SDK de Linux, algunos comandos `dotnet-dump` pueden producir la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="01286-211">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="01286-212">Excepción no controlada: System.DllNotFoundException: No se puede cargar la biblioteca compartida "libdl.so" o una de su excepción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="01286-212">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="01286-213">Para solucionar este problema, instale el paquete "libc6-dev".</span><span class="sxs-lookup"><span data-stu-id="01286-213">To work around this problem, install the "libc6-dev" package.</span></span>

## <a name="see-also"></a><span data-ttu-id="01286-214">Vea también</span><span class="sxs-lookup"><span data-stu-id="01286-214">See also</span></span>

- [<span data-ttu-id="01286-215">Entrada de blog sobre la recopilación y el análisis de volcados de memoria</span><span class="sxs-lookup"><span data-stu-id="01286-215">Collecting and analyzing memory dumps blog</span></span>](https://devblogs.microsoft.com/dotnet/collecting-and-analyzing-memory-dumps/)
- [<span data-ttu-id="01286-216">Herramienta de análisis del montón (dotnet-gcdump)</span><span class="sxs-lookup"><span data-stu-id="01286-216">Heap analysis tool (dotnet-gcdump)</span></span>](dotnet-gcdump.md)
