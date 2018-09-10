---
title: Comando dotnet tool install - CLI de .NET Core
description: El comando dotnet tool install instala la herramienta global especificada de .NET Core en el equipo.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: aad5a3e815936749d90f40975a8b13d34e89386c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512200"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nombre

`dotnet tool install`: instala la [herramienta global de .NET Core](global-tools.md) especificada en el equipo.

## <a name="synopsis"></a>Sinopsis

```console
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool install` permite instalar en el equipo herramientas globales de .NET Core. Para utilizar el comando, especifique que quiere una instalación en todos los usuarios con la opción `--global`, o bien especifique una ruta para instalarla usando para ello la opción `--tool-path`.

Las herramientas globales se instalan en los siguientes directorios de forma predeterminada cuando se especifica la opción `-g` (o `--global`):

| SO          | Ruta de acceso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

## <a name="arguments"></a>Argumentos

`PACKAGE_NAME`

Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere instalar.

## <a name="options"></a>Opciones

`--add-source <SOURCE>`

Agrega un origen de paquete NuGet adicional que se usará durante la instalación.

`--configfile <FILE>`

El archivo de configuración de NuGet (*nuget.config*) que se usará.

`--framework <FRAMEWORK>`

Especifica el [marco de destino](../../standard/frameworks.md) para instalar la herramienta. De forma predeterminada, el SDK de .NET Core intenta elegir la plataforma de destino más apropiada.

`-g|--global`

Especifica que la instalación se realiza en todos los usuarios. No se puede combinar con la opción `--tool-path`. Si no especifica esta opción, debe especificar la opción `--tool-path`.

`-h|--help`

Imprime una corta ayuda para el comando.

`--tool-path <PATH>`

Especifica la ubicación de donde se tiene que instalar la herramienta global. PATH puede ser una ruta absoluta o relativa. Si la ruta no existe, el comando intenta crearla. No se puede combinar con la opción `--global`. Si no especifica esta opción, debe especificar la opción `--global`.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

`--version <VERSION_NUMBER>`

La versión de la herramienta que se va instalar. De forma predeterminada, se instala la versión estable más reciente del paquete. Utilice esta opción para instalar la versión preliminar o versiones anteriores de la herramienta.

## <a name="examples"></a>Ejemplos

Instala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) en la ubicación predeterminada:

`dotnet tool install -g dotnetsay`

Instala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) en una carpeta específica de Windows:

`dotnet tool install dotnetsay --tool-path c:\global-tools`

Instala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) en una carpeta específica de Linux/macOS:

`dotnet tool install dotnetsay --tool-path ~/bin`

Instala la versión 2.0.0 de la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool install -g dotnetsay --version 2.0.0`

## <a name="see-also"></a>Vea también

* [Herramientas globales de .NET Core](global-tools.md)