---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: d3f7083366e2019d01884b5dff6e60d05ed565dd
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768292"
---
# <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

En este artículo, obtendrá información sobre cómo descargar e instalar el entorno de ejecución de .NET Core. El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a>Instalación mediante un instalador

Windows tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:

- [CPU de x64 (64 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [CPU de x86 (32 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a>Instalación mediante un instalador

macOS tiene instaladores independientes que se pueden usar para instalar el entorno de ejecución de .NET Core 3.1:

- [CPU de x64 (64 bits)](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a>Descarga e instalación de forma manual

Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar manualmente el entorno de ejecución.

Para instalar el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar [descargue](#all-net-core-downloads) una versión binaria de .NET Core. Después, abra un terminal y ejecute los comandos siguientes. Se supone que el entorno de ejecución se ha descargado al archivo `~/Downloads/dotnet-runtime.pkg`.

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a>Instalar en Linux

Este artículo se retirará pronto. En este momento se reemplaza por [Instalación de .NET Core en Linux](linux.md).

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a>Instalación mediante la automatización de PowerShell

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Puede elegir una versión concreta especificando el modificador `Channel`. Incluya el modificador `Runtime` para instalar un entorno de ejecución. De lo contrario, el script instala el [SDK](sdk.md).

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad. El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.

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

## <a name="install-with-bash-automation"></a>Instalación mediante la automatización de Bash

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Puede elegir una versión concreta especificando el modificador `current`. Incluya el modificador `runtime` para instalar un entorno de ejecución. De lo contrario, el script instala el [SDK](sdk.md).

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad. El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.

::: zone-end

## <a name="all-net-core-downloads"></a>Todas las descargas de .NET Core

Puede descargar e instalar .NET Core directamente con uno de los vínculos siguientes:

- [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a>Docker

Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host. Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.

.NET Core puede ejecutarse en un contenedor de Docker. Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/). Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.

Microsoft ofrece imágenes que se adaptan a escenarios específicos. Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.

Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).

## <a name="next-steps"></a>Pasos siguientes

- [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).
