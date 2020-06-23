---
title: 'Instalación de .NET Core en Debian: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Debian.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: c66d8e1daad4e59a766781b7117600352879b724
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602811"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a>Instalación del SDK de .NET Core o de .NET Core Runtime en Debian

En este artículo se describe cómo instalar .NET Core en Debian. Cuando una versión de Debian no es compatible, .NET Core deja de ser compatible con esa versión. Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Debian en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).

- Una ✔️ indica que todavía se admite la versión de Debian o de .NET Core.
- Una ❌ indica que la versión de Debian o de .NET Core no se admite en esa versión de Debian.
- Cuando una versión de Debian y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](#debian-10-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [9](#debian-9-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [8](#debian-8-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a>Debian 10 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a>Debian 9 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a>Debian 8 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a>SDK o entorno de ejecución de actualización de APT

Cuando hay disponible una nueva versión de revisión para .NET Core, basta con que la actualice mediante APT con los siguientes comandos:

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a>Solución de problemas de APT

En esta sección se proporciona información sobre los errores comunes que puede recibir al usar ATP para instalar .NET Core.

### <a name="unable-to-locate"></a>No se encuentra el elemento

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Dependencias

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a>Instalación con script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalación manual

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
