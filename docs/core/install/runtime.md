---
title: 'Instalación del entorno de ejecución de .NET Core en Windows, Linux y macOS: .NET Core'
description: Obtenga información sobre cómo instalar .NET Core en Windows, Linux y macOS. Descubra las dependencias necesarias para ejecutar aplicaciones de .NET Core.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 8f4a895ad66dea3063a32f785e4c521196266978
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2019
ms.locfileid: "74998892"
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

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a>Instalación con un administrador de paquetes

Se puede instalar el entorno de ejecución de .NET Core con muchos de los administradores de paquetes comunes de Linux. Para obtener más información, vea [Administrador de paquetes de Linux: instalación de .NET Core](linux-package-manager-rhel7.md).

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

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a>Instalación mediante la automatización de Bash

Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución. Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).

El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1. Puede elegir una versión concreta especificando el modificador `current`. Incluya el modificador `runtime` para instalar un entorno de ejecución. De lo contrario, el script instala el [SDK](sdk.md).

```bash
./dotnet-install.sh --current 3.1 --runtime aspnetcore
```

> [!NOTE]
> El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad. El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.

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

- [Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md).
