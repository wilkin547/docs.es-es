---
title: 'Herramienta de diagnóstico dotnet-trace: CLI de .NET'
description: Aprenda a instalar y usar la herramienta dotnet-trace de la CLI para recopilar seguimientos de .NET de un proceso en ejecución sin el generador de perfiles nativo, mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: d0798e4f703c18c48db47193ac24ec0d13b66ae5
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94829315"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>Utilidad de análisis de rendimiento dotnet-trace

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="install"></a>Instalar

Hay dos maneras de descargar e instalar `dotnet-trace`:

- **Herramienta global dotnet:**

  Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-trace
  ```

- **Descarga directa:**

  descargue el archivo ejecutable de la herramienta que coincida con la plataforma:

  | SO  | Plataforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-trace/win-x86) \| [x64](https://aka.ms/dotnet-trace/win-x64) \| [arm](https://aka.ms/dotnet-trace/win-arm) \| [arm-x64](https://aka.ms/dotnet-trace/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-trace/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-trace/linux-x64) \| [arm](https://aka.ms/dotnet-trace/linux-arm) \| [arm64](https://aka.ms/dotnet-trace/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-trace/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-trace/linux-musl-arm64) |

## <a name="synopsis"></a>Sinopsis

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Descripción

La herramienta `dotnet-trace`:

* Es una herramienta de .NET Core para varias plataformas.
* Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.
* Se basa en [`EventPipe`](./eventpipe.md) del entorno de ejecución de .NET Core.
* Ofrece la misma experiencia en Windows, Linux o macOS.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

- **`--version`**

  Muestra la versión de la utilidad dotnet-trace.

## <a name="commands"></a>Comandos

| Comando                                                   |
|-----------------------------------------------------------|
| [dotnet-trace collect](#dotnet-trace-collect)             |
| [dotnet-trace convert](#dotnet-trace-convert)             |
| [dotnet-trace ps](#dotnet-trace-ps)                       |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles) |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Recopila un seguimiento de diagnóstico de un proceso en ejecución.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace collect [--buffersize <size>] [--clreventlevel <clreventlevel>] [--clrevents <clrevents>]
    [--format <Chromium|NetTrace|Speedscope>] [-h|--help]
    [-n, --name <name>]  [-o|--output <trace-file-path>] [-p|--process-id <pid>]
    [--profile <profile-name>] [--providers <list-of-comma-separated-providers>]
    [-- <command>] (for target applications running .NET 5.0 or later)
```

### <a name="options"></a>Opciones

- **`--buffersize <size>`**

  Establece el tamaño del búfer circular en memoria, en megabytes. Valor predeterminado de 256 MB.

- **`--clreventlevel <clreventlevel>`**

  Nivel de detalle de los eventos CLR que se van a emitir.

- **`--clrevents <clrevents>`**

  Lista de eventos de tiempo de ejecución de CLR que se van a emitir.

- **`--format {Chromium|NetTrace|Speedscope}`**

  Establece el formato de salida para la conversión del archivo de seguimiento. De manera predeterminada, es `NetTrace`.

- **`-n, --name <name>`**

  Nombre del proceso del que se va a recopilar el seguimiento.

- **`-o|--output <trace-file-path>`**

  Ruta de acceso de salida para los datos de seguimiento recopilados. Si no se especifica, el valor predeterminado es `trace.nettrace`.

- **`-p|--process-id <PID>`**

  Identificador del proceso del que se va a recopilar el seguimiento.

- **`--profile <profile-name>`**

  Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.

- **`--providers <list-of-comma-separated-providers>`**

  Lista separada por comas de proveedores de `EventPipe` que se van a habilitar. Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`. Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.

  Esta lista de proveedores tiene el siguiente formato:

  - `Provider[,Provider]`
  - `Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.

- **`-- <command>` (solo para seleccionar como destino aplicaciones que ejecutan .NET 5.0)**

  Después de los parámetros de configuración de la colección, el usuario puede anexar `--` seguido de un comando para iniciar una aplicación de .NET con un entorno de ejecución de 5.0 como mínimo. Esto puede resultar útil al diagnosticar problemas que se producen al principio del proceso, como problemas de rendimiento de inicio o de cargador de ensamblados y errores del enlazador.

  > [!NOTE]
  > El uso de esta opción supervisa el primer proceso de .NET 5.0 que se comunica con la herramienta, lo que significa que, si el comando inicia varias aplicaciones de .NET, solo recopilará la primera. Por tanto, se recomienda usar esta opción en aplicaciones independientes, o bien utilizar la opción `dotnet exec <app.dll>`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace convert [<input-filename>] [--format <Chromium|NetTrace|Speedscope>] [-h|--help] [-o|--output <output-filename>]
