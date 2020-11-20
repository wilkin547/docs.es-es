---
title: Instalación de .NET en distribuciones de Linux
description: Obtenga información sobre qué distribuciones de Linux admiten la instalación de .NET en Linux.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 6354ef6f0f9af2126312683893d6705b3b4c70f4
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594526"
---
# <a name="install-net-on-linux"></a>Instalación de .NET en Linux

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

.NET está disponible en diferentes distribuciones de Linux. La mayoría de las plataformas y distribuciones de Linux tienen una versión principal cada año, y la mayoría proporcionan un administrador de paquetes que se usa para instalar .NET. En este artículo se describe lo que se admite actualmente y el administrador de paquetes que se usa.

El resto de este artículo es un desglose de cada una de las principales distribuciones de Linux que admite .NET. Todas las versiones de .NET siguen siendo compatibles hasta que la [versión de .NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la distribución de Linux llega al final del ciclo de vida.

Para conseguir la mejor compatibilidad, elija una versión de lanzamiento a largo plazo (LTS).

## <a name="unsupported-releases"></a>Versiones no admitidas

Las versiones siguientes de .NET ya ❌ no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

Estas versiones no admitidas no se detallan en las secciones siguientes y los resultados pueden variar si intenta instalarlas.

## <a name="alpine"></a>Alpine

No hay instaladores para Alpine. Debe usar el [script de instalación](linux-alpine.md#scripted-install) o seguir las instrucciones de [instalación manual](linux-alpine.md#manual-install).

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Alpine en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- El símbolo ✔️ indica que todavía se admite la versión de Alpine o de .NET.
- El símbolo ❌ indica que la versión de Alpine o de .NET no se admite en esa versión de Alpine.
- Si una versión de Alpine y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Alpine                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|-----------------------------|---------------|---------------|----------------|
| ✔️ [3.12](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [3.11](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [3.10](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [3.9](linux-alpine.md)   | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [3.8](linux-alpine.md)   | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |

Para obtener más información, vea [Instalación de .NET en Alpine](linux-alpine.md).

## <a name="centos"></a>CentOS

CentOS 7 usa Yum como administrador de paquetes y CentOS 8 emplea DNF.

En la tabla siguiente se muestra una lista de las versiones de .NET admitidas actualmente en CentOS 7 y CentOS 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-centos.md#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](linux-centos.md#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Para obtener más información, vea [Instalación de .NET en CentOS](linux-centos.md).

## <a name="debian"></a>Debian

Debian usa APT (herramienta avanzada de paquetes) como administrador de paquetes.

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Debian en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).

- El símbolo ✔️ indica que todavía se admite la versión de Debian o de .NET.
- El símbolo ❌ indica que la versión de Debian o de .NET no se admite en esa versión de Debian.
- Si una versión de Debian y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](linux-debian.md#debian-10-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [9](linux-debian.md#debian-9-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [8](linux-debian.md#debian-8-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |

Para obtener más información, vea [Instalación de .NET en Debian](linux-debian.md).

## <a name="fedora"></a>Fedora

Fedora usa DNF como administrador de paquetes.

En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Fedora en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).

- El símbolo ✔️ indica que todavía se admite la versión de Fedora o de .NET.
- El símbolo ❌ indica que la versión de Fedora o de .NET no se admite en esa versión de Fedora.
- Si una versión de Fedora y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Fedora                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [33](linux-fedora.md#fedora-33-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [31](linux-fedora.md#fedora-31-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [29](linux-fedora.md#fedora-29-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [28](linux-fedora.md#fedora-28-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [27](linux-fedora.md#fedora-27-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |

Para obtener más información, vea [Instalación de .NET en Fedora](linux-fedora.md).

## <a name="opensuse"></a>openSUSE

openSUSE usa zypper como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con openSUSE 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-opensuse.md#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Para obtener más información, vea [Instalación de .NET en openSUSE](linux-opensuse.md).

## <a name="red-hat"></a>Red Hat

Red Hat Enterprise Linux (RHEL) usa yum (RHEL 7) y DNF (RHEL 8) como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con RHEL 7 y RHEL 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.

- El símbolo ✔️ indica que todavía se admite la versión de RHEL o de .NET.
- El símbolo ❌ indica que la versión de RHEL o de .NET no se admite en esa versión de RHEL.
- Si una versión de RHEL y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-rhel.md#rhel-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](linux-rhel.md#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](linux-rhel.md#rhel-7--net-core-31)        | ✔️ [5.0](linux-rhel.md#rhel-7--net-50) |

Para obtener más información, vea [Instalación de .NET en RHEL](linux-rhel.md).

## <a name="sles"></a>SLES

SLES usa zypper como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente en SLES 12 SP2 y SLES 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.

- El símbolo ✔️ indica que todavía se admite la versión de SLES o de .NET.
- El símbolo ❌ indica que la versión de SLES o de .NET no se admite en esa versión de SLES.
- Si una versión de SLES y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-sles.md#sles-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [12 SP2](linux-sles.md#sles-12-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Para obtener más información, vea [Instalación de .NET en SLES](linux-sles.md).

## <a name="ubuntu"></a>Ubuntu

Ubuntu usa APT (herramienta avanzada de paquetes) como administrador de paquetes.

En la tabla siguiente se representa el estado de compatibilidad de Ubuntu y .NET.

- El símbolo ✔️ indica que todavía se admite la versión de Ubuntu o de .NET.
- El símbolo ❌ indica que la versión de Ubuntu o de .NET no se admite en esa versión de Ubuntu.
- Si una versión de Ubuntu y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20.10](linux-ubuntu.md#2010-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [20.04 (LTS)](linux-ubuntu.md#2004-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [19.10](linux-ubuntu.md#1910-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [19.04](linux-ubuntu.md#1904-)       | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 |
| ❌ [18.10](linux-ubuntu.md#1810-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ✔️ [18.04 (LTS)](linux-ubuntu.md#1804-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ❌ [17.10](linux-ubuntu.md#1710-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [17.04](linux-ubuntu.md#1704-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ❌ [16.10](linux-ubuntu.md#1610-)       | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 |
| ✔️ [16.04 (LTS)](linux-ubuntu.md#1604-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |

Para obtener más información, vea [Instalación de .NET en Ubuntu](linux-ubuntu.md).

## <a name="next-steps"></a>Pasos siguientes

- [Procedimiento para comprobar que .NET ya está instalado](how-to-detect-installed-versions.md?pivots=os-linux).
- [Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).
- [Tutorial: Inclusión de una aplicación de .NET en un contenedor](../docker/build-container.md).
