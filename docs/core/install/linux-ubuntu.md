---
title: 'Instalación de .NET Core en Ubuntu: .NET Core'
description: En este artículo se muestran las diversas maneras de instalar el SDK de .NET Core y .NET Core Runtime en Ubuntu.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7045d4d1c3585ba6d26c55ded4653775c9413841
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602727"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a>Instalación del SDK de .NET Core o de .NET Core Runtime en Ubuntu

.NET Core es compatible con Ubuntu. En este artículo se describe cómo instalar .NET Core en Ubuntu. Cuando una versión de Ubuntu no es compatible, .NET Core deja de ser compatible con esa versión. Sin embargo, estas instrucciones pueden ayudarle a conseguir que .NET Core se ejecute en esas versiones, aunque no se admita.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Ubuntu en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Ubuntu llegue al final del ciclo de vida](https://wiki.ubuntu.com/Releases).

- Una ✔️ indica que todavía se admite la versión de Ubuntu o de .NET Core.
- Una ❌ indica que la versión de Ubuntu o de .NET Core no se admite en esa versión de Ubuntu.
- Cuando una versión de Ubuntu y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20.04 (LTS)](#2004-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [19.10](#1910-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [19.04](#1904-)       | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [18.10](#1810-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ✔️ [18.04 (LTS)](#1804-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [17.10](#1710-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [17.04](#1704-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [16.10](#1610-)       | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ✔️ [16.04 (LTS)](#1604-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Las siguientes versiones de .NET Core ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a>20.04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a>19.10 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a>19.04 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a>18.10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a>18.04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a>17.10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a>17.04 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a>16.10 ❌

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a>16.04 ✔️

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

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
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
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

Al realizar la instalación con un administrador de paquetes, estas bibliotecas se instalan automáticamente. Sin embargo, si instala manualmente .NET Core o publica una aplicación independiente, deberá asegurarse de que estas bibliotecas estén instaladas:

- liblttng-ust0
- libcurl3 (para 14.x y 16.x)
- libcurl4 (para 18.x)
- libssl1.0.0
- libkrb5-3
- zlib1g
- libicu52 (para 14.x)
- libicu55 (para 16.x)
- libicu57 (para 17.x)
- libicu60 (para 18.x)

En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:

- libgdiplus (versión 6.0.1 o posteriores)

  > [!WARNING]
  > Puede instalar una versión reciente de *libgdiplus* agregando el repositorio Mono al sistema. Para obtener más información, vea <https://www.mono-project.com/download/stable/>.

## <a name="scripted-install"></a>Instalación con script

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a>Instalación manual

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a>Pasos siguientes

- [Tutorial: Creación de una aplicación de consola con el SDK de .NET Core mediante Visual Studio Code](../tutorials/with-visual-studio-code.md)
