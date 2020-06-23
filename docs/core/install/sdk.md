---
title: 'Instalación del SDK de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para desarrollar aplicaciones en .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: f8e5cc134d4132c83544effa7f1937f2a2c8d012
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596311"
---
# <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

En este artículo obtendrá información sobre cómo instalar el SDK de .NET Core. El SDK de .NET Core se usa para crear aplicaciones y bibliotecas de .NET Core. El entorno de ejecución de .NET Core siempre se instala con el SDK.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Instalación mediante un instalador

Windows tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:

- [CPU de x64 (64 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU de x86 (32 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Instalación mediante un instalador

macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:

- [CPU de x64 (64 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Descarga e instalación de forma manual

Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar el SDK de forma manual.

Para extraer el SDK y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core. Después, abra un terminal y ejecute los comandos siguientes. Se supone que el entorno de ejecución se ha descargado al archivo `~/Downloads/dotnet-sdk.pkg`.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a>Instalar en Linux

Este artículo se retirará pronto. En este momento se reemplaza por [Instalación de .NET Core en Linux](linux.md).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a>Instalación con Visual Studio

Si usa Visual Studio para desarrollar aplicaciones de .NET Core, en la tabla siguiente se describe la versión mínima necesaria de Visual Studio, basada en la versión del SDK de .NET Core de destino.

| Versión del SDK de .NET Core | Versión de Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.1                   | Visual Studio 2019, versión 16.4 o posterior. |
| 3.0                   | Visual Studio 2019, versión 16.3 o posterior. |
| 2.2                   | Visual Studio 2017, versión 15.9 o posterior. |
| 2.1                   | Visual Studio 2017, versión 15.7 o posterior. |

Si ya tiene Visual Studio instalado, puede comprobar la versión siguiendo los pasos que se detallan a continuación.

01. Abra Visual Studio.
01. Seleccione **Ayuda** > **Acerca de Microsoft Visual Studio**.
01. Lea el número de versión en el cuadro de diálogo **Acerca de**.

Visual Studio puede instalar el SDK y el entorno de ejecución de .NET Core más recientes.

- [Descargue Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).

### <a name="select-a-workload"></a>Selección de una carga de trabajo

Al instalar o modificar Visual Studio, seleccione una de las cargas de trabajo siguientes o más, en función del tipo de aplicación que quiera compilar:

- La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.
- La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.
- La carga de trabajo **Desarrollo de Azure** en la sección **Web y nube**.
- La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Móviles y de escritorio**.

[![Visual Studio 2019 para Windows con la carga de trabajo de .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)

## <a name="download-and-manually-install"></a>Descarga e instalación de forma manual

Para extraer el runtime y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core. A continuación, cree un directorio para la instalación, por ejemplo `%USERPROFILE%\dotnet`. Por último, extraiga el archivo zip descargado en ese directorio.

De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET Core no usarán la versión de .NET Core instalada de esta manera y debe elegir explícitamente usarla. Para ello, cambie las variables de entorno con las que se inicia una aplicación:

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.

Incluso cuando se establecen estas variables de entorno, .NET Core sigue teniendo en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación. Normalmente, el valor predeterminado es `C:\Program Files\dotnet`, que usan los instaladores. Puede indicar al motor en tiempo de ejecución que solo use la ubicación de instalación personalizada mediante la configuración de esta variable de entorno:

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a>Instalación con Visual Studio para Mac

Visual Studio para Mac instala el SDK de .NET Core cuando se selecciona la carga de trabajo **.NET Core**. Para empezar con el desarrollo en .NET Core en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation). Para obtener la versión más reciente, .NET Core 3.1, se debe usar la versión preliminar de Visual Studio para Mac 8.4.

[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)

::: zone-end

## <a name="install-alongside-visual-studio-code"></a>Instalación junto con Visual Studio Code

Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio. Visual Studio Code está disponible para Windows, macOS y Linux.

Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.

01. [Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).
01. [Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).
01. [Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Instalación mediante la automatización de PowerShell

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Instalación mediante la automatización de Bash

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del SDK. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Para instalar la versión actual de .NET Core, ejecute el script con el modificador siguiente.

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a>Todas las descargas de .NET Core

Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:

- [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Descargas de .NET Core 3.0](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [Descargas de .NET Core 2.2](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host. Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.

.NET Core puede ejecutarse en un contenedor de Docker. Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/). Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.

Microsoft ofrece imágenes que se adaptan a escenarios específicos. Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.

Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Pasos siguientes

::: zone pivot="os-windows"

- [Tutorial: Tutorial Hola mundo](../tutorials/with-visual-studio.md).
- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).

::: zone-end

::: zone pivot="os-macos"

- [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).
- [Tutorial: Introducción a macOS](../tutorials/using-on-mac-vs.md).
- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).

::: zone-end

::: zone pivot="os-linux"

- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).

::: zone-end
