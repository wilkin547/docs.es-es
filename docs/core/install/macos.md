---
title: Instalación de .NET Core en macOS
description: Descubra qué versiones de macOS puede instalar en .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: 2900d98dbd30c51f689cdce37ea273ccc4f598b5
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/14/2020
ms.locfileid: "86308928"
---
# <a name="install-net-core-on-macos"></a>Instalación de .NET Core en macOS

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

En este artículo obtendrá información sobre cómo instalar .NET Core en macOS. .NET Core está formado por el entorno de ejecución y el SDK. El tiempo de ejecución se usa para ejecutar una aplicación de .NET Core, y puede o no incluirse con la aplicación. El SDK se usa para crear aplicaciones y bibliotecas de .NET Core. El entorno de ejecución de .NET Core siempre se instala con el SDK.

La versión más reciente de .NET Core es la 3.1.

> [!div class="button"]
> [Descargar .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a>Versiones compatibles

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de macOS que se admiten. Estas versiones se siguen admitiendo hasta que la versión de [.NET Core alcance la finalización del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).

- Con la marca ✔️ se indica que la versión de .NET Core se sigue admitiendo.
- Con la marca ❌ se indica que la versión de .NET Core no se admite.

| Sistema operativo          | .NET Core 2.1 | .NET Core 3.1 | .NET 5 (versión preliminar) |
|---------------------------|---------------|---------------|----------------|
| macOS 10.15 "Catalina"    | ✔️ 2.1 ([Notas de la versión][release-notes-21]) | ✔️ 3.1 ([Notas de la versión][release-notes-31]) | ✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50]) |
| macOS 10.14 "Mojave"      | ✔️ 2.1 ([Notas de la versión][release-notes-21]) | ✔️ 3.1 ([Notas de la versión][release-notes-31]) | ✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50]) |
| macOS 10.13 "High Sierra" | ✔️ 2.1 ([Notas de la versión][release-notes-21]) | ✔️ 3.1 ([Notas de la versión][release-notes-31]) | ✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50]) |
| macOS 10.12 "Sierra"      | ✔️ 2.1 ([Notas de la versión][release-notes-21]) | ❌ 3.1 ([Notas de la versión][release-notes-31]) | ❌ 5.0, versión preliminar ([Notas de la versión][release-notes-50]) |

## <a name="unsupported-releases"></a>Versiones no admitidas

Las siguientes versiones de .NET Core ya no se admiten ❌. aunque sus descargas siguen estando publicadas:

- 3.0 ([Notas de la versión][release-notes-30])
- 2.2 ([Notas de la versión][release-notes-22])
- 2.0 ([Notas de la versión][release-notes-20])

## <a name="runtime-information"></a>Información en tiempo de ejecución

El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core. Cuando un autor publica una aplicación, puede incluir el tiempo de ejecución. Si no lo hace, el usuario elige si quiere instalar el tiempo de ejecución.

Hay tres tiempos de ejecución distintos que se pueden instalar en macOS:

*Entorno de ejecución de ASP.NET Core*\
Ejecuta aplicaciones de ASP.NET Core. Incluye el entorno de ejecución de .NET Core.

*Entorno de ejecución de .NET Core*\
Este entorno de ejecución es el más sencillo y no incluye ningún otro. Le recomendamos encarecidamente que instale el *entorno de ejecución de ASP.NET Core* para conseguir la mejor compatibilidad con las aplicaciones de .NET Core.

> [!div class="button"]
> [Descarga del entorno de ejecución de .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a>Información del SDK

El SDK se usa para compilar y publicar aplicaciones y bibliotecas de .NET Core. La instalación del SDK incluye ambos [entornos de ejecución](#runtime-information): ASP.NET Core y .NET Core.

> [!div class="button"]
> [Download .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core) (Descarga del SDK de .NET Core)

## <a name="dependencies"></a>Dependencias

.NET Core es compatible con las versiones siguientes de macOS:

> [!NOTE]
> Un símbolo `+` representa la versión mínima.

| Versión de .NET Core | macOS                 | Arquitecturas |     |
| ----------------- | --------------------- | --------------| --- |
| 3.1               | High Sierra (10.13 y posteriores)  | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| 3.0               | High Sierra (10.13 y posteriores)  | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| 2.2               | Sierra (10.12 y posteriores)       | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| 2.1               | Sierra (10.12 y posteriores)       | x64 | [Más información](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador. Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.

Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK). A las versiones publicadas anteriores no se les ha concedido la certificación. Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).

## <a name="libgdiplus"></a>libgdiplus

Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.

Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS. Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a>Instalación mediante un instalador

macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:

- [CPU de x64 (64 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Descarga e instalación de forma manual

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar manualmente el SDK y el entorno de ejecución. La instalación manual se suele llevar a cabo durante las pruebas de integración continua. Para un desarrollador o usuario, generalmente es mejor usar un [instalador](https://dotnet.microsoft.com/download/dotnet-core).

Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente. En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:

- ✔️ [Descargas de la versión preliminar de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)
- ✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- ✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)
- [Todas las descargas de .NET Core](https://dotnet.microsoft.com/download/dotnet-core)

A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET Core. Luego, asegúrese de que .NET Core esté en PATH.

Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET Core. Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo. El nombre del archivo puede ser distinto en función de lo que haya descargado.

**Use el comando siguiente para extraer el entorno de ejecución**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

**Use el comando siguiente para extraer el SDK**:

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.
>
> Puede editar el perfil del shell para agregar los comandos de forma permanente. Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente. Por ejemplo:
>
> - **Shell de Bash**: *~/.bash_profile*, *~/.bashrc*
> - **Shell de Korn**: *~/.kshrc* or *.profile*
> - **Shell de Z**: *~/.zshrc* or *.zprofile*
>
> Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente. Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.
>
> Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.

Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.

## <a name="install-with-visual-studio-for-mac"></a>Instalación con Visual Studio para Mac

Visual Studio para Mac instala el SDK de .NET Core cuando se selecciona la carga de trabajo **.NET Core**. Para empezar con el desarrollo en .NET Core en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation). Para obtener la versión más reciente, .NET Core 3.1, se debe usar la versión preliminar de Visual Studio para Mac 8.4.

[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

## <a name="install-alongside-visual-studio-code"></a>Instalación junto con Visual Studio Code

Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio. Visual Studio Code está disponible para Windows, macOS y Linux.

Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.

01. [Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).
01. [Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

## <a name="install-with-bash-automation"></a>Instalación mediante la automatización de Bash

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Puede elegir una versión concreta especificando el modificador `current`. Incluya el modificador `runtime` para instalar un entorno de ejecución. De lo contrario, el script instala el [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad. El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.

## <a name="docker"></a>Docker

Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host. Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.

.NET Core puede ejecutarse en un contenedor de Docker. Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/). Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.

Microsoft ofrece imágenes que se adaptan a escenarios específicos. Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.

Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Pasos siguientes

- [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md?pivots=os-macos).
- [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).
- [Tutorial: Introducción a macOS](../tutorials/using-on-mac-vs.md).
- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
