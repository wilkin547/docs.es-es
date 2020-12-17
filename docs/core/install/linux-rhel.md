---
title: 'Instalación de .NET en RHEL: .NET'
description: Se muestran las diversas maneras de instalar el SDK y el entorno de ejecución de .NET en RHEL.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 0b6138185bfd3e2f50c1b31e82779165715a5b6e
ms.sourcegitcommit: 45c7148f2483db2501c1aa696ab6ed2ed8cb71b2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/08/2020
ms.locfileid: "96851645"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-rhel"></a>Instalación del SDK y el entorno de ejecución de .NET en RHEL

.NET es compatible con RHEL. En este artículo se describe cómo instalar .NET en RHEL.

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="register-your-red-hat-subscription"></a>Registro de la suscripción de Red Hat

Para instalar .NET desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat. Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/).

## <a name="supported-distributions"></a>Distribuciones admitidas

En la tabla siguiente se muestra una lista de las versiones de .NET compatibles actualmente con RHEL 7 y RHEL 8. Estas versiones siguen siendo compatibles hasta que la versión de [.NET llegue al final del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o ya no se admita la versión de RHEL.

- El símbolo ✔️ indica que todavía se admite la versión de RHEL o de .NET.
- El símbolo ❌ indica que la versión de RHEL o de .NET no se admite en esa versión de RHEL.
- Si una versión de RHEL y una versión de .NET tienen un símbolo ✔️, esa combinación de sistema operativo y .NET se admite.

| RHEL                     | .NET Core 2.1 | .NET Core 3.1 | .NET 5.0 |
|--------------------------|---------------|---------------|----------------|
| ✔️ [8](#rhel-8-)        | ✔️ 2.1        | ✔️ 3.1        | ✔️ 5.0 |
| ✔️ [7](#rhel-7--net-50) | ✔️ 2.1        | ✔️ [3.1](#rhel-7--net-core-31)        | ✔️ [5.0](#rhel-7--net-50) |

Las versiones siguientes de .NET ya no se admiten. Las descargas de estas siguen estando publicadas:

- 3.0
- 2.2
- 2.0

## <a name="remove-preview-versions"></a>Eliminación de versiones preliminares

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

Consulte la [documentación de Red Hat para .NET](https://access.redhat.com/documentation/net/5.0/) sobre los pasos necesarios para instalar otras versiones de .NET.

## <a name="rhel-8-"></a>RHEL 8 ✔️

.NET se incluye en los repositorios de AppStream para RHEL 8.

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="rhel-7--net-50"></a>RHEL 7 ✔️ .NET 5.0

El siguiente comando instala el paquete `scl-utils`:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET permite desarrollar aplicaciones con .NET. Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente. Para instalar el SDK de .NET, ejecute los comandos siguientes:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50 -y
scl enable rh-dotnet50 bash
```

Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas. Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.

```bash
source scl_source enable rh-dotnet50
```

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

El entorno de ejecución de .NET permite ejecutar aplicaciones creadas con .NET, pero sin incluir el entorno de ejecución. Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet50-aspnetcore-runtime-5.0 -y
scl enable rh-dotnet50 bash
```

Red Hat no recomienda habilitar `rh-dotnet50` de forma permanente porque puede afectar a otros programas. Si quiere habilitar `rh-dotnet50` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.

```bash
source scl_source enable rh-dotnet50
```

Una alternativa al entorno de ejecución de ASP.NET Core es instalar el de .NET, que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet50-aspnetcore-runtime-5.0` en los comandos anteriores por `rh-dotnet50-dotnet-runtime-5.0`.

## <a name="rhel-7--net-core-31"></a>RHEL 7 ✔️ .NET Core 3.1

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

El siguiente comando instala el paquete `scl-utils`:

```bash
sudo yum install scl-utils
```

### <a name="install-the-sdk"></a>Instalación del SDK

El SDK de .NET Core permite desarrollar aplicaciones con .NET Core. Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente. Para instalar el SDK de .NET Core, ejecute los siguientes comandos:

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31 -y
scl enable rh-dotnet31 bash
```

Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas. Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL. Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`. Si quiere habilitar `rh-dotnet` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.

```bash
source scl_source enable rh-dotnet31
```

### <a name="install-the-runtime"></a>Instalación de la instancia en tiempo de ejecución

.NET Core Runtime le permite ejecutar aplicaciones que se realizaron con .NET Core que no incluían el entorno de ejecución. Los siguientes comandos instalan el entorno de ejecución de ASP.NET Core, que es el entorno de ejecución más compatible con .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
subscription-manager repos --enable=rhel-7-server-dotnet-rpms
yum install rh-dotnet31-aspnetcore-runtime-3.1 -y
scl enable rh-dotnet31 bash
```

Red Hat no recomienda habilitar `rh-dotnet31` de forma permanente porque puede afectar a otros programas. Por ejemplo, `rh-dotnet31` incluye una versión de `libcurl` que varía con respecto a la versión base de RHEL. Esto puede dar lugar a problemas en programas que no esperan una versión diferente de `libcurl`. Si quiere habilitar `rh-dotnet31` de forma permanente, agregue la siguiente línea al archivo _~/.bashrc_.

```bash
source scl_source enable rh-dotnet31
```

Una alternativa al entorno de ejecución de ASP.NET Core es instalar la instancia de .NET Core Runtime que no incluye compatibilidad con ASP.NET Core. Reemplace `rh-dotnet31-aspnetcore-runtime-3.1` en los comandos anteriores por `rh-dotnet31-dotnet-runtime-3.1`.

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
