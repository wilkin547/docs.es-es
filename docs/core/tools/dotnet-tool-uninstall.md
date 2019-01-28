---
title: Comando dotnet tool uninstall
description: El comando dotnet tool uninstall desinstala del equipo la herramienta global especificada de .NET Core.
ms.date: 05/29/2018
ms.openlocfilehash: 4d53d305131e3399ab5d9c19f9319f3ba3544c19
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54680928"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a>nombre

`dotnet tool uninstall`: desinstala la [herramienta global de .NET Core](global-tools.md) especificada del equipo.

## <a name="synopsis"></a>Sinopsis

```console
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool uninstall` permite desinstalar del equipo herramientas globales de .NET Core. Para utilizar el comando, especifique que quiere quitar una herramienta de los usuarios con la opción `--global` o especifique una ruta de acceso en la que está instalada la herramienta usando para ello la opción `--tool-path`.

## <a name="arguments"></a>Argumentos

`PACKAGE_NAME`

Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere desinstalar. Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opciones

`-g|--global`

Especifica que la herramienta que se va a quitar es de una instalación en el ámbito de los usuarios. No se puede combinar con la opción `--tool-path`. Si no especifica esta opción, debe especificar la opción `--tool-path`.

`-h|--help`

Imprime una corta ayuda para el comando.

`--tool-path <PATH>`

Especifica la ubicación de donde se tiene que desinstalar la herramienta global. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Si no especifica esta opción, debe especificar la opción `--global`.

## <a name="examples"></a>Ejemplos

Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/):

`dotnet tool uninstall -g dotnetsay`

Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de una carpeta específica de Windows:

`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`

Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de una carpeta específica de Linux/macOS:

`dotnet tool uninstall dotnetsay --tool-path ~/bin`

## <a name="see-also"></a>Vea también

- [Herramientas globales de .NET Core](global-tools.md)
