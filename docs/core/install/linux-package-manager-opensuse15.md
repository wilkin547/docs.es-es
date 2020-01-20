---
title: 'Instalación de .NET Core en openSUSE 15 (administrador de paquetes): .NET Core'
description: Use un administrador de paquetes para instalar el SDK y el entorno de ejecución de .NET Core en openSUSE 15.
author: thraka
ms.author: adegeo
ms.date: 12/26/2019
ms.openlocfilehash: cba07bafc32cc71a1cdaec08902284e105af4776
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740676"
---
# <a name="opensuse-15-package-manager---install-net-core"></a>Administrador de paquetes de openSUSE 15: instalación de .NET Core

[!INCLUDE [package-manager-switcher](./includes/package-manager-switcher.md)]

En este artículo se describe cómo usar un administrador de paquetes para instalar .NET Core en openSUSE 15. Si va a instalar el entorno de ejecución, le recomendamos que instale el [entorno de ejecución de ASP.NET Core](#install-the-aspnet-core-runtime), ya que incluye los de .NET Core y ASP.NET Core.

## <a name="register-microsoft-key-and-feed"></a>Registro de la clave y la fuente de Microsoft

Antes de instalar .NET, deberá realizar lo siguiente:

- Registrar clave de Microsoft.
- Registrar el repositorio del producto.
- Instalar las dependencias necesarias.

Esto solo se debe hacer una vez por máquina.

Abra un terminal y ejecute los comandos siguientes.

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget -q https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

## <a name="dependency-error-with-net-core-31"></a>Error de dependencia con .NET Core 3.1

La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**. Use el siguiente comando para instalar las dependencias correctas antes de instalar .NET Core 3.1 o ASP.NET Core 3.1.

```bash
sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
```

## <a name="install-the-net-core-sdk"></a>Instalación del SDK de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el SDK de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install dotnet-sdk-3.1
```

> [!IMPORTANT]
> La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**. Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el SDK de .NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-aspnet-core-runtime"></a>Instalación del entorno de ejecución de ASP.NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de ASP.NET. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install aspnetcore-runtime-3.1
```

> [!IMPORTANT]
> La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**. Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el runtime de ASP.NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="install-the-net-core-runtime"></a>Instalación del entorno de ejecución de .NET Core

Actualice los productos disponibles para la instalación y, después, instale el entorno de ejecución de .NET Core. En el terminal, ejecute el comando siguiente.

```bash
sudo zypper install dotnet-runtime-3.1
```

> [!IMPORTANT]
> La fuente del paquete de .NET Core 3.1 para openSUSE tiene un problema con la dependencia **krb5**. Use el siguiente comando para instalar las dependencias correctas y, a continuación, instale el runtime de .NET Core 3.1.
>
> ```bash
> sudo zypper install https://packages.microsoft.com/opensuse/15/prod/dotnet-runtime-deps-3.1.0-opensuse.42-x64.rpm
> ```

## <a name="how-to-install-other-versions"></a>Procedimiento para instalar otras versiones

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]
