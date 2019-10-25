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
# <a name="trace-for-performance-analysis-utility-dotnet-trace"></a>Seguimiento de la utilidad de análisis de rendimiento (`dotnet-trace`)

**Este artículo se aplica a:** SDK de .NET Core 3.0 y versiones posteriores

## <a name="installing-dotnet-trace"></a>Instalación de `dotnet-trace`

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-trace) de `dotnet-trace`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-trace
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-trace [-h, --help] [--version] <command>
```

## <a name="description"></a>DESCRIPCIÓN

La herramienta `dotnet-trace` es una herramienta global de CLI multiplataforma que permite la recopilación de seguimientos de .NET Core de un proceso en ejecución sin ningún generador de perfiles nativo implicado. Se basa en la tecnología `EventPipe` multiplataforma del runtime de .NET Core. `dotnet-trace` ofrece la misma experiencia en Windows, Linux o macOS.

## <a name="options"></a>Opciones

- **`--version`**

Muestra la versión de la utilidad dotnet-counters.

- **`-h|--help`**

Muestra la ayuda de la línea de comandos.

## <a name="commands"></a>Comandos

| Comando                                                     |
| ----------------------------------------------------------- |
| [dotnet-trace collect](#dotnet-trace-collect)               |
| [dotnet-trace convert](#dotnet-trace-convert)               |
| [dotnet-trace list-processes](#dotnet-trace-list-processes) |
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

  Establece el tamaño del búfer circular en memoria en megabytes. Valor predeterminado de 256 MB.

- **`-o|--output <trace-file-path>`**

  Ruta de acceso de salida para los datos de seguimiento recopilados. Si no se especifica, el valor predeterminado es`trace.nettrace`.

- **`--providers <list-of-comma-separated-providers>`**

  Lista separada por comas de proveedores de `EventPipe` que se van a habilitar. Estos proveedores complementan a los proveedores implícitos en `--profile <profile-name>`. Si hay alguna incoherencia para un proveedor determinado, la configuración aquí tiene prioridad sobre la configuración implícita del perfil.

  Esta lista de proveedores tiene el siguiente formato:

  - `Provider[,Provider]`
  - `Provider` tiene el formato: `KnownProviderName[:Flags[:Level][:KeyValueArgs]]`.
  - `KeyValueArgs` tiene el formato: `[key1=value1][;key2=value2]`.

- **`--profile <profile-name>`**

  Un conjunto con nombre predefinido de configuraciones de proveedor que permite especificar sucintamente los escenarios de seguimiento comunes.

- **`--format <NetTrace|Speedscope>`**

  Establece el formato de salida para la conversión del archivo de seguimiento.

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

## <a name="dotnet-trace-list-processes"></a>dotnet-trace list-processes

Muestra los procesos de dotnet en los que se puede realizar un seguimiento.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace list-processes [-h|--help]
```

## <a name="dotnet-trace-list-profiles"></a>dotnet-trace list-profiles

Muestra los perfiles de seguimiento pregenerados con una descripción de los proveedores y filtros que hay en cada perfil.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-trace list-profiles [-h|--help]
```

## <a name="collect-a-trace-with-dotnet-trace"></a>Recopilación de un seguimiento con `dotnet-trace`

- Para recopilar seguimientos mediante `dotnet-trace`, primero debe averiguar el identificador de proceso (PID) de la aplicación .NET Core del que se van a recopilar seguimientos.

  - En Windows, hay opciones como el uso del administrador de tareas o el comando `tasklist`.
  - En Linux, la opción trivial podría ser con el uso del comando `ps`.

También puede usar el comando [dotnet-trace list-processes](#dotnet-trace-list-processes) para averiguar qué procesos de .NET Core se están ejecutando, junto con los PID.

- Luego, ejecute el siguiente comando:

```console
> dotnet-trace collect --process-id <PID>

