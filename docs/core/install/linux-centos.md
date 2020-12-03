---
title: 'Instalación de .NET en CentOS: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en CentOS.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b30aa206057107aa17fcd62e0f042f9fe3ad56dc
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031935"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a>Instalación del SDK y el entorno de ejecución de .NET en CentOS

.NET es compatible con CentOS. En este artículo se describe cómo instalar .NET en CentOS.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET admitidas actualmente en CentOS 7 y CentOS 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.

- El símbolo ✔️ indica que todavía se admite la versión de CentOS o de .NET.
- El símbolo ❌ indica que la versión de CentOS o de .NET no se admite en esa versión de CentOS.
- Si una versión de CentOS y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Las versiones siguientes de .NET ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a>Eliminación de versiones preliminares

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a>CentOS 8 ✔️

> [!TIP]
> .NET 5.0 todavía no está disponible en los repositorios de paquetes predeterminados, pero .NET Core 3.1 sí. Para instalar .NET Core 3.1, use el comando `dnf install` con el paquete adecuado, como `aspnetcore-runtime-3.1` o `dotnet-sdk-3.1`. Las siguientes instrucciones son para .NET 5.0.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/8/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a>CentOS 7 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.

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
