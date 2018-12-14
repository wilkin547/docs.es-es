---
title: Requisitos previos para .NET Core en Linux
description: Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux.
author: thraka
ms.author: adegeo
ms.date: 12/03/2018
ms.openlocfilehash: e250158d10c6a03535f4e693e74954747f860a3c
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148343"
---
# <a name="prerequisites-for-net-core-on-linux"></a>Requisitos previos para .NET Core en Linux

En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux. Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:

* [Línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

> [!NOTE]
> El paquete del SDK de .NET Core no es necesario para entornos o servidores de producción. Solo se necesita el paquete del entorno de ejecución .NET Core para las aplicaciones que se implementan en entornos de producción. El entorno de ejecución .NET Core se implementa con aplicaciones como parte de una implementación independiente, aunque se debe implementar para aplicaciones implementadas por separado dependientes del marco. Para obtener más información sobre las implementaciones independientes y dependientes del marco, vea [Implementación de aplicaciones .NET Core](./deploying/index.md). Consulte también [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones independientes de Linux) para obtener instrucciones específicas.

## <a name="supported-linux-versions"></a>Versiones de Linux compatibles

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.x considera a Linux como un único sistema operativo. Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles. 

Para los vínculos de descarga y más información, consulte [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Descargas de .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Descargas de .NET Core 2.1).

.NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux:

* Red Hat Enterprise Linux 7.6 - 64 bits (`x86_64` o `amd64`)
* CentOS 7 - 64 bits (`x86_64` o `amd64`) 
* Oracle Linux 7 - 64 bits (`x86_64` o `amd64`) 
* Fedora 28, 27 - 64 bits (`x86_64` o `amd64`) 
* Debian 9 (64 bits, `arm32`), 8.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* Ubuntu 18.04 (64 bits, `arm32`), 16.04, 14.04 - 64-bits (`x86_64` o `amd64`)
* Linux Mint 18, 17 - 64 bits (`x86_64` o `amd64`)
* openSUSE 42.3 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* Alpine Linux 3.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)

Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) y [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1 y .NET Core 2.2, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Para los vínculos de descarga y más información, consulte [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Descargas de .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Descargas de .NET Core 1.0).

NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 28 (.NET Core 1.1), 27
* Debian 8.2 o versiones posteriores
* Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04
* Linux Mint 17
* openSUSE 42.3 o versiones posteriores (.NET Core 1.1)

Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.

---

## <a name="linux-distribution-dependencies"></a>Dependencias de distribución de Linux

Los siguientes están diseñados a modo de ejemplos. Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.

### <a name="ubuntu"></a>Ubuntu

Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:

* liblttng-ust0
* libcurl3
* libssl1.0.0
* libkrb5-3
* zlib1g
* libicu52 (para 14.x)
* libicu55 (para 16.x)
* libicu57 (para 17.x)
* libicu60 (para 18.x)

Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:

* libunwind8
* libuuid1

### <a name="centos-and-fedora"></a>CentOS y Fedora

Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:

* lttng-ust
* libcurl
* openssl-libs
* krb5-libs
* libicu
* zlib

Usuarios de Fedora: si la versión de openssl >= 1.1, es necesario instalar compat-openssl10.

Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:

* libunwind
* libuuid

Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Instalación de las dependencias de .NET Core con los instaladores nativos

Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles. Los instaladores nativos requieren acceso de administrador (sudo) para el servidor. La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas. Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.

En Linux, existen dos opciones de paquete de instalador:

* Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.
* Usar los propios paquetes, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Instalaciones de scripting con el script del instalador de .NET Core

Los [scripts de dotnet-install](./tools/dotnet-install-script.md) se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de la CLI y del entorno de ejecución compartido. Puede descargar el script de [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).

El valor predeterminado del script es instalar la versión más reciente "LTS", que actualmente es .NET Core 1.1. Para instalar .NET Core 2.1, ejecute el script con el modificador siguiente:

```console
./dotnet-install.sh -c Current
```

El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas. Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.

## <a name="troubleshoot"></a>Solucionar problemas

Si tiene problemas con una instalación de .NET Core en una versión o distribución de Linux compatible, vea los siguientes temas para sus versiones o distribuciones instaladas:

* [.NET Core 3.0 known issues](https://github.com/dotnet/core/tree/master/release-notes/3.0) (Problemas conocidos de .NET Core 3.0)
* [.NET Core 2.2 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.2) (Problemas conocidos de .NET Core 2.2)
* [.NET Core 2.1 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) (Problemas conocidos de .NET Core 2.1)
* [.NET Core 1.1 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.1) (Problemas conocidos de .NET Core 1.1)
* [.NET Core 1.0 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0) (Problemas conocidos de .NET Core 1.0)
