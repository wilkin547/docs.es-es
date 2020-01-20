---
title: 'dotnet-dump: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-trace.
ms.date: 10/14/2019
ms.openlocfilehash: dcd5dd42620010c1a9b6dffd3365fc1b777c0eeb
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740781"
---
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a><span data-ttu-id="95c88-103">Utilidad de recopilación y análisis de volcado (`dotnet-dump`)</span><span class="sxs-lookup"><span data-stu-id="95c88-103">Dump collection and analysis utility (`dotnet-dump`)</span></span>

<span data-ttu-id="95c88-104">**Este artículo se aplica a: ✓** SDK de .NET Core 3.0.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="95c88-104">**This article applies to: ✓** .NET Core 3.0 SDK and later versions</span></span>

> [!NOTE]
> <span data-ttu-id="95c88-105">`dotnet-dump` no se admite en macOS.</span><span class="sxs-lookup"><span data-stu-id="95c88-105">`dotnet-dump` isn't supported on macOS.</span></span>

## <a name="installing-dotnet-dump"></a><span data-ttu-id="95c88-106">Instalación de `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="95c88-106">Installing `dotnet-dump`</span></span>

<span data-ttu-id="95c88-107">Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-dump) de `dotnet-dump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):</span><span class="sxs-lookup"><span data-stu-id="95c88-107">To install the latest release version of the `dotnet-dump` [NuGet package](https://www.nuget.org/packages/dotnet-dump), use the [dotnet tool install](../tools/dotnet-tool-install.md) command:</span></span>

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a><span data-ttu-id="95c88-108">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="95c88-108">Synopsis</span></span>

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a><span data-ttu-id="95c88-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="95c88-109">Description</span></span>

<span data-ttu-id="95c88-110">La herramienta global `dotnet-dump` es una forma de recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo implicado, como `lldb` en Linux.</span><span class="sxs-lookup"><span data-stu-id="95c88-110">The `dotnet-dump` global tool is a way to collect and analyze Windows and Linux dumps without any native debugger involved like `lldb` on Linux.</span></span> <span data-ttu-id="95c88-111">Esta herramienta es importante en plataformas como Alpine Linux, donde no está disponible una versión de `lldb` totalmente operativa.</span><span class="sxs-lookup"><span data-stu-id="95c88-111">This tool is important on platforms like Alpine Linux where a fully working `lldb` isn't available.</span></span> <span data-ttu-id="95c88-112">La herramienta `dotnet-dump` permite ejecutar comandos SOS para analizar bloqueos y el recolector de elementos no utilizados (GC), pero no es un depurador nativo, por lo que no se admiten elementos como la visualización de marcos de pila nativos.</span><span class="sxs-lookup"><span data-stu-id="95c88-112">The `dotnet-dump` tool allows you to run SOS commands to analyze crashes and the garbage collector (GC), but it isn't a native debugger so things like displaying native stack frames aren't supported.</span></span>

## <a name="options"></a><span data-ttu-id="95c88-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="95c88-113">Options</span></span>

- **`--version`**

  <span data-ttu-id="95c88-114">Muestra la versión de la utilidad dotnet-counters.</span><span class="sxs-lookup"><span data-stu-id="95c88-114">Displays the version of the dotnet-counters utility.</span></span>

- **`-h|--help`**

  <span data-ttu-id="95c88-115">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="95c88-115">Shows command-line help.</span></span>

## <a name="commands"></a><span data-ttu-id="95c88-116">Comandos</span><span class="sxs-lookup"><span data-stu-id="95c88-116">Commands</span></span>

| <span data-ttu-id="95c88-117">Comando</span><span class="sxs-lookup"><span data-stu-id="95c88-117">Command</span></span>                                     |
| ------------------------------------------- |
| [<span data-ttu-id="95c88-118">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="95c88-118">dotnet-dump collect</span></span>](#dotnet-dump-collect) |
| [<span data-ttu-id="95c88-119">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="95c88-119">dotnet-dump analyze</span></span>](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a><span data-ttu-id="95c88-120">dotnet-dump collect</span><span class="sxs-lookup"><span data-stu-id="95c88-120">dotnet-dump collect</span></span>

<span data-ttu-id="95c88-121">Captura un volcado de un proceso.</span><span class="sxs-lookup"><span data-stu-id="95c88-121">Captures a dump from a process.</span></span>

### <a name="synopsis"></a><span data-ttu-id="95c88-122">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="95c88-122">Synopsis</span></span>

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a><span data-ttu-id="95c88-123">Opciones</span><span class="sxs-lookup"><span data-stu-id="95c88-123">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="95c88-124">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="95c88-124">Shows command-line help.</span></span>

- **`-p|--process-id <PID>`**

  <span data-ttu-id="95c88-125">Especifica el número de id. de proceso del que se va a recopilar un volcado de memoria.</span><span class="sxs-lookup"><span data-stu-id="95c88-125">Specifies the process ID number to collect a memory dump from.</span></span>

- **`--type <Heap|Mini>`**

  <span data-ttu-id="95c88-126">Especifica el tipo de volcado, que determina los tipos de información que se recopilan del proceso.</span><span class="sxs-lookup"><span data-stu-id="95c88-126">Specifies the dump type, which determines the kinds of information that are collected from the process.</span></span> <span data-ttu-id="95c88-127">Hay dos tipos:</span><span class="sxs-lookup"><span data-stu-id="95c88-127">There are two types:</span></span>

  - <span data-ttu-id="95c88-128">`Heap`: un volcado grande y relativamente completo que contiene listas de módulos, listas de subprocesos, todas las pilas, información de excepción, información de control y toda la memoria excepto las imágenes asignadas.</span><span class="sxs-lookup"><span data-stu-id="95c88-128">`Heap` - A large and relatively comprehensive dump containing module lists, thread lists, all stacks, exception information, handle information, and all memory except for mapped images.</span></span>
  - <span data-ttu-id="95c88-129">`Mini`: un volcado pequeño que contiene listas de módulos, listas de subprocesos, información de excepción y todas las pilas.</span><span class="sxs-lookup"><span data-stu-id="95c88-129">`Mini` - A small dump containing module lists, thread lists, exception information, and all stacks.</span></span>

  <span data-ttu-id="95c88-130">Si no se especifica, el valor predeterminado es `Heap`.</span><span class="sxs-lookup"><span data-stu-id="95c88-130">If not specified, `Heap` is the default.</span></span>

- **`-o|--output <output_dump_path>`**

  <span data-ttu-id="95c88-131">La ruta de acceso completa y el nombre de archivo donde se debe escribir el volcado recopilado.</span><span class="sxs-lookup"><span data-stu-id="95c88-131">The full path and file name where the collected dump should be written.</span></span>

  <span data-ttu-id="95c88-132">Si no se especifica:</span><span class="sxs-lookup"><span data-stu-id="95c88-132">If not specified:</span></span>

  - <span data-ttu-id="95c88-133">El valor predeterminado es *.\dump_AAAAMMDD_HHMMSS.dmp* en Windows.</span><span class="sxs-lookup"><span data-stu-id="95c88-133">Defaults to *.\dump_YYYYMMDD_HHMMSS.dmp* on Windows.</span></span>
  - <span data-ttu-id="95c88-134">El valor predeterminado es *./core_AAAAMMDD_HHMMSS* en Linux.</span><span class="sxs-lookup"><span data-stu-id="95c88-134">Defaults to *./core_YYYYMMDD_HHMMSS* on Linux.</span></span>

  <span data-ttu-id="95c88-135">AAAAMMDD es año/mes/día y HHMMSS es hora/minuto/segundo.</span><span class="sxs-lookup"><span data-stu-id="95c88-135">YYYYMMDD is Year/Month/Day and HHMMSS is Hour/Minute/Second.</span></span>

- **`--diag`**

  <span data-ttu-id="95c88-136">Habilita el registro de diagnóstico de la recopilación de volcado.</span><span class="sxs-lookup"><span data-stu-id="95c88-136">Enables dump collection diagnostic logging.</span></span>

## <a name="dotnet-dump-analyze"></a><span data-ttu-id="95c88-137">dotnet-dump analyze</span><span class="sxs-lookup"><span data-stu-id="95c88-137">dotnet-dump analyze</span></span>

<span data-ttu-id="95c88-138">Inicia un shell interactivo para explorar un volcado.</span><span class="sxs-lookup"><span data-stu-id="95c88-138">Starts an interactive shell to explore a dump.</span></span> <span data-ttu-id="95c88-139">El shell acepta varios [comandos SOS](#analyze-sos-commands).</span><span class="sxs-lookup"><span data-stu-id="95c88-139">The shell accepts various [SOS commands](#analyze-sos-commands).</span></span>

### <a name="synopsis"></a><span data-ttu-id="95c88-140">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="95c88-140">Synopsis</span></span>

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a><span data-ttu-id="95c88-141">Argumentos</span><span class="sxs-lookup"><span data-stu-id="95c88-141">Arguments</span></span>

- **`<dump_path>`**

  <span data-ttu-id="95c88-142">Especifica la ruta de acceso al archivo de volcado que se va a analizar.</span><span class="sxs-lookup"><span data-stu-id="95c88-142">Specifies the path to the dump file to analyze.</span></span>

### <a name="options"></a><span data-ttu-id="95c88-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="95c88-143">Options</span></span>

- **`-c|--command <debug_command>`**

  <span data-ttu-id="95c88-144">Especifica el [comando](#analyze-sos-commands) que se va a ejecutar en el shell al inicio.</span><span class="sxs-lookup"><span data-stu-id="95c88-144">Specifies the [command](#analyze-sos-commands) to run in the shell on start.</span></span>

### <a name="analyze-sos-commands"></a><span data-ttu-id="95c88-145">Análisis de comandos SOS</span><span class="sxs-lookup"><span data-stu-id="95c88-145">Analyze SOS commands</span></span>

| <span data-ttu-id="95c88-146">Comando</span><span class="sxs-lookup"><span data-stu-id="95c88-146">Command</span></span>                             | <span data-ttu-id="95c88-147">Función</span><span class="sxs-lookup"><span data-stu-id="95c88-147">Function</span></span>                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | <span data-ttu-id="95c88-148">Muestra todos los comandos disponibles.</span><span class="sxs-lookup"><span data-stu-id="95c88-148">Displays all available commands</span></span>                                                               |
| `soshelp|help <command>`            | <span data-ttu-id="95c88-149">Muestra el comando especificado.</span><span class="sxs-lookup"><span data-stu-id="95c88-149">Displays the specified command.</span></span>                                                               |
| `exit|quit`                         | <span data-ttu-id="95c88-150">Sale del modo interactivo.</span><span class="sxs-lookup"><span data-stu-id="95c88-150">Exits interactive mode.</span></span>                                                                       |
| `clrstack <arguments>`              | <span data-ttu-id="95c88-151">Proporciona un seguimiento de pila del código administrado únicamente.</span><span class="sxs-lookup"><span data-stu-id="95c88-151">Provides a stack trace of managed code only.</span></span>                                                  |
| `clrthreads <arguments>`            | <span data-ttu-id="95c88-152">Enumera los subprocesos administrados que se ejecutan.</span><span class="sxs-lookup"><span data-stu-id="95c88-152">Lists the managed threads running.</span></span>                                                            |
| `dumpasync <arguments>`             | <span data-ttu-id="95c88-153">Muestra información sobre las máquinas de estado asincrónicas en el montón de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="95c88-153">Displays information about async state machines on the garbage-collected heap.</span></span>                |
| `dumpassembly <arguments>`          | <span data-ttu-id="95c88-154">Muestra detalles sobre un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="95c88-154">Displays details about an assembly.</span></span>                                                           |
| `dumpclass <arguments>`             | <span data-ttu-id="95c88-155">Muestra información sobre una estructura de clase EE en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-155">Displays information about a EE class structure at the specified address.</span></span>                     |
| `dumpdelegate <arguments>`          | <span data-ttu-id="95c88-156">Muestra información sobre un delegado.</span><span class="sxs-lookup"><span data-stu-id="95c88-156">Displays information about a delegate.</span></span>                                                        |
| `dumpdomain <arguments>`            | <span data-ttu-id="95c88-157">Muestra información sobre todos los dominios de aplicación y sobre todos los ensamblados en los dominios.</span><span class="sxs-lookup"><span data-stu-id="95c88-157">Displays information all the AppDomains and all assemblies within the domains.</span></span>                |
| `dumpheap <arguments>`              | <span data-ttu-id="95c88-158">Muestra información sobre el montón de recolección de elementos no utilizados y estadísticas de recolección de los objetos.</span><span class="sxs-lookup"><span data-stu-id="95c88-158">Displays info about the garbage-collected heap and collection statistics about objects.</span></span>       |
| `dumpil <arguments>`                | <span data-ttu-id="95c88-159">Muestra el Lenguaje intermedio de Microsoft (MSIL) que está asociado a un método administrado.</span><span class="sxs-lookup"><span data-stu-id="95c88-159">Displays the Microsoft intermediate language (MSIL) that is associated with a managed method.</span></span> |
| `dumplog <arguments>`               | <span data-ttu-id="95c88-160">Escribe el contenido de un registro de esfuerzo existente en memoria en el archivo especificado.</span><span class="sxs-lookup"><span data-stu-id="95c88-160">Writes the contents of an in-memory stress log to the specified file.</span></span>                         |
| `dumpmd <arguments>`                | <span data-ttu-id="95c88-161">Muestra información sobre una estructura MethodDesc en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-161">Displays information about a MethodDesc structure at the specified address.</span></span>                   |
| `dumpmodule <arguments>`            | <span data-ttu-id="95c88-162">Muestra información sobre una estructura de módulo EE en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-162">Displays information about a EE module structure at the specified address.</span></span>                    |
| `dumpmt <arguments>`                | <span data-ttu-id="95c88-163">Muestra información sobre una tabla de métodos en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-163">Displays information about a method table at the specified address.</span></span>                           |
| `dumpobj <arguments>`               | <span data-ttu-id="95c88-164">Muestra información sobre un objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-164">Displays info about an object at the specified address.</span></span>                                       |
| `dso|dumpstackobjects <arguments>`  | <span data-ttu-id="95c88-165">Muestra todos los objetos administrados que se han encontrado dentro de los límites de la pila actual.</span><span class="sxs-lookup"><span data-stu-id="95c88-165">Displays all managed objects found within the bounds of the current stack.</span></span>                    |
| `eeheap <arguments>`                | <span data-ttu-id="95c88-166">Muestra información sobre la memoria de proceso que usan las estructuras de datos internas del runtime.</span><span class="sxs-lookup"><span data-stu-id="95c88-166">Displays info about process memory consumed by internal runtime data structures.</span></span>              |
| `finalizequeue <arguments>`         | <span data-ttu-id="95c88-167">Muestra todos los objetos registrados para su finalización.</span><span class="sxs-lookup"><span data-stu-id="95c88-167">Displays all objects registered for finalization.</span></span>                                             |
| `gcroot <arguments>`                | <span data-ttu-id="95c88-168">Muestra información acerca de las referencias (o raíces) a un objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-168">Displays info about references (or roots) to an object at the specified address.</span></span>              |
| `gcwhere <arguments>`               | <span data-ttu-id="95c88-169">Muestra la ubicación en el montón de recolección de elementos no utilizados del argumento que se ha pasado.</span><span class="sxs-lookup"><span data-stu-id="95c88-169">Displays the location in the GC heap of the argument passed in.</span></span>                               |
| `ip2md <arguments>`                 | <span data-ttu-id="95c88-170">Muestra la estructura MethodDesc en la dirección especificada en código JIT.</span><span class="sxs-lookup"><span data-stu-id="95c88-170">Displays the MethodDesc structure at the specified address in JIT code.</span></span>                       |
| `histclear <arguments>`             | <span data-ttu-id="95c88-171">Libera los recursos usados por la familia de comandos `hist*`.</span><span class="sxs-lookup"><span data-stu-id="95c88-171">Releases any resources used by the family of `hist*` commands.</span></span>                                |
| `histinit <arguments>`              | <span data-ttu-id="95c88-172">Inicializa las estructuras SOS del registro de esfuerzo guardado en el código que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="95c88-172">Initializes the SOS structures from the stress log saved in the debuggee.</span></span>                     |
| `histobj <arguments>`               | <span data-ttu-id="95c88-173">Muestra las reubicaciones de registro de esfuerzo de la recolección de elementos no utilizados relacionadas con `<arguments>`.</span><span class="sxs-lookup"><span data-stu-id="95c88-173">Displays the garbage collection stress log relocations related to `<arguments>`.</span></span>              |
| `histobjfind <arguments>`           | <span data-ttu-id="95c88-174">Muestra todas las entradas de registro que hacen referencia a un objeto en la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-174">Displays all the log entries that reference an object at the specified address.</span></span>               |
| `histroot <arguments>`              | <span data-ttu-id="95c88-175">Muestra información relacionada con las promociones y las reubicaciones de la raíz especificada.</span><span class="sxs-lookup"><span data-stu-id="95c88-175">Displays information related to both promotions and relocations of the specified root.</span></span>        |
| `lm|modules`                        | <span data-ttu-id="95c88-176">Muestra los módulos nativos del proceso.</span><span class="sxs-lookup"><span data-stu-id="95c88-176">Displays the native modules in the process.</span></span>                                                   |
| `name2ee <arguments>`               | <span data-ttu-id="95c88-177">Muestra la estructura MethodTable y la estructura EEClass para `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="95c88-177">Displays the MethodTable structure and EEClass structure for the `<argument>`.</span></span>                |
| `pe|printexception <arguments>`     | <span data-ttu-id="95c88-178">Muestra cualquier objeto que se deriva de la clase Exception en la dirección `<argument>`.</span><span class="sxs-lookup"><span data-stu-id="95c88-178">Displays any object derived from the Exception class at the address `<argument>`.</span></span>             |
| `setsymbolserver <arguments>`       | <span data-ttu-id="95c88-179">Habilita la compatibilidad con el servidor de símbolos.</span><span class="sxs-lookup"><span data-stu-id="95c88-179">Enables the symbol server support</span></span>                                                             |
| `syncblk <arguments>`               | <span data-ttu-id="95c88-180">Muestra la información del contenedor de SyncBlock.</span><span class="sxs-lookup"><span data-stu-id="95c88-180">Displays the SyncBlock holder info.</span></span>                                                           |
| `threads|setthread <threadid>`      | <span data-ttu-id="95c88-181">Establece o muestra el identificador del subproceso actual para los comandos SOS.</span><span class="sxs-lookup"><span data-stu-id="95c88-181">Sets or displays the current thread ID for the SOS commands.</span></span>                                  |

