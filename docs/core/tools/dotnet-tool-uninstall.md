---
title: Comando dotnet tool uninstall
description: El comando dotnet tool uninstall desinstala del equipo la herramienta especificada de .NET Core.
ms.date: 02/14/2020
ms.openlocfilehash: 82dad0206d9c3e2ef0f41c353f4a608f10e4f127
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543448"
---
# <a name="dotnet-tool-uninstall"></a>dotnet tool uninstall

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool uninstall`: desinstala la [herramienta de .NET Core](global-tools.md) especificada del equipo.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool uninstall <PACKAGE_NAME> <-g|--global>
dotnet tool uninstall <PACKAGE_NAME> <--tool-path>
dotnet tool uninstall <PACKAGE_NAME>
dotnet tool uninstall <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool uninstall` permite desinstalar del equipo herramientas de .NET Core. Para usar el comando, especifique una de las siguientes opciones:

* Para desinstalar una herramienta global que se instaló en la ubicación predeterminada, use la opción `--global`.
* Para desinstalar una herramienta global que se instaló en una ubicación personalizada, use la opción `--tool-path`.
* Para desinstalar una herramienta local, omita las opciones `--global` y `--tool-path`.

**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**

## <a name="arguments"></a>Argumentos

- **`PACKAGE_NAME`**

  Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere desinstalar. Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opciones

- **`-g|--global`**

  Especifica que la herramienta que se va a quitar es de una instalación en el ámbito de los usuarios. No se puede combinar con la opción `--tool-path`. Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a quitar es una herramienta local. 

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--tool-path <PATH>`**

  Especifica la ubicación de donde se tiene que desinstalar la herramienta. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a quitar es una herramienta local. 

## <a name="examples"></a>Ejemplos

- **`dotnet tool uninstall -g dotnetsay`**

  Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool uninstall dotnetsay --tool-path c:\global-tools`**

  Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de un directorio específico de Windows.

- **`dotnet tool uninstall dotnetsay --tool-path ~/bin`**

  Desinstala la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) de un directorio específico de Linux/macOS.

- **`dotnet tool uninstall dotnetsay`**

  Desinstala la herramienta local [dotnetsay](https://www.nuget.org/packages/dotnetsay/) del directorio actual.

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
