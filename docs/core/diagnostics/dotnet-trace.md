---
title: 'La herramienta dotnet-trace: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-trace.
ms.date: 11/21/2019
ms.openlocfilehash: 6880c3721e4cab12677bd02c82ca944cc9812670
ms.sourcegitcommit: 2b3b2d684259463ddfc76ad680e5e09fdc1984d2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2020
ms.locfileid: "80888090"
---
# <a name="dotnet-trace-performance-analysis-utility"></a>Utilidad de análisis de rendimiento dotnet-trace

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.0 y versiones posteriores

## <a name="install-dotnet-trace"></a>Instalación de dotnet-trace

Instale el [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) `dotnet-trace` con el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>Descripción

La herramienta `dotnet-trace`:

* Es una herramienta de .NET Core para varias plataformas.
* Habilita la recolección de seguimientos de .NET Core de un proceso en ejecución sin un generador de perfiles nativo.
* Se basa en la tecnología `EventPipe` multiplataforma del entorno de ejecución de .NET Core.
* Ofrece la misma experiencia en Windows, Linux o macOS.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra la versión de la utilidad dotnet-trace.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="commands"></a>Comandos

| Comando                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace ps](#dotnet-trace-ps) |
| [dotnet-trace list-profiles](#dotnet-trace-list-profiles)   |

## <a name="dotnet-trace-collect"></a>dotnet-trace collect

Recopila un seguimiento de diagnóstico de un proceso en ejecución.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace collect [-h|--help] [-p|--process-id] [--buffersize <size>] [-o|--output]
    [--providers] [--profile <profile-name>] [--format]
```

### <a name="options"></a>Opciones

- **`-p|--process-id <PID>`**

  Proceso del que se va a recopilar el seguimiento.

- **`--buffersize <size>`**

  Establece el tamaño del búfer circular en memoria, en megabytes. Valor predeterminado de 256 MB.

- **`-o|--output <trace-file-path>`**

  Ruta de acceso de salida para los datos de seguimiento recopilados. Si no se especifica, el valor predeterminado es`trace.nettrace`.

- **`--providers <list-of-comma-separated-providers>`**

  Lista separada por comas de proveedores de `EventPipe` que se van a habilitar. Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`. Si hay alguna incoherencia para un proveedor determinado, esta configuración tiene prioridad sobre la configuración implícita del perfil.

  Esta lista de proveedores tiene el siguiente formato:

  - `Provider[,Provider]`
  - `Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.

- **`--format {NetTrace|Speedscope}`**

  Establece el formato de salida para la conversión del archivo de seguimiento. De manera predeterminada, es `NetTrace`.

## <a name="dotnet-trace-convert"></a>dotnet-trace convert

Convierte los seguimientos de `nettrace` en formatos alternativos para usarlos con herramientas de análisis de seguimiento alternativas.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace convert [<input-filename>] [-h|--help] [--format] [-o|--output]
```

### <a name="arguments"></a>Argumentos

- **`<input-filename>`**

  Archivo de seguimiento de entrada que se va a convertir. El valor predeterminado es *trace.nettrace*.

### <a name="options"></a>Opciones

- **`--format <NetTrace|Speedscope>`**

  Establece el formato de salida para la conversión del archivo de seguimiento.

- **`-o|--output <output-filename>`**

  Nombre de archivo de salida. Se agregará la extensión del formato de destino.

## <a name="dotnet-trace-ps"></a>dotnet-trace ps

Muestra los procesos de dotnet a los cuales se puede adjuntar.

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
