---
title: 'Instalación de .NET Core en openSUSE: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ccdb23ca1838d2c15c9a95b45c8505efe7a6df0e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539235"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a>Instalación del SDK de .NET Core o de .NET Core Runtime en openSUSE

.NET Core es compatible con openSUSE. En este artículo se describe cómo instalar .NET Core en openSUSE.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con openSUSE 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.

- Una ✔️ indica que todavía se admite la versión de openSUSE o de .NET Core.
- Una ❌ indica que la versión de openSUSE o de .NET Core no se admite en esa versión de openSUSE.
- Cuando una versión de openSUSE y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten. aunque sus descargas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a>openSUSE 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.

### <a name="unable-to-find-package"></a>No se puede encontrar el paquete

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a>Snap

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a>Dependencias

Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente. Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:

- krb5
- libicu
- libopenssl1_0_0

Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.

Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- [libgdiplus (versión 6.0.1 o posterior)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Instalación con script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalación manual

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
