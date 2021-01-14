---
title: 'Herramienta de diagnóstico dotnet-symbol: CLI de .NET'
description: Aprenda a instalar y usar la herramienta de la CLI dotnet-symbol para descargar los archivos necesarios para depurar minivolcados y volcados de memoria de .NET.
ms.date: 11/17/2020
ms.openlocfilehash: 69c05544e886d9d41113c8a2383f760b85d01124
ms.sourcegitcommit: c0b803bffaf101e12f071faf94ca21b46d04ff30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/24/2020
ms.locfileid: "97764999"
---
# <a name="symbol-downloader-dotnet-symbol"></a>Aplicación de descarga de símbolos (dotnet-symbol)

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="install"></a>Instalar

Para instalar la versión de lanzamiento más reciente del [paquete NuGet](https://www.nuget.org/packages/dotnet-symbol) de `dotnet-symbol`, use el comando [dotnet tool install](../tools/dotnet-tool-install.md):

```dotnetcli
dotnet tool install --global dotnet-symbol
```

## <a name="synopsis"></a>Sinopsis

```console
dotnet-symbol [-h|--help] [options] <FILES>
```

## <a name="description"></a>Descripción

La herramienta global `dotnet-symbol` descarga archivos (símbolos, paquetes DAC, módulos, etc.) que son necesarios para la depuración de volcados y minivolcados de núcleo. Esto puede ser útil al depurar volcados de memoria capturados en otra máquina. `dotnet-symbol` puede descargar los módulos y símbolos necesarios para analizar el volcado de memoria.

## <a name="options"></a>Opciones

- **`--microsoft-symbol-server`**

  Agrega la ruta de acceso del servidor de símbolos "http://msdl.microsoft.com/download/symbols" (valor predeterminado).

- **`--server-path <symbol server path>`**

  Agrega un servidor de símbolos a la ruta de acceso del servidor.

- **`authenticated-server-path <pat> <server path>`**

  Agrega un servidor de símbolos autenticado a la ruta de acceso del servidor mediante un token de acceso personal (PAT).

- **`--cache-directory <file cache directory>`**

  Agrega un directorio de caché.

- **`--recurse-subdirectories`**

  Procesa archivos de entrada en todos los subdirectorios.

- **`--host-only`**

  Descarga solo el programa host (es decir, dotnet) que necesita lldb para cargar volcados de núcleo.

- **`--symbols`**

  Descarga archivos de símbolos (.pdb, .dbg, .dwarf).

- **`--modules`**

  Descarga archivos de módulo (.dll, .so, .dylib).

- **`--debugging`**

  Descarga módulos de depuración especiales (DAC, DBI, SOS).

- **`--windows-pdbs`**

  Fuerza la descarga de los archivos PDB de Windows cuando también hay archivos PDB portátiles disponibles.

- **`-o, --output <output directory>`**

  Establece el directorio de salida. De lo contrario, escribe "next" en el archivo de entrada (valor predeterminado).

- **`-d, --diagnostics`**

  Habilita la salida de diagnóstico.

- **`-h|--help`**

  Muestra la ayuda de la línea de comandos.

## <a name="download-symbols"></a>Descargar símbolos

De forma predeterminada, al ejecutar `dotnet-symbol` en un archivo de volcado de memoria, se descargan todos los módulos, símbolos y archivos DAC/DBI necesarios para depurar el volcado, incluidos los ensamblados administrados. Dado que SOS ahora puede descargar símbolos cuando sea necesario, la mayoría de los volcados de núcleo de Linux se pueden analizar mediante lldb solo con los módulos host (dotnet) y de depuración. Para obtener estos archivos necesarios para diagnosticar un volcado de memoria con lldb, ejecute lo siguiente:

```console
dotnet-symbol --host-only --debugging <dump file path>
```

## <a name="troubleshoot"></a>Solución de problemas

- Error "404 No encontrado" al descargar símbolos.

   La descarga de símbolos solo se admite para las versiones oficiales del entorno de ejecución de .NET Core adquiridas a través de canales oficiales como el [sitio web oficial](https://dotnet.microsoft.com/download/dotnet-core) y los [orígenes predeterminados en los scripts de instalación de dotnet](../tools/dotnet-install-script.md). Un error 404 al descargar archivos de depuración puede indicar que el volcado de memoria se ha creado con un entorno de ejecución de .NET Core desde otro origen, como uno compilado localmente desde el origen o para una distribución concreta de Linux, o bien desde sitios de la comunidad como archlinux. En estos casos, el archivo necesario para la depuración (dotnet, libcoreclr.so y libmscordaccore.so) se debe copiar desde esos orígenes o desde el entorno en el que se creó el archivo de volcado de memoria.

## <a name="see-also"></a>Consulte también

* [Depuración con símbolos](/windows/win32/dxtecharts/debugging-with-symbols)
* [PDB portátiles](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md)