Press <Enter> to exit...
Connecting to process: <Full-Path-To-Process-Being-Profiled>/dotnet.exe
Collecting to file: <Full-Path-To-Trace>/trace.nettrace
  Session Id: <SessionId>
  Recording trace 721.025 (KB)
```

- Por último, detenga la recolección presionando la tecla `<Enter>` y `dotnet-trace` terminará de registrar los eventos en el archivo `trace.nettrace`.

## <a name="viewing-the-trace-captured-from-dotnet-trace"></a>Vista del seguimiento capturado desde `dotnet-trace`

En Windows, los archivos `.nettrace` se pueden ver en [PerfView](https://github.com/microsoft/perfview) para su análisis, al igual que los seguimientos recopilados con ETW o LTTng. En el caso de los seguimientos recopilados en Linux, puede trasladar el seguimiento a una máquina Windows para verlo en PerfView.

También puede ver el seguimiento en una máquina Linux cambiando el formato de salida de `dotnet-trace` a `speedscope`. Puede cambiar el formato de archivo de salida mediante la opción `-f|--format`: `-f speedscope` hará que `dotnet-trace` genere un archivo `speedscope`. Actualmente, puede elegir entre `nettrace` (opción predeterminada) y `speedscope`. Loa archivos `Speedscope` se pueden abrir en <https://www.speedscope.app>.

> [!NOTE]
> El runtime de .NET Core genera seguimientos en el formato `nettrace` y se convierten a speedscope (si se especifica) una vez completado este seguimiento. Dado que algunas conversiones pueden provocar la pérdida de datos, el archivo `nettrace` original se conserva junto al archivo convertido.

## <a name="using-dotnet-trace-to-collect-counter-values-over-time"></a>Uso de `dotnet-trace` para recopilar valores de contador a lo largo del tiempo

Si está intentando usar `EventCounter` para la supervisión básica del estado en configuraciones sensibles al rendimiento, como los entornos de producción, y quiere recopilar seguimientos en lugar de verlos en tiempo real, también puede hacerlo con `dotnet-trace`.

Por ejemplo, si quiere recopilar valores de contador de rendimiento en runtime, puede usar el comando siguiente:

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1
```

Este comando indica a los contadores en runtime que se van a notificar una vez por segundo para la supervisión ligera del estado. Reemplazar `EventCounterIntervalSec=1` por un valor mayor (por ejemplo, 60) permite recopilar un seguimiento más pequeño con menos granularidad en los datos de contador.

Si quiere deshabilitar los eventos en runtime para reducir aún más la sobrecarga (y el tamaño de seguimiento), puede usar el comando siguiente para deshabilitar los eventos en runtime y el generador de perfiles de pila administrado.

```console
dotnet-trace collect --process-id <PID> --providers System.Runtime:0:1:EventCounterIntervalSec=1,Microsoft-Windows-DotNETRuntime:0:1,Microsoft-DotNETCore-SampleProfiler:0:1
```

## <a name="net-providers"></a>Proveedores .NET

El runtime de .NET Core admite los siguientes proveedores .NET. .NET Core usa las mismas palabras clave para habilitar los seguimientos de `Event Tracing for Windows (ETW)` y `EventPipe`.

| Nombre del proveedor                            | Información |
|------------------------------------------|-------------|
| `Microsoft-Windows-DotNETRuntime`        | [El proveedor de runtime](../../framework/performance/clr-etw-providers.md#the-runtime-provider)<br>[Palabras clave de runtime de CLR](../../framework/performance/clr-etw-keywords-and-levels.md#runtime) |
| `Microsoft-Windows-DotNETRuntimeRundown` | [El proveedor de informe detallado](../../framework/performance/clr-etw-providers.md#the-rundown-provider)<br>[Palabras clave de informe detallado de CLR](../../framework/performance/clr-etw-keywords-and-levels.md#rundown) |
| `Microsoft-DotNETCore-SampleProfiler`    | Habilita el generador de perfiles de ejemplo. |
