---
title: 'Instalación de .NET Core en Fedora 32 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el runtime de .NET Core en Fedora 32.
author: thraka
ms.author: adegeo
ms.date: 04/28/2020
ms.openlocfilehash: e5a69bf00e7e2969143e044aea4c9938fd5a610d
ms.sourcegitcommit: e09dbff13f0b21b569a101f3b3c5efa174aec204
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/01/2020
ms.locfileid: "82624955"
---
# <a name="fedora-32-package-manager---install-net-core"></a>Administrador de paquetes de Fedora 32: instalación de .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

En este artículo se explica cómo usar un administrador de paquetes para instalar .NET Core en Fedora 32.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

A partir de Fedora 32, .NET Core 3.1 está disponible en los repositorios de paquetes predeterminados de Fedora.

## <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

Instale el SDK de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo dnf install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Instalación del entorno de ejecución de ASP.NET Core

Instalación del entorno de ejecución de ASP.NET En el terminal, ejecute el comando siguiente.

```bash
sudo dnf install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

Instale el entorno de ejecución de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo dnf install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

Para instalar otras versiones de .NET Core, instale manualmente el [SDK de .NET Core](sdk.md?pivots=os-linux#download-and-manually-install) o el [entorno de ejecución de .NET Core](runtime.md?pivots=os-linux#download-and-manually-install).
