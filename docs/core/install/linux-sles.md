---
title: 'Instalación de .NET Core en SLES: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en SLES.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: b2eab6a0305d492e37e1b33d02be43ca41d42b6f
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602793"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a>Instalación del SDK o de .NET Core Runtime en SLES

.NET Core es compatible con SLES. En este artículo se describe cómo instalar .NET Core en SLES.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente en SLES 12 SP 2 y SLES 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.

- Una ✔️ indica que todavía se admite la versión de SLES o de .NET Core.
- Una ❌ indica que la versión de SLES o de .NET Core no se admite en esa versión de SLES.
- Cuando una versión de SLES y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](#sles-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [12 SP2](#sles-12-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a>SLES 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

Actualmente, el paquete de instalación del repositorio de Microsoft de SLES 15 instala el archivo *microsoft-prod.repo* en el directorio incorrecto, lo que impide que zypper pueda encontrar los paquetes de .NET Core. Para corregir este problema, cree un symlink en el directorio apropiado.

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a>SLES 12 ✔️

.NET Core necesita SP2 como mínimo para la familia SLES 12.

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

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
