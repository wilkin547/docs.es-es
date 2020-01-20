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
# <a name="dump-collection-and-analysis-utility-dotnet-dump"></a>Utilidad de recopilación y análisis de volcado (`dotnet-dump`)

**Este artículo se aplica a: ✓** SDK de .NET Core 3.0.x y versiones posteriores

> [!NOTE]
> `dotnet-dump` no se admite en macOS.

## <a name="installing-dotnet-dump"></a>Instalación de `dotnet-dump`

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-dump) de `dotnet-dump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-dump
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-dump [-h|--help] [--version] <command>
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-dump` es una forma de recopilar y analizar los volcados de Windows y Linux sin necesidad de un depurador nativo implicado, como `lldb` en Linux. Esta herramienta es importante en plataformas como Alpine Linux, donde no está disponible una versión de `lldb` totalmente operativa. La herramienta `dotnet-dump` permite ejecutar comandos SOS para analizar bloqueos y el recolector de elementos no utilizados (GC), pero no es un depurador nativo, por lo que no se admiten elementos como la visualización de marcos de pila nativos.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra la versión de la utilidad dotnet-counters.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="commands"></a>Comandos

| Comando                                     |
| ------------------------------------------- |
| [dotnet-dump collect](#dotnet-dump-collect) |
| [dotnet-dump analyze](#dotnet-dump-analyze) |

## <a name="dotnet-dump-collect"></a>dotnet-dump collect

Captura un volcado de un proceso.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-dump collect [-h|--help] [-p|--process-id] [--type] [-o|--output] [--diag]
```

### <a name="options"></a>Opciones

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

- **`-p|--process-id <PID>`**

  Especifica el número de id. de proceso del que se va a recopilar un volcado de memoria.

- **`--type <Heap|Mini>`**

  Especifica el tipo de volcado, que determina los tipos de información que se recopilan del proceso. Hay dos tipos:

  - `Heap`: un volcado grande y relativamente completo que contiene listas de módulos, listas de subprocesos, todas las pilas, información de excepción, información de control y toda la memoria excepto las imágenes asignadas.
  - `Mini`: un volcado pequeño que contiene listas de módulos, listas de subprocesos, información de excepción y todas las pilas.

  Si no se especifica, el valor predeterminado es `Heap`.

- **`-o|--output <output_dump_path>`**

  La ruta de acceso completa y el nombre de archivo donde se debe escribir el volcado recopilado.

  Si no se especifica:

  - El valor predeterminado es *.\dump_AAAAMMDD_HHMMSS.dmp* en Windows.
  - El valor predeterminado es *./core_AAAAMMDD_HHMMSS* en Linux.

  AAAAMMDD es año/mes/día y HHMMSS es hora/minuto/segundo.

- **`--diag`**

  Habilita el registro de diagnóstico de la recopilación de volcado.

## <a name="dotnet-dump-analyze"></a>dotnet-dump analyze

Inicia un shell interactivo para explorar un volcado. El shell acepta varios [comandos SOS](#analyze-sos-commands).

### <a name="synopsis"></a>Sinopsis

```console
dotnet-dump analyze <dump_path> [-h|--help] [-c|--command]
```

### <a name="arguments"></a>Argumentos

- **`<dump_path>`**

  Especifica la ruta de acceso al archivo de volcado que se va a analizar.

### <a name="options"></a>Opciones

- **`-c|--command <debug_command>`**

  Especifica el [comando](#analyze-sos-commands) que se va a ejecutar en el shell al inicio.

### <a name="analyze-sos-commands"></a>Análisis de comandos SOS

| Comando                             | Función                                                                                      |
| ----------------------------------- | --------------------------------------------------------------------------------------------- |
| `soshelp`                           | Muestra todos los comandos disponibles.                                                               |
| `soshelp|help <command>`            | Muestra el comando especificado.                                                               |
| `exit|quit`                         | Sale del modo interactivo.                                                                       |
| `clrstack <arguments>`              | Proporciona un seguimiento de pila del código administrado únicamente.                                                  |
| `clrthreads <arguments>`            | Enumera los subprocesos administrados que se ejecutan.                                                            |
| `dumpasync <arguments>`             | Muestra información sobre las máquinas de estado asincrónicas en el montón de recolección de elementos no utilizados.                |
| `dumpassembly <arguments>`          | Muestra detalles sobre un ensamblado.                                                           |
| `dumpclass <arguments>`             | Muestra información sobre una estructura de clase EE en la dirección especificada.                     |
| `dumpdelegate <arguments>`          | Muestra información sobre un delegado.                                                        |
| `dumpdomain <arguments>`            | Muestra información sobre todos los dominios de aplicación y sobre todos los ensamblados en los dominios.                |
| `dumpheap <arguments>`              | Muestra información sobre el montón de recolección de elementos no utilizados y estadísticas de recolección de los objetos.       |
| `dumpil <arguments>`                | Muestra el Lenguaje intermedio de Microsoft (MSIL) que está asociado a un método administrado. |
| `dumplog <arguments>`               | Escribe el contenido de un registro de esfuerzo existente en memoria en el archivo especificado.                         |
| `dumpmd <arguments>`                | Muestra información sobre una estructura MethodDesc en la dirección especificada.                   |
| `dumpmodule <arguments>`            | Muestra información sobre una estructura de módulo EE en la dirección especificada.                    |
| `dumpmt <arguments>`                | Muestra información sobre una tabla de métodos en la dirección especificada.                           |
| `dumpobj <arguments>`               | Muestra información sobre un objeto en la dirección especificada.                                       |
| `dso|dumpstackobjects <arguments>`  | Muestra todos los objetos administrados que se han encontrado dentro de los límites de la pila actual.                    |
| `eeheap <arguments>`                | Muestra información sobre la memoria de proceso que usan las estructuras de datos internas del runtime.              |
| `finalizequeue <arguments>`         | Muestra todos los objetos registrados para su finalización.                                             |
| `gcroot <arguments>`                | Muestra información acerca de las referencias (o raíces) a un objeto en la dirección especificada.              |
| `gcwhere <arguments>`               | Muestra la ubicación en el montón de recolección de elementos no utilizados del argumento que se ha pasado.                               |
| `ip2md <arguments>`                 | Muestra la estructura MethodDesc en la dirección especificada en código JIT.                       |
| `histclear <arguments>`             | Libera los recursos usados por la familia de comandos `hist*`.                                |
| `histinit <arguments>`              | Inicializa las estructuras SOS del registro de esfuerzo guardado en el código que se está depurando.                     |
| `histobj <arguments>`               | Muestra las reubicaciones de registro de esfuerzo de la recolección de elementos no utilizados relacionadas con `<arguments>`.              |
| `histobjfind <arguments>`           | Muestra todas las entradas de registro que hacen referencia a un objeto en la dirección especificada.               |
| `histroot <arguments>`              | Muestra información relacionada con las promociones y las reubicaciones de la raíz especificada.        |
| `lm|modules`                        | Muestra los módulos nativos del proceso.                                                   |
| `name2ee <arguments>`               | Muestra la estructura MethodTable y la estructura EEClass para `<argument>`.                |
| `pe|printexception <arguments>`     | Muestra cualquier objeto que se deriva de la clase Exception en la dirección `<argument>`.             |
| `setsymbolserver <arguments>`       | Habilita la compatibilidad con el servidor de símbolos.                                                             |
| `syncblk <arguments>`               | Muestra la información del contenedor de SyncBlock.                                                           |
| `threads|setthread <threadid>`      | Establece o muestra el identificador del subproceso actual para los comandos SOS.                                  |

## <a name="using-dotnet-dump"></a>Uso de `dotnet-dump`

El primer paso es recopilar un volcado. Este paso se puede omitir si ya se ha generado un volcado principal. El sistema operativo o la [característica de generación de volcado](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) integrada del runtime de .NET Core pueden crear volcados principales.

```console
$ dotnet-dump collect --process-id 1902
Writing minidump to file ./core_20190226_135837
Written 98983936 bytes (24166 pages) to core file
Complete
```

Ahora analice el volcado principal con el comando `analyze`:

```console
$ dotnet-dump analyze ./core_20190226_135850
Loading core dump: ./core_20190226_135850
Ready to process analysis commands. Type 'help' to list available commands or 'help [command]' to get detailed help on a command.
Type 'quit' or 'exit' to exit the session.
>
```

Esta acción abre una sesión interactiva que acepta comandos como los siguientes:

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

Para ver una excepción no controlada que ha terminado la aplicación:

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

## <a name="special-instructions-for-docker"></a>Instrucciones especiales para Docker

Si ejecuta en Docker, la recopilación de volcados requiere capacidades de `SYS_PTRACE` (`--cap-add=SYS_PTRACE` o `--privileged`).

En Microsoft SDK de .NET Core imágenes de Docker de SDK de Linux, algunos comandos `dotnet-dump` pueden producir la siguiente excepción:

> Excepción no controlada: System.DllNotFoundException: No se puede cargar la biblioteca compartida "libdl.so" o una de su excepción de dependencias.

Para solucionar este problema, instale el paquete "libc6-dev".
