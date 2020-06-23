---
title: 'Instalación de .NET Core en CentOS: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en CentOS.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 743bd4ce47fdecef512f9605d8ec5503eb6da9ba
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602883"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-centos"></a>Instalación del SDK de .NET Core o .NET Core Runtime en CentOS

.NET Core es compatible con CentOS. En este artículo se describe cómo instalar .NET Core en CentOS.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET Core admitidas actualmente en CentOS 7 y CentOS 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.

- Una ✔️ indica que todavía se admite la versión de CentOS o de .NET Core.
- Una ❌ indica que la versión de CentOS o de .NET Core no se admite en esa versión de CentOS.
- Cuando una versión de CentOS y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [7](#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a>CentOS 8 ✔️

.NET Core 3.1 está disponible en los repositorios de paquetes predeterminados de CentOS 8.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="centos-7-"></a>CentOS 7 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-31](includes/linux-install-31-yum.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

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