## <a name="using-dotnet-dump"></a><span data-ttu-id="95c88-182">Uso de `dotnet-dump`</span><span class="sxs-lookup"><span data-stu-id="95c88-182">Using `dotnet-dump`</span></span>

<span data-ttu-id="95c88-183">El primer paso es recopilar un volcado.</span><span class="sxs-lookup"><span data-stu-id="95c88-183">The first step is to collect a dump.</span></span> <span data-ttu-id="95c88-184">Este paso se puede omitir si ya se ha generado un volcado principal.</span><span class="sxs-lookup"><span data-stu-id="95c88-184">This step can be skipped if a core dump has already been generated.</span></span> <span data-ttu-id="95c88-185">El sistema operativo o la [característica de generación de volcado](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) integrada del runtime de .NET Core pueden crear volcados principales.</span><span class="sxs-lookup"><span data-stu-id="95c88-185">The operating system or the .NET Core runtime's built-in [dump generation feature](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) can each create core dumps.</span></span>

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

<span data-ttu-id="95c88-186">Ahora analice el volcado principal con el comando `analyze`:</span><span class="sxs-lookup"><span data-stu-id="95c88-186">Now analyze the core dump with the `analyze` command:</span></span>

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

<span data-ttu-id="95c88-187">Esta acción abre una sesión interactiva que acepta comandos como los siguientes:</span><span class="sxs-lookup"><span data-stu-id="95c88-187">This action brings up an interactive session that accepts commands like:</span></span>

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

