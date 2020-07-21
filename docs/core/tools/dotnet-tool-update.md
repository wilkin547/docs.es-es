---
title: Comando dotnet tool update
description: El comando dotnet tool update actualiza la herramienta de .NET Core en su equipo.
ms.date: 07/08/2020
ms.openlocfilehash: a212fbb40af68019c1bc9a63963d960292be6b08
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308876"
---
# <a name="dotnet-tool-update"></a>dotnet tool update

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet tool update`: actualiza la [herramienta de .NET Core](global-tools.md) especificada en el equipo.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet tool update <PACKAGE_ID> -g|--global
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --tool-path <PATH>
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update <PACKAGE_ID> --local
    [--add-source <SOURCE>] [--configfile <FILE>]
    [--disable-parallel] [--framework <FRAMEWORK>]
    [--ignore-failed-sources] [--interactive] [--no-cache]
    [--tool-manifest <PATH>]
    [-v|--verbosity <LEVEL>] [--version <VERSION>]

dotnet tool update -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet tool update` permite actualizar las herramientas de .NET Core en su equipo a la versión estable más reciente del paquete. El comando desinstala y vuelve a instalar una herramienta, actualizándola de facto. Para usar el comando, especifique una de las siguientes opciones:

* Para actualizar una herramienta global que se instaló en la ubicación predeterminada, use la opción `--global`.
* Para actualizar una herramienta global que se instaló en una ubicación personalizada, use la opción `--tool-path`.
* Para actualizar una herramienta local, use la opción `--local`.

**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**

## <a name="arguments"></a>Argumentos

- **`PACKAGE_ID`**

  Nombre o identificador del paquete de NuGet que contiene la herramienta global de .NET Core que se quiere actualizar. Para conocer el nombre el paquete, use el comando [dotnet tool list](dotnet-tool-list.md).

## <a name="options"></a>Opciones

- **`--add-source <SOURCE>`**

  Agrega un origen de paquete NuGet adicional que se usará durante la instalación.

- **`--configfile <FILE>`**

  El archivo de configuración de NuGet (*nuget.config*) que se usará.

- **`--disable-parallel`**

  Impide que se restauren varios proyectos en paralelo.

- **`--framework <FRAMEWORK>`**

  Especifica la [plataforma de destino](../../standard/frameworks.md) para la que se actualiza la herramienta.

- **`--ignore-failed-sources`**

  Indica que los errores de origen de paquete se traten como advertencias.

- **`--interactive`**

  Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).

- **`--local`**

  Actualice la herramienta y el manifiesto de la herramienta local. No se puede combinar con las opciones `--global` o `--tool-path`.

- **`--no-cache`**

  Indica que no se almacenen en caché los paquetes ni las solicitudes HTTP.

- **`--tool-manifest <PATH>`**

  Ruta de acceso al archivo de manifiesto.

- **`--tool-path <PATH>`**

  Especifica la ubicación en la que está instalada la herramienta global. PATH puede ser una ruta absoluta o relativa. No se puede combinar con la opción `--global`. Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.

- **`--version <VERSION>`**

  El intervalo de versiones del paquete de herramientas al que se actualiza. Esto no se puede usar para degradar versiones, primero debe `uninstall` versiones más recientes.

- **`-g|--global`**

  Especifica que la actualización es para una herramienta del ámbito de los usuarios. No se puede combinar con la opción `--tool-path`. Al omitir `--global` y `--tool-path`, se especifica que la herramienta que se va a actualizar es una herramienta local.

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`-v|--verbosity <LEVEL>`**

  Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

- **`dotnet tool update -g dotnetsay`**

  Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/).

- **`dotnet tool update dotnetsay --tool-path c:\global-tools`**

  Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Windows.

- **`dotnet tool update dotnetsay --tool-path ~/bin`**

  Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) ubicada en un directorio específico de Linux/macOS.

- **`dotnet tool update dotnetsay`**

  Actualiza la herramienta local [dotnetsay](https://www.nuget.org/packages/dotnetsay/) instalada para el directorio actual.

- **`dotnet tool update -g dotnetsay --version 2.0.*`**

  Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) a la última versión de revisión, con una versión principal de `2` y una versión secundaria de `0`.

- **`dotnet tool update -g dotnetsay --version (2.0.*,2.1.4)`**

  Actualiza la herramienta global [dotnetsay](https://www.nuget.org/packages/dotnetsay/) a la versión más baja del intervalo especificado `(> 2.0.0 && < 2.1.4)`; se instalará la versión `2.1.0`. Para obtener más información sobre los intervalos de versiones semánticas, consulte [Intervalos de versiones de empaquetado de NuGet](/nuget/concepts/package-versioning#version-ranges).

## <a name="see-also"></a>Vea también

- [Herramientas de .NET Core](global-tools.md)
- [Versionamiento semántico](https://semver.org)
- [Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core](global-tools-how-to-use.md)
- [Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core](local-tools-how-to-use.md)
