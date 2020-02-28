---
title: Comando dotnet tool install
description: El comando dotnet tool install instala la herramienta especificada de .NET Core en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 2705defe9b77009ca1411da28dd86d144ccc19e6
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543474"
---
# <a name="dotnet-tool-install"></a>dotnet tool install

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool install`: instala la [herramienta de .NET Core](global-tools.md) especificada en el equipo.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool install <PACKAGE_NAME> <-g|--global> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> <--tool-path> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <PACKAGE_NAME> [--add-source] [--configfile] [--framework] [-v|--verbosity] [--version]
dotnet tool install <-h|--help>
```

## <a name="description"></a>Descripción

El comando `dotnet tool install` permite instalar en el equipo herramientas de .NET Core. Para usar el comando, especifique una de las siguientes opciones de instalación:

* Para instalar una herramienta global en la ubicación predeterminada, use la opción `--tool-path`.
* Para instalar una herramienta global en una ubicación personalizada, use la opción `--tool-path`.
* Para instalar una herramienta local, omita las opciones `--global` y `--tool-path`.

**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**

Las herramientas globales se instalan en los siguientes directorios de forma predeterminada cuando se especifica la opción `-g` o `--global`:

| SO          | Ruta de acceso                          |
|-------------|-------------------------------|
| Linux/macOS | `$HOME/.dotnet/tools`         |
| Windows     | `%USERPROFILE%\.dotnet\tools` |

Las herramientas locales se agregan a un archivo *tool-manifest.json* en un directorio *.config* en el directorio actual. Si aún no existe un archivo de manifiesto, créelo ejecutando el siguiente comando:

```dotnetcli
dotnet new tool-manifest
```

Para obtener más información, vea [Instalación de una herramienta local](global-tools.md#install-a-local-tool).

## <a name="arguments"></a>Argumentos

- **`PACKAGE_NAME`**

  Nombre o identificador del paquete NuGet que contiene la herramienta de .NET Core que se quiere instalar.

## <a name="options"></a>Opciones

- **`add-source <SOURCE>`**

  Agrega un origen de paquete NuGet adicional que se usará durante la instalación.

- **`configfile <FILE>`**

  El archivo de configuración de NuGet (*nuget.config*) que se usará.

- **`framework <FRAMEWORK>`**

  Especifica el [marco de destino](../../standard/frameworks.md) para instalar la herramienta. De forma predeterminada, el SDK de .NET Core intenta elegir la plataforma de destino más apropiada.

- **`-g|--global`**

  Especifica que la instalación se realiza en todos los usuarios. No se puede combinar con la opción `--tool-path`. Al omitir `--global` y `--tool-path`, se especifica la instalación de una herramienta local. 

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`tool-path <PATH>`**

  Especifica la ubicación de donde se tiene que instalar la herramienta global. PATH puede ser una ruta absoluta o relativa. Si la ruta no existe, el comando intenta crearla. Al omitir `--global` y `--tool-path`, se especifica la instalación de una herramienta local. 

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

- **`--version <VERSION_NUMBER>`**

  La versión de la herramienta que se va instalar. De forma predeterminada, se instala la versión estable más reciente del paquete. Utilice esta opción para instalar la versión preliminar o versiones anteriores de la herramienta.

## <a name="examples"></a>Ejemplos

- **`dotnet tool install -g dotnetsay`**

  Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en la ubicación predeterminada.

- **`dotnet tool install dotnetsay --tool-path c:\global-tools`**

  Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en un directorio específico de Windows.

- **`dotnet tool install dotnetsay --tool-path ~/bin`**

  Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta global en un directorio específico de Linux/macOS.

- **`dotnet tool install -g dotnetsay --version 2.0.0`**

  Instala la versión 2.0.0 de [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como la herramienta global.

- **`dotnet tool install dotnetsay`**

  Instala [dotnetsay](https://www.nuget.org/packages/dotnetsay/) como herramienta local del directorio actual.

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
