---
title: 'Instalación de .NET en Fedora: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Fedora.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: f7422941af7e39d69d286a0f79920b025c1bf9c0
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031909"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a>Instalación del SDK y el entorno de ejecución de .NET en Fedora

.NET es compatible con Fedora. En este artículo se describe cómo instalar .NET en Fedora. Cuando una versión de Fedora no es compatible, .NET deja de ser compatible con esa versión. Pero estas instrucciones pueden ayudarle a conseguir que .NET se ejecute en esas versiones, aunque no se admita.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).

- El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.
- El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.
- Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Fedora               | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|----------------------|---------------|---------------|----------|
| ✔️ [33](#fedora-33-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [32](#fedora-32-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [31](#fedora-31-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [30](#fedora-30-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [29](#fedora-29-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [28](#fedora-28-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [27](#fedora-27-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |

Las versiones siguientes de .NET ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Eliminación de versiones preliminares

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-33-"></a>Fedora 33 ✔️

> [!TIP]
> .NET Core 3.1 está disponible en los repositorios de paquetes predeterminados para Fedora 33. Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`. .NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-32-"></a>Fedora 32 ✔️

> [!TIP]
> .NET Core 3.1 está disponible en los repositorios de paquetes predeterminados para Fedora 32. Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`. .NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="fedora-31-"></a>Fedora 31 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a>Fedora 30 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a>Fedora 29 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a>Fedora 28 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a>Fedora 27 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.

### <a name="unable-to-find-package"></a>No se puede encontrar el paquete

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Dependencias

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a>Instalación con script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalación manual

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
