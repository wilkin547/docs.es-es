---
title: 'Instalación de .NET en Fedora: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en Fedora.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970829"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a>Instalación del SDK y el entorno de ejecución de .NET en Fedora

.NET es compatible con Fedora. En este artículo se describe cómo instalar .NET en Fedora. Cuando una versión de Fedora no es compatible, .NET deja de ser compatible con esa versión.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a>Instalación de .NET 5.0

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

**Fedora 32**

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

**Fedora 33**

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a>Instalación de .NET Core 3.1

La última versión de .NET disponible en los repositorios de paquetes predeterminados para Fedora es .NET Core 3.1.

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).

- El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.
- El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.
- Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Versión de .NET  | Fedora 33 ✔️ | 32 ✔️ | 31 ❌ | 30 ❌ | 29 ❌ | 28 ❌ | 27 ❌ |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| .NET 5.0      | ✔️        | ✔️ | ❌|❌ |❌ |❌  |❌ |
| .NET Core 3.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |❌  |❌ |
| .NET Core 2.1 | ✔️        | ✔️ | ✔️|✔️ |✔️ |✔️  |✔️ |

Las versiones siguientes de .NET ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Eliminación de versiones preliminares

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a>Dependencias

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a>Instalación en distribuciones anteriores

Las versiones anteriores de Fedora no contienen .NET Core en los repositorios de paquetes predeterminados. Puede instalar .NET con un [snap](linux-snap.md), mediante el [script _dotnet-install.sh_](linux-scripted-manual.md#scripted-install) o con el repositorio de Microsoft para instalar .NET:

01. En primer lugar, agregue la clave de firma de Microsoft a la lista de claves de confianza.

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. Después, agregue el repositorio de paquetes de Microsoft. El origen del repositorio se basa en la versión que tenga de Fedora.

    | Versión de Fedora | Repositorio de paquetes |
    | -------------- | ------- |
    | 31             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | 30             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | 29             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | 28             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | 27             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede recibir al usar el administrador de paquetes para instalar .NET o .NET Core.

### <a name="unable-to-find-package"></a>No se puede encontrar el paquete

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para habilitar la finalización con tabulación para la CLI de .NET](../tools/enable-tab-autocomplete.md)
- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