```

### <a name="arguments"></a>Argumentos

- **`<input-filename>`**

  Archivo de seguimiento de entrada que se va a convertir. El valor predeterminado es *trace.nettrace*.

### <a name="options"></a>Opciones

- **`--format <Chromium|NetTrace|Speedscope>`**

  Establece el formato de salida para la conversión del archivo de seguimiento.

- **`-o|--output <output-filename>`**

  Nombre de archivo de salida. Se agregará la extensión del formato de destino.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

 Enumera los procesos de dotnet de los que se pueden recopilar seguimientos.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace ps [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Recopilación de un seguimiento con dotnet-trace

Para recopilar seguimientos mediante `dotnet-trace`:

- Averigüe el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.

  - En Windows, puede usar el administrador de tareas o el comando `tasklist`, por ejemplo.
  - En Linux, por ejemplo, el comando `ps`.
  - [dotnet-trace ps](#dotnet-trace-ps)

- Ejecute el siguiente comando:

  ```console
  dotnet-trace collect --process-id <PID>
  ```

  El comando anterior genera una salida similar a la siguiente:

  ```console
  Press <Enter> to exit...
  Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
  Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
  ```

- Detenga la recolección presionando la tecla `<Enter>`. `dotnet-trace` finalizará el registro de eventos en el archivo *trace.nettrace*.

## <a name="launch-a-child-application-and-collect-a-trace-from-its-startup-using-dotnet-trace"></a>Inicio de una aplicación secundaria y recopilación de un seguimiento de su inicio mediante dotnet-trace

> [!IMPORTANT]
> Esto solo funciona para las aplicaciones que ejecutan .NET 5.0 o una versión posterior.

A veces puede resultar útil recopilar un seguimiento de un proceso desde su inicio. En el caso de las aplicaciones que ejecutan .NET 5.0 o versiones posteriores, es posible hacerlo mediante dotnet-trace.

Esto iniciará `hello.exe` con `arg1` y `arg2` como argumentos de la línea de comandos y recopilará un seguimiento de su inicio en tiempo de ejecución:

```console
dotnet-trace collect -- hello.exe arg1 arg2
```

El comando anterior genera una salida similar a la siguiente:

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

Para detener la recopilación del seguimiento, presione `<Enter>` o las teclas `<Ctrl + C>`. Si lo hace, también saldrá de `hello.exe`.

> [!NOTE]
> El inicio de `hello.exe` a través de dotnet-trace redirigirá su entrada o salida, y no podrá interactuar con su stdin/stdout.
> La salida de la herramienta por medio de Ctrl + C o SIGTERM finalizará con seguridad la herramienta y el proceso secundario.
> Si el proceso secundario termina antes que la herramienta, la herramienta también se cerrará y el seguimiento se debe poder ver de forma segura.

## <a name="view-the-trace-captured-from-dotnet-trace"></a>Vista del seguimiento capturado de dotnet-trace

En Windows, los archivos *.nettrace* se pueden ver en [PerfView](https://github.com/microsoft/perfview) para el análisis: En el caso de los seguimientos recopilados en otras plataformas, el archivo de seguimiento se puede trasladar a una máquina Windows para verlo en PerfView.

En Linux, el seguimiento se puede ver cambiando el formato de salida de `dotnet-trace` a `speedscope`. Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`. Puede elegir entre `nettrace` (opción predeterminada) y `speedscope`. Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.

> [!NOTE]
> El tiempo de ejecución de .NET Core genera seguimientos en el formato `nettrace`. Los seguimientos se convierten a formato speedscope (si se especifica) una vez completado el seguimiento. Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.

## <a name="use-dotnet-trace-to-collect-counter-values-over-time"></a>Uso de dotnet-trace para recopilar valores de contador a lo largo del tiempo

`dotnet-trace` puede:

* Use `EventCounter` para la supervisión de estado básica en entornos con distinción de rendimiento. Por ejemplo, en producción.
* Recopile seguimientos para que no sea necesario visualizarlos en tiempo real.

Por ejemplo, para recopilar valores de contador de rendimiento en tiempo de ejecución, puede usar el comando siguiente:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

El comando anterior indica a los contadores en tiempo de ejecución que se deben notificar una vez por segundo para la supervisión ligera del estado. Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.

El comando siguiente reduce la sobrecarga y el tamaño de seguimiento más que el anterior:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

El comando anterior deshabilita los eventos en tiempo de ejecución y el generador de perfiles de pila administrado.

## <a name="net-providers"></a>Proveedores .NET

El runtime de .NET Core admite los siguientes proveedores .NET. .NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.

| Nombre del proveedor                            | Información |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [El proveedor de runtime](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Palabras clave de runtime de CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [El proveedor de informe detallado](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Palabras clave de informe detallado de CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Habilita el generador de perfiles de ejemplo. |
