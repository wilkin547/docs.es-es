---
title: 'Herramienta de diagnóstico dotnet-gcdump: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-gcdump para recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET en vivo mediante EventPipe de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 59de1845ada9e5bdd0b24bf4312517283324ce94
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94826045"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Herramienta de análisis del montón (dotnet-gcdump)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1 y versiones posteriores

## <a name="install"></a>Instalar

Hay dos maneras de descargar e instalar `dotnet-gcdump`:

- **Herramienta global dotnet:**

  Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-gcdump) de `dotnet-gcdump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

  ```dotnetcli
  dotnet tool install --global dotnet-gcdump
  ```

- **Descarga directa:**

  Descargue el archivo ejecutable de la herramienta que coincida con la plataforma:

  | SO  | Plataforma |
  | --- | -------- |
  | Windows | [x86](https://aka.ms/dotnet-gcdump/win-x86) \| [x64](https://aka.ms/dotnet-gcdump/win-x64) \| [arm](https://aka.ms/dotnet-gcdump/win-arm) \| [arm-x64](https://aka.ms/dotnet-gcdump/win-arm64) |
  | macOS   | [x64](https://aka.ms/dotnet-gcdump/osx-x64) |
  | Linux   | [x64](https://aka.ms/dotnet-gcdump/linux-x64) \| [arm](https://aka.ms/dotnet-gcdump/linux-arm) \| [arm64](https://aka.ms/dotnet-gcdump/linux-arm64) \| [musl-x64](https://aka.ms/dotnet-gcdump/linux-musl-x64) \| [musl-arm64](https://aka.ms/dotnet-gcdump/linux-musl-arm64) |

## <a name="synopsis"></a>Sinopsis

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-gcdump` recopila volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET en vivo mediante [EventPipe](./eventpipe.md). Los volcados de memoria de GC se crean desencadenando un GC en el proceso de destino, activando eventos especiales y regenerando el gráfico de raíces de objeto a partir del flujo de eventos. Este proceso permite recopilar volcados de memoria de GC mientras el proceso se está ejecutando y con una sobrecarga mínima. Estos volcados de memoria son útiles para varios escenarios:

- Comparar el número de objetos del montón en varios puntos en el tiempo.
- Analizar raíces de objetos (responder a preguntas como "¿qué sigue teniendo una referencia a este tipo?").
- Recopilar estadísticas generales sobre los recuentos de objetos en el montón.

### <a name="view-the-gc-dump-captured-from-dotnet-gcdump"></a>Ver el volcado de memoria de GC capturado por dotnet-gcdump

En Windows, los archivos `.gcdump` se pueden ver en [PerfView](https://github.com/microsoft/perfview) o en Visual Studio para analizarlos. Actualmente, no es posible abrir un archivo `.gcdump` en plataformas que no sean de Windows.

Puede recopilar varios archivos `.gcdump` y abrirlos simultáneamente en Visual Studio para obtener una comparativa.

## <a name="options"></a>Opciones

- **`--version`**

  Muestra la versión del servicio `dotnet-gcdump`.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## `dotnet-gcdump collect`

Recopila un volcado de memoria de GC de un proceso que se está ejecutando actualmente.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-gcdump collect [-h|--help] [-p|--process-id <pid>] [-o|--output <gcdump-file-path>] [-v|--verbose] [-t|--timeout <timeout>] [-n|--name <name>]
```

### <a name="options"></a>Opciones

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

- **`-p|--process-id <pid>`**

  Identificador del proceso del que se va a recopilar el volcado de memoria de GC.

- **`-o|--output <gcdump-file-path>`**

  Ruta de acceso donde se deben escribir los volcados de memoria de GC recopilados. El valor predeterminado es *.\\AAAAMMDD\_HHMMSS\_\<pid>.gcdump*.

- **`-v|--verbose`**

  Obtener resultados del registro mientras recopila el volcado de memoria de GC.

- **`-t|--timeout <timeout>`**

  Dejar de recopilar el volcado de memoria de GC si tarda más de la cantidad de segundos indicada. El valor predeterminado es 30.

- **`-n|--name <name>`**

  Nombre del proceso del que se va a recopilar el volcado de memoria de GC.

## `dotnet-gcdump ps`

Enumera los procesos de dotnet de los que se pueden recopilar volcados de memoria de GC.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-gcdump ps
```

## `dotnet-gcdump report <gcdump_filename>`

Crear un informe a partir de un volcado de memoria de GC generado anteriormente o de un proceso en ejecución y escribir en `stdout`.

### <a name="synopsis"></a>Sinopsis

```console
dotnet-gcdump report [-h|--help] [-p|--process-id <pid>] [-t|--report-type <HeapStat>]
```

### <a name="options"></a>Opciones

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

- **`-p|--process-id <pid>`**

  Identificador del proceso del que se va a recopilar el volcado de memoria de GC.

- **`-t|--report-type <HeapStat>`**

  Tipo de informe que se va a generar. Opciones disponibles: heapstat (predeterminado).

## <a name="troubleshoot"></a>Solución de problemas

- No hay información de tipo en gcdump.

   Antes de .NET Core 3.1, se producía un problema por el que una memoria caché de tipos no se borraba entre varios gcdump cuando se invocaba con EventPipe. El resultado fue que los eventos necesarios para determinar la información de tipo no se enviaban al segundo gcdump y a los siguientes. Esto se corrigió en la versión preliminar 2 de .NET Core 3.1.

- Los tipos COM y estáticos no se encuentran en el volcado de memoria de GC.

   Antes de la versión preliminar 2 de .NET Core 3.1, se producía un problema por el que los tipos estáticos y COM no se enviaban cuando se invocaba el volcado de memoria de GC a través de EventPipe. Esto se ha corregido en la versión preliminar 2 de .NET Core 3.1.
