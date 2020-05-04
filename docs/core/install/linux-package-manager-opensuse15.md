---
title: 'Instalación de .NET Core en openSUSE 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 03/17/2020
ms.openlocfilehash: fc4c9e30ddb0cfd3e6fe79fa4f78206f4700eeee
ms.sourcegitcommit: 62285ec11fa8e8424bab00511a90760c60e63c95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/20/2020
ms.locfileid: "81645662"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>Administrador de paquetes de openSUSE 15: instalación de .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en openSUSE 15.

[!INCLUDE [package-manager-intro-sdk-vs-runtime](includes/package-manager-intro-sdk-vs-runtime.md)]

## <a name="add-microsoft-repository-key-and-feed"></a>Adición de la clave y la fuente del repositorio de Microsoft

Antes de instalar .NET, deberá realizar lo siguiente:

- Agregar la clave de firma del paquete de Microsoft a la lista de claves de confianza.
- Agregar el repositorio al administrador de paquetes.
- Instalar las dependencias necesarias.

Esto solo se debe hacer una vez por máquina.

Abra un terminal y ejecute los comandos siguientes.

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install dotnet-sdk-3.1
```

## <a name="install-the-aspnet-core-runtime"></a>Instalación del entorno de ejecución de ASP.NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

## <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install dotnet-runtime-3.1
```

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

En esta sección se proporciona información sobre los errores comunes que puede obtener al usar el administrador de paquetes para instalar .NET Core.

### <a name="failed-to-fetch"></a>No se pudo capturar el elemento

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]