<span data-ttu-id="95c88-188">Para ver una excepción no controlada que ha terminado la aplicación:</span><span class="sxs-lookup"><span data-stu-id="95c88-188">To see an unhandled exception that killed your app:</span></span>

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

## <a name="special-instructions-for-docker"></a><span data-ttu-id="95c88-189">Instrucciones especiales para Docker</span><span class="sxs-lookup"><span data-stu-id="95c88-189">Special instructions for Docker</span></span>

<span data-ttu-id="95c88-190">Si ejecuta en Docker, la recopilación de volcados requiere capacidades de `SYS_PTRACE` (`--cap-add=SYS_PTRACE` o `--privileged`).</span><span class="sxs-lookup"><span data-stu-id="95c88-190">If you're running under Docker, dump collection requires `SYS_PTRACE` capabilities (`--cap-add=SYS_PTRACE` or `--privileged`).</span></span>

<span data-ttu-id="95c88-191">En Microsoft SDK de .NET Core imágenes de Docker de SDK de Linux, algunos comandos `dotnet-dump` pueden producir la siguiente excepción:</span><span class="sxs-lookup"><span data-stu-id="95c88-191">On Microsoft .NET Core SDK Linux Docker images, some `dotnet-dump` commands can throw the following exception:</span></span>

> <span data-ttu-id="95c88-192">Excepción no controlada: System.DllNotFoundException: No se puede cargar la biblioteca compartida "libdl.so" o una de su excepción de dependencias.</span><span class="sxs-lookup"><span data-stu-id="95c88-192">Unhandled exception: System.DllNotFoundException: Unable to load shared library 'libdl.so' or one of its dependencies' exception.</span></span>

<span data-ttu-id="95c88-193">Para solucionar este problema, instale el paquete "libc6-dev".</span><span class="sxs-lookup"><span data-stu-id="95c88-193">To work around this problem, install the "libc6-dev" package.</span></span>
