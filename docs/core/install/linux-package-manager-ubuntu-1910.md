---
title: 'Instalación de .NET Core en el administrador de paquetes de Ubuntu 19.10: .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el runtime de .NET Core en Ubuntu 19.10.
author: thraka
ms.author: adegeo
ms.date: 01/16/2020
ms.openlocfilehash: afba761e2237ed84528157841e538a9b44d9a966
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/17/2020
ms.locfileid: "76164073"
---
# <a name="ubuntu-1910-package-manager---install-net-core"></a>Administrador de paquetes de Ubuntu 19.10: instalación de .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

En este artículo se explica cómo usar un administrador de paquetes para instalar .NET Core en Ubuntu 19.10. Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Registro de la clave y la fuente de Microsoft

Antes de instalar .NET, deberá realizar lo siguiente:

- Registrar la clave de Microsoft.
- Registrar el repositorio del producto.
- Instalar las dependencias necesarias.

Esto solo se debe hacer una vez por máquina.

Abra un terminal y ejecute los comandos siguientes.

```bash
wget -q https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

## <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-sdk-3.1
```

> [!IMPORTANT]
> Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-sdk-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).

## <a name="install-the-aspnet-core-runtime"></a>Instalación del entorno de ejecución de ASP.NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> Si recibe un mensaje de error similar a **No se puede encontrar el paquete aspnetcore-runtime-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).

## <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core. En el terminal, ejecute los comandos siguientes.

```bash
sudo apt-get update
sudo apt-get install apt-transport-https
sudo apt-get update
sudo apt-get install dotnet-runtime-3.1
```

> [!IMPORTANT]
> Si recibe un mensaje de error similar a **No se puede encontrar el paquete dotnet-runtime-3.1**, vea la sección [Solución de problemas del administrador de paquetes](#troubleshoot-the-package-manager).

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a>Solución de problemas del administrador de paquetes

Si recibe un mensaje de error similar a **No se puede encontrar el paquete (el paquete .NET Core)** , ejecute los comandos siguientes.

```bash
sudo dpkg --purge packages-microsoft-prod && sudo dpkg -i packages-microsoft-prod.deb
sudo apt-get update
sudo apt-get install {the .NET Core package}
```

Si eso no funciona, puede ejecutar una instalación manual con los comandos siguientes.

```bash
sudo apt-get install -y gpg
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget -q https://packages.microsoft.com/config/ubuntu/19.10/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get install -y apt-transport-https
sudo apt-get update
sudo apt-get install {the .NET Core package}
```
