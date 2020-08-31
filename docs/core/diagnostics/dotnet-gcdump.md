---
title: 'dotnet-gcdump: .NET Core'
description: Instalación y uso de la herramienta de línea de comandos dotnet-gcdump.
ms.date: 07/26/2020
ms.openlocfilehash: a7b19f4d7487677b975621e7267a17894dae2e3a
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656656"
---
# <a name="heap-analysis-tool-dotnet-gcdump"></a>Herramienta de análisis del montón (dotnet-gcdump)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 3.1 y versiones posteriores

## <a name="install-dotnet-gcdump"></a>Instalación de dotnet-gcdump

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-gcdump) de `dotnet-gcdump`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install -g dotnet-gcdump
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-gcdump [-h|--help] [--version] <command>
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-gcdump` permite recopilar volcados de memoria de GC (recolector de elementos no utilizados) de procesos de .NET dinámicos. Usa la tecnología EventPipe, que es una alternativa multiplataforma a ETW en Windows. Los volcados de memoria de GC se crean desencadenando un GC en el proceso de destino, activando eventos especiales y regenerando el gráfico de raíces de objeto a partir del flujo de eventos. Este proceso permite recopilar volcados de memoria de GC mientras el proceso se está ejecutando y con una sobrecarga mínima. Estos volcados de memoria son útiles para varios escenarios:

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
