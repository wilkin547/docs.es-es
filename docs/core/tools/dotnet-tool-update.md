---
title: Comando dotnet tool update - CLI de .NET Core
description: El comando dotnet tool update actualiza la herramienta global de .NET Core en su equipo.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 90b0dc91f74d890420dc7185642aa89100cadba8
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2018
ms.locfileid: "44069398"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nombre

`dotnet tool update`: actualiza la [herramienta global de .NET Core](global-tools.md) especificada en el equipo.

## <a name="synopsis"></a>Sinopsis

```console
dotnet tool update <PACKAGE_NAME> <-g|--global> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <PACKAGE_NAME> <--tool-path> [--configfile] [--framework] [-v|--verbosity]
dotnet tool update <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool update` permite actualizar las herramientas globales de .NET Core en su equipo a la versión estable más reciente del paquete. El comando desinstala y vuelve a instalar una herramienta, actualizándola de facto. Para utilizar el comando, especifique que quiere actualizar una herramienta de una instalación en el ámbito de los usuarios con la opción `--global`, o bien especifique una ruta de acceso en la que instalar la herramienta usando para ello la opción `--tool-path`.

## <a name="arguments"></a>Argumentos

`PACKAGE_NAME`

Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere actualizar. Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opciones

`--add-source <SOURCE>`

Agrega un origen de paquete NuGet adicional que se usará durante la instalación.

`--configfile <FILE>`

El archivo de configuración de NuGet (*nuget.config*) que se usará.

`--framework <FRAMEWORK>`

Especifica la [plataforma de destino](../../standard/frameworks.md) para la que se actualiza la herramienta.

`-g|--global`

Especifica que la actualización es para una herramienta del ámbito de los usuarios. No se puede combinar con la opción `--tool-path`. Si no especifica esta opción, debe especificar la opción `--tool-path`.

`-h|--help`

Imprime una corta ayuda para el comando.

`--tool-path <PATH>`

Especifica la ubicación en la que está instalada la herramienta global. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Si no especifica esta opción, debe especificar la opción `--global`.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool update -g dotnetsay`

Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en una carpeta específica de Windows:

`dotnet tool update dotnetsay --tool-path c:\global-tools`

Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en una carpeta específica de Linux/macOS:

`dotnet tool update dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Vea también

* [Herramientas globales de .NET Core](global-tools.md)