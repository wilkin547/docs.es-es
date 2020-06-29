---
title: Instalación de distribuciones de .NET Core y de Linux
description: Conozca qué distribuciones de Linux admiten la instalación de .NET Core en Linux.
author: adegeo
ms.author: adegeo
ms.date: 06/01/2020
ms.openlocfilehash: 22c07c5a8263dd6059f415cb4d9e2915811351b0
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324640"
---
# <a name="install-net-core-on-linux"></a>Instalación de .NET Core en Linux

.NET Core está disponible en diferentes distribuciones de Linux. La mayoría de las plataformas y distribuciones de Linux tienen una versión principal cada año, y la mayoría proporcionan un administrador de paquetes que se usa para instalar .NET Core. En este artículo se describe lo que se admite actualmente y el administrador de paquetes que se usa.

El resto de este artículo es un desglose de cada una de las principales distribuciones de Linux que admite .NET Core. Todas estas versiones siguen siendo compatibles hasta que la [versión de .NET Core llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la distribución de Linux llega al final del ciclo de vida.

Para conseguir la mejor compatibilidad, elija una versión de lanzamiento a largo plazo (LTS).

## <a name="unsupported-releases"></a>Versiones no admitidas

Las siguientes versiones de .NET Core ya no se admiten ❌. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

Estas versiones no admitidas no se detallan en las secciones siguientes y los resultados pueden variar si intenta instalarlas.

## <a name="alpine"></a>Alpine

No hay instaladores para Alpine. Debe usar el [script de instalación](linux-alpine.md#scripted-install) o seguir las instrucciones de [instalación manual](linux-alpine.md#manual-install).

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Alpine en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Alpine llega al final del ciclo de vida](https://wiki.alpinelinux.org/wiki/Alpine_Linux:Releases).

- Una ✔️ indica que todavía se admite la versión de Alpine o de .NET Core.
- Una ❌ indica que la versión de Alpine o de .NET Core no se admite en esa versión de Alpine.
- Cuando una versión de Alpine y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Alpine                      | .NET Core 2.1 | .NET Core 3.1 | .NET 5 (versión preliminar) |
|-----------------------------|---------------|---------------|----------------|
| ✔️ [3.12](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [3.11](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [3.10](linux-alpine.md)  | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [3.9](linux-alpine.md)   | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [3.8](linux-alpine.md)   | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en Alpine](linux-alpine.md).

## <a name="centos"></a>CentOS

CentOS 7 usa Yum como administrador de paquetes y CentOS 8 emplea DNF.

En la tabla siguiente se muestra una lista de las versiones de .NET Core admitidas actualmente en CentOS 7 y CentOS 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de CentOS.

| CentOS                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-centos.md#centos-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [7](linux-centos.md#centos-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en CentOS](linux-centos.md).

## <a name="debian"></a>Debian

Debian usa APT (herramienta avanzada de paquetes) como administrador de paquetes.

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Debian en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Debian llegue al final del ciclo de vida](https://wiki.debian.org/DebianReleases).

- Una ✔️ indica que todavía se admite la versión de Debian o de .NET Core.
- Una ❌ indica que la versión de Debian o de .NET Core no se admite en esa versión de Debian.
- Cuando una versión de Debian y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Debian                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [10](linux-debian.md#debian-10-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [9](linux-debian.md#debian-9-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [8](linux-debian.md#debian-8-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en Debian](linux-debian.md).

## <a name="fedora"></a>Fedora

Fedora usa DNF como administrador de paquetes.

En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de Fedora en las que se admiten. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Fedora llegue al final del ciclo de vida](https://fedoraproject.org/wiki/End_of_life).

- Una ✔️ indica que todavía se admite la versión de Fedora o de .NET Core.
- Una ❌ indica que la versión de Fedora o de .NET Core no se admite en esa versión de Fedora.
- Cuando una versión de Fedora y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Fedora                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [32](linux-fedora.md#fedora-32-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [31](linux-fedora.md#fedora-31-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [30](linux-fedora.md#fedora-30-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [29](linux-fedora.md#fedora-29-) | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [28](linux-fedora.md#fedora-28-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [27](linux-fedora.md#fedora-27-) | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en Fedora](linux-fedora.md).

## <a name="opensuse"></a>openSUSE

openSUSE usa zypper como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con openSUSE 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de openSUSE.

- Una ✔️ indica que todavía se admite la versión de openSUSE o de .NET Core.
- Una ❌ indica que la versión de openSUSE o de .NET Core no se admite en esa versión de openSUSE.
- Cuando una versión de openSUSE y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| openSUSE                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|----------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-opensuse.md#opensuse-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en openSUSE](linux-opensuse.md).

## <a name="red-hat"></a>Red Hat

Red Hat Enterprise Linux (RHEL) usa yum (RHEL 7) y DNF (RHEL 8) como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente con RHEL 7 y RHEL 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.

- Una ✔️ indica que todavía se admite la versión de RHEL o de .NET Core.
- Una ❌ indica que la versión de RHEL o de .NET Core no se admite en esa versión de RHEL.
- Cuando una versión de RHEL y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| RHEL                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](linux-rhel.md#rhel-8-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [7](linux-rhel.md#rhel-7-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en RHEL](linux-rhel.md).

## <a name="sles"></a>SLES

SLES usa zypper como administrador de paquetes.

En la tabla siguiente se muestra una lista de las versiones de .NET Core compatibles actualmente en SLES 12 SP 2 y SLES 15. Estas versiones siguen siendo compatibles hasta que la versión de [.NET Core llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de SLES.

- Una ✔️ indica que todavía se admite la versión de SLES o de .NET Core.
- Una ❌ indica que la versión de SLES o de .NET Core no se admite en esa versión de SLES.
- Cuando una versión de SLES y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| SLES                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|------------------------|---------------|---------------|----------------|
| ✔️ [15](linux-sles.md#sles-15-)     | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [12 SP2](linux-sles.md#sles-12-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en SLES](linux-sles.md).

## <a name="ubuntu"></a>Ubuntu

Ubuntu usa APT (herramienta avanzada de paquetes) como administrador de paquetes.

En la tabla siguiente se representa el estado de compatibilidad de Ubuntu y .NET Core.

- Una ✔️ indica que todavía se admite la versión de Ubuntu o de .NET Core.
- Una ❌ indica que la versión de Ubuntu o de .NET Core no se admite en esa versión de Ubuntu.
- Cuando una versión de Ubuntu y una versión de .NET Core tienen una ✔️, se admite esa combinación de sistema operativo y .NET.

| Ubuntu                   | .NET Core 2.1 | .NET Core 3.1 | Versión preliminar de .NET 5 (solo instalación manual) |
|--------------------------|---------------|---------------|----------------|
| ✔️ [20.04 (LTS)](linux-ubuntu.md#2004-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ✔️ [19.10](linux-ubuntu.md#1910-)       | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [19.04](linux-ubuntu.md#1904-)       | ✔️ 2.1        | ✔️ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [18.10](linux-ubuntu.md#1810-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ✔️ [18.04 (LTS)](linux-ubuntu.md#1804-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |
| ❌ [17.10](linux-ubuntu.md#1710-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [17.04](linux-ubuntu.md#1704-)       | ✔️ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ❌ [16.10](linux-ubuntu.md#1610-)       | ❌ 2.1        | ❌ 3.1        | ❌ 5.0 (versión preliminar) |
| ✔️ [16.04 (LTS)](linux-ubuntu.md#1604-) | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 (versión preliminar) |

Para más información, consulte [Instalación de .NET Core en Ubuntu](linux-ubuntu.md).
