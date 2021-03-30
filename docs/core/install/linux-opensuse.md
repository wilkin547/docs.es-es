---
title: 'Instalación de .NET en openSUSE: .NET'
description: En este artículo se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en openSUSE.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: d238054a217a7295594db856d5497982572af377
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873957"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a>Instalación del SDK y el entorno de ejecución de .NET en openSUSE

.NET es compatible con openSUSE. En este artículo se describe cómo instalar .NET en openSUSE.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con openSUSE 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.

- El símbolo ✔️ indica que todavía se admite la versión de openSUSE o de .NET.
- El símbolo ❌ indica que la versión de openSUSE o de .NET no se admite en esa versión de openSUSE.
- Si una versión de openSUSE y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Las versiones siguientes de .NET ya no se admiten. aunque sus descargas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Eliminación de versiones preliminares

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="opensuse-15-"></a>openSUSE 15 ✔️

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET.

### <a name="unable-to-find-package"></a>No se puede encontrar el paquete

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a>Dependencias

Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente. Pero si instala manualmente .NET o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:

- krb5
- libicu
- libopenssl1_0_0

Si la versión de OpenSSL del entorno de tiempo de ejecución de destino es 1.1 o más reciente, deberá instalar **compat-openssl10**.

Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/main/Documentation/self-contained-linux-apps.md).

En el caso de las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:

- [libgdiplus (versión 6.0.1 o posterior)](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para habilitar la finalización con tabulación para la CLI de .NET](../tools/enable-tab-autocomplete.md)
- [Tutorial: Creación de una aplicación de consola con el SDK de .NET mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
