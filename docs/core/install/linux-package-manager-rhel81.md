---
title: 'Instalación de .NET Core en el administrador de paquetes de Linux RHEL 8.1: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en RHEL 8.1.
author: thraka
ms.author: adegeo
ms.date: 12/03/2019
ms.openlocfilehash: 8781d6bd14daf975fcc602fd2924a333750d4256
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714373"
---
# <a name="rhel-81-package-manager---install-net-core"></a>Administrador de paquetes de RHEL 8.1: instalación de .NET Core

[!INCLUDE [package-manager-switcher](includes/package-manager-switcher.md)]

En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en RHEL 8.1. .NET Core 3.1 todavía no está disponible para RHEL 8.1.

> [!NOTE]
> RHEL 8.0 no incluye .NET Core 3.0. Use el comando `yum upgrade` para actualizar a RHEL 8.1.

## <a name="register-your-red-hat-subscription"></a>Registro de la suscripción de Red Hat

Para instalar .NET Core desde Red Hat en RHEL, primero debe registrarse con el administrador de suscripciones de Red Hat. Si esto no se ha realizado en el sistema, o si no tiene certeza de ello, vea la [documentación del producto de Red Hat para .NET Core](https://access.redhat.com/documentation/net_core/).

## <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el SDK de .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
dnf install dotnet-sdk-3.0
scl enable dotnet-sdk-3.0 bash
```

## <a name="install-the-aspnet-core-runtime"></a>Instalación del entorno de ejecución de ASP.NET Core

Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de ASP.NET Core. En el terminal, ejecute los comandos siguientes.

```bash
dnf install aspnetcore-runtime-3.0
scl enable aspnetcore-runtime-3.0 bash
```

## <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

Después de registrarse con el administrador de suscripciones, está a punto para instalar y habilitar el entorno de ejecución de .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo dnf install dotnet-runtime-3.0
scl enable dotnet-runtime-3.0 bash
```

## <a name="see-also"></a>Vea también

- [Uso de .NET Core 3.0 en Red Hat Enterprise Linux 8](https://access.redhat.com/documentation/en-us/net_core/3.0/html/getting_started_guide_for_rhel_8/gs_install_dotnet)
