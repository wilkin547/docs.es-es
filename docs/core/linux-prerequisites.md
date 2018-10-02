---
title: Requisitos previos para .NET Core en Linux
description: Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux.
author: jralexander
ms.author: johalex
ms.date: 08/20/2018
ms.openlocfilehash: d0e5b203dc8e1ec6807f28de7d910c74a2ffe665
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2018
ms.locfileid: "43506854"
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

**NET Core 2.1**

NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:

* Red Hat Enterprise Linux 7.6 - 64 bits (`x86_64` o `amd64`)
* CentOS 7 - 64 bits (`x86_64` o `amd64`) 
* Oracle Linux 7 - 64 bits (`x86_64` o `amd64`) 
* Fedora 28, 27 - 64 bits (`x86_64` o `amd64`) 
* Debian 9 (64 bits, ARM32), 8.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* Ubuntu 18.04 (64bits, ARM32), 16.04, 14.04 - 64 bits (`x86_64` o `amd64`)
* Linux Mint 18, 17 - 64 bits (`x86_64` o `amd64`)
* openSUSE 42.3 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versiones posteriores - 64 bits (`x86_64` o `amd64`)
* Alpine Linux 3.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)

Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

**NET Core 2.0**

NET Core 2.0 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):

* Red Hat Enterprise Linux 7, 6
* CentOS 7
* Oracle Linux 7
* Fedora 27
* Debian 9, 8.7 o versiones posteriores
* Ubuntu 18.04, 16.04, 14.04
* Linux Mint 18, 17
* openSUSE 42.3 o versiones posteriores
* SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versiones posteriores

Vea [.NET Core 2.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.0, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

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

El valor predeterminado del script es instalar la versión más reciente "LTS", que actualmente es .NET Core 1.1. Para instalar .NET Core 2.x, ejecute el script con el modificador siguiente:

```console
./dotnet-install.sh -c Current
```

El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas. Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.

## <a name="install-net-core-for-supported-red-hat-enterprise-linux-rhel-versions"></a>Instalación de .NET Core para versiones compatibles de Red Hat Enterprise Linux (RHEL)

Para instalar .NET Core en versiones compatibles de RHEL:

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**.NET Core 2.1**

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Para obtener la información de instalación más reciente de .NET Core 2.1 en Red Hat Enterprise Linux, vea [.NET Core 2.1 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.1/html/getting_started_guide/) (Guía de introducción de .NET Core 2.1).

**.NET Core 2.0**

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Para obtener la información de instalación más reciente de .NET Core 2.0 en Red Hat Enterprise Linux, vea [.NET Core 2.0 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/2.0/html/getting_started_guide/) (Guía de introducción de .NET Core 2.0). 

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2.  Para consultar la información de instalación más reciente de .NET Core 1.1 en Red Hat Enterprise Linux, vea [.NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.1/html/getting_started_guide/) (Guía de introducción de .NET Core 1.1).
     
**.NET Core 1.0**

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2.  Para consultar la información de instalación más reciente de .NET Core 1.0 en Red Hat Enterprise Linux, vea [.NET Core 1.0 Getting Started Guide](https://access.redhat.com/documentation/en-us/net_core/1.0/html/getting_started_guide/) (Guía de introducción de .NET Core 1.0).

Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.

---

## <a name="install-net-core-for-supported-ubuntu-and-linux-mint-distributionsversions-64-bit"></a>Instalar .NET Core para versiones o distribuciones compatibles de Ubuntu y Linux Mint (64 bits)

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 2.x en versiones o distribuciones compatibles de Ubuntu y Linux Mint (64 bits):

**.NET Core 2.0**

|Entornos de ejecución o SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|Runtime de .NET Core 2.0.9  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.9)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.9)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.9)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.9)            |
|Runtime de .NET Core 2.0.8  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.8)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.8)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.8)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.8)            |
|Runtime de .NET Core 2.0.7  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.7)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.7)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.7)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.7)            |
|Entorno de ejecución .NET Core 2.0.6  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.6)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.6)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.6)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.6)            |
|Entorno de ejecución .NET Core 2.0.5  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.0.5)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.0.5)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.0.5)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.0.5)            |
|SDK de .NET Core 2.1.202    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.202)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.202)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.202)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.202)            |
|SDK de .NET Core 2.1.201    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.201)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.201)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.201)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.201)            |
|SDK de .NET Core 2.1.200    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.200)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.200)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.200)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.200)            |
|SDK de .NET Core 2.1.105    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.105)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.105)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.105)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.105)            |
|SDK de .NET Core 2.1.103    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.103)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.103)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.103)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.103)            |
|SDK de .NET Core 2.0.3      |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.3)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.3)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.3)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.3)            |
|SDK de .NET Core 2.0.0      |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.0.0)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.0.0)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.0.0)          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.0.0)            |

**.NET Core 2.1**

>[!IMPORTANT]
> Para usar .NET Core 2.1 con Visual Studio, necesita [instalar Visual Studio 2017 15.7 o una versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Entornos de ejecución o SDK          |Ubuntu 18.04    |Ubuntu 17.10    |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|-------------------------|----------------|----------------|----------------------------|----------------------------|
|Runtime de .NET Core 2.1.2          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.2)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.2)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.2)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.2)            |
|SDK de .NET Core 2.1.400     |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.400)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.400)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.400)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.400)            |
|SDK de .NET Core 2.1.302     |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.302)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.302)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.302)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.302)            |
|Runtime de .NET Core 2.1.1          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.1)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.1)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.1)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.1)            |
|SDK de .NET Core 2.1.301     |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.301)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.301)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.301)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.301)            |
|Runtime de .NET Core 2.1.0          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/runtime-2.1.0)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/runtime-2.1.0)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/runtime-2.1.0)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/runtime-2.1.0)            |
|SDK de .NET Core 2.1.300     |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu18-04/sdk-2.1.300)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu17-10/sdk-2.1.300)|[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu16-04/sdk-2.1.300)            |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/ubuntu14-04/sdk-2.1.300)            |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 1.x en versiones o distribuciones compatibles de Ubuntu y Linux Mint (64 bits):

| Entornos de ejecución o SDK         |Ubuntu 16.04 / Linux Mint 18|Ubuntu 14.04 / Linux Mint 17|
|-------------------------|----------------------------|----------------------------|
|Runtime de .NET Core 1.1.9  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.1.8  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Entorno de ejecución .NET Core 1.1.7  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|Entorno de ejecución .NET Core 1.1.6  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.1.5  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.1.4  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
|Entorno de ejecución .NET Core 1.0.10 |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-ubuntu-14.04-x64-binaries)            |
|Entorno de ejecución .NET Core 1.0.9  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.0.8  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.0.7  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.0.5  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-ubuntu-14.04-x64-binaries)            |
|Runtime de .NET Core 1.0.4  |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.10     |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.9      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.8      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.7      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.5      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.1.4      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.0.4      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-ubuntu-14.04-x64-binaries)            |
|SDK de .NET Core 1.0.1      |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-16.04-x64-binaries)            |[Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-ubuntu-14.04-x64-binaries)            |

---

## <a name="install-net-core-for-supported-debian-versions-64-bit"></a>Instalar .NET Core para versiones compatibles de Debian (64 bits)

Para instalar .NET Core en versiones compatibles de Debian (64 bits):

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 2.x en versiones compatibles de Debian (64 bits):

**.NET Core 2.0**

|Entornos de ejecución o SDK          |Debian 9       |Debian 8       |
|-------------------------|---------------|---------------|
|Runtime de .NET Core 2.0.9  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.9)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.9)   |
|Runtime de .NET Core 2.0.8  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.8)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.8)   |
|Runtime de .NET Core 2.0.7  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.7)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.7)   |
|Entorno de ejecución .NET Core 2.0.6  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.6)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.6)   |
|Entorno de ejecución .NET Core 2.0.5  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.5)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.5)   |
|Runtime de .NET Core 2.0.3  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.3)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.3)   |
|Runtime de .NET Core 2.0.0  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.0.0)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.0.0)   |
|SDK de .NET Core 2.1.202    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.202)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.202)   |
|SDK de .NET Core 2.1.201    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.201)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.201)   |
|SDK de .NET Core 2.1.200    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.200)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.200)   |
|SDK de .NET Core 2.1.105    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|SDK de .NET Core 2.1.105    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.105)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.105)   |
|SDK de .NET Core 2.1.104    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.104)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.104)   |
|SDK de .NET Core 2.1.103    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.103)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.103)   |
|SDK de .NET Core 2.1.102    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.102)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.102)   |
|SDK de .NET Core 2.1.101    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.101)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.101)   |
|SDK de .NET Core 2.0.3      |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.3)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.3)   |
|SDK de .NET Core 2.0.0      |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.0.0)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.0.0)   |

**.NET Core 2.1**

>[!IMPORTANT]
> Para usar .NET Core 2.1 con Visual Studio, necesita [instalar Visual Studio 2017 15.7 o una versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Entornos de ejecución o SDK                  |Debian 9       |Debian 8       |
|---------------------------------|---------------|---------------|
|Runtime de .NET Core 2.1.2          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.2)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.2)   |
|SDK de .NET Core 2.1.400        |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.400)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.400)        |
|SDK de .NET Core 2.1.302        |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.302)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.302)        |
|Runtime de .NET Core 2.1.1          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.1)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.1)   |
|SDK de .NET Core 2.1.301        |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.301)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.301)        |
|Runtime de .NET Core 2.1.0          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/runtime-2.1.0)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/runtime-2.1.0)   |
|SDK de .NET Core 2.1.300        |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian9/sdk-2.1.300)   |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/debian8/sdk-2.1.300)        |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 1.x en Debian 9 o Debian 8:

* Runtime de .NET Core 1.1.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-debian-x64-binaries)
* Entorno de ejecución .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-debian-x64-binaries)
* Entorno de ejecución .NET Core 1.1.6 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-debian-x64-binaries)
* Runtime de .NET Core 1.1.0 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.0-linux-debian-x64-binaries)
* Entorno de ejecución .NET Core 1.0.10 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-debian-x64-binaries)
* Entorno de ejecución .NET Core 1.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-debian-x64-binaries)
* Runtime de .NET Core 1.0.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-debian-x64-binaries)
* Runtime de .NET Core 1.0.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-debian-x64-binaries)
* Runtime de .NET Core 1.0.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-debian-x64-binaries)
* Runtime de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.10 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-debian-x64-binaries)
* SDK de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-debian-x64-binaries)
* SDK de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-debian-x64-binaries)
* SDK de .NET Core 1.0.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

---

## <a name="install-net-core-for-supported-fedora-versions-64-bit"></a>Instalar .NET Core para versiones compatibles de Fedora (64 bits)

Para instalar .NET Core en versiones compatibles de Fedora:

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 2.x en versiones compatibles de Fedora (64 bits):

**.NET Core 2.0**

|Entornos de ejecución o SDK          |Fedora 26 o versiones posteriores |Fedora 25 o versiones anteriores |
|-------------------------|-------------------|----------------------|
|Runtime de .NET Core 2.0.9  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.9)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.9)           |
|Runtime de .NET Core 2.0.8  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.8)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.8)           |
|Runtime de .NET Core 2.0.7  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.7)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.7)           |
|Entorno de ejecución .NET Core 2.0.6  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.6)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.6)           |
|Entorno de ejecución .NET Core 2.0.5  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.5)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.5)           |
|Runtime de .NET Core 2.0.3  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.3)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.3)           |
|Runtime de .NET Core 2.0.0  |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/runtime-2.0.0)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/runtime-2.0.0)           |
|SDK de .NET Core 2.1.200    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.200)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.200)           |
|SDK de .NET Core 2.1.105    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.105)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.105)           |
|SDK de .NET Core 2.1.103    |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.1.103)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.1.103)           |
|SDK de .NET Core 2.0.3      |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora26/sdk-2.0.3)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora25/sdk-2.0.3)           |

**.NET Core 2.1**

>[!IMPORTANT]
> Para usar .NET Core 2.1 con Visual Studio, necesita [instalar Visual Studio 2017 15.7 o una versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

|Entornos de ejecución o SDK                  |Fedora 28          |Fedora 27             |
|---------------------------------|-------------------|----------------------|
|Runtime de .NET Core 2.1.2          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.2)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.2)           |
|SDK de .NET Core 2.1.400          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.400)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.400)           |
|SDK de .NET Core 2.1.302          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.302)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.302)           |
|Runtime de .NET Core 2.1.1          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.1)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.1)           |
|SDK de .NET Core 2.1.301          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.301)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.301)           |
|Runtime de .NET Core 2.1.0          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/runtime-2.1.0)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/runtime-2.1.0)           |
|SDK de .NET Core 2.1.300          |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora28/sdk-2.1.300)       |[Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/fedora27/sdk-2.1.300)           |

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 1.x en versiones compatibles de Fedora (64 bits):

**Fedora 24**

* Runtime de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-fedora-24-x64-binaries)
* Entorno de ejecución .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-fedora-24-x64-binaries)
* Entorno de ejecución .NET Core 1.1.6 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-fedora-24-x64-binaries)
* Runtime de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-fedora-24-x64-binaries)
* Runtime de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-24-x64-binaries)
* Runtime de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-24-x64-binaries)
* Runtime de .NET Core 1.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.1.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5linux-fedora-24-x64-binaries)
* SDK de .NET Core 1.0.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-debian-x64-binaries)

**Fedora 23**

* Runtime de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-fedora-23-x64-binaries)
* Runtime de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-fedora-23-x64-binaries)
* Runtime de .NET Core 1.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-fedora-23-x64-binaries)
* Entorno de ejecución .NET Core 1.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-fedora-23-x64-binaries)
* Runtime de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-fedora-23-x64-binaries)
* SDK de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4linux-fedora-23-x64-binaries)
* SDK de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
* SDK de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.2linux-fedora-23-x64-binaries)
* SDK de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-fedora-23-x64-binaries)
* SDK de .NET Core 1.0.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-fedora-23-x64-binaries)

---

## <a name="install-net-core-for-supported-centos-and-oracle-linux-distributionsversions-64-bit"></a>Instalar .NET Core para versiones o distribuciones compatibles de CentOS y Oracle Linux (64 bits)

Para instalar .NET Core para versiones o distribuciones compatibles de CentOS y Oracle Linux (64 bits):

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 2.x en versiones o distribuciones compatibles de CentOS y Oracle Linux (64 bits):

**.NET Core 2.0**

* Runtime de .NET Core 2.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.9)
* Runtime de .NET Core 2.0.8 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.8)
* Runtime de .NET Core 2.0.7 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.7)
* Entorno de ejecución .NET Core 2.0.6 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.6)
* Entorno de ejecución .NET Core 2.0.5 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.5)
* Runtime de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.3)
* Runtime de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.0.0)
* SDK de .NET Core 2.1.202 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.202)
* SDK de .NET Core 2.1.201 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.201)
* SDK de .NET Core 2.1.200 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.200)
* SDK de .NET Core 2.1.105 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.105)
* SDK de .NET Core 2.1.104 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.104)
* SDK de .NET Core 2.1.103 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.103)
* SDK de .NET Core 2.1.102 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.102)
* SDK de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.3)
* SDK de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Para usar .NET Core 2.1 con Visual Studio, necesita [instalar Visual Studio 2017 15.7 o una versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

* Runtime de .NET Core 2.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.2)
* SDK de .NET Core 2.1.400 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.400)
* SDK de .NET Core 2.1.302 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.302)
* Runtime de .NET Core 2.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.1)
* SDK de .NET Core 2.1.301 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.301)
* Runtime de .NET Core 2.1.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/runtime-2.1.0)
* SDK de .NET Core 2.1.300 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/centos/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 1.x en versiones o distribuciones compatibles de CentOS y Oracle Linux (64 bits):

* Runtime de .NET Core 1.1.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.9-linux-centos-x64-binaries)
* Runtime de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.8-linux-centos-x64-binaries)
* Entorno de ejecución .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-centos-x64-binaries)
* Entorno de ejecución .NET Core 1.1.6 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-centos-x64-binaries)
* Runtime de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.5-linux-centos-x64-binaries)
* Runtime de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.4-linux-centos-x64-binaries)
* Runtime de .NET Core 1.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.2-linux-centos-x64-binaries)
* Runtime de .NET Core 1.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.1-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.12 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.12-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.11 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.11-linux-centos-x64-binaries)
* Entorno de ejecución .NET Core 1.0.10 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.10-linux-centos-x64-binaries)
* Entorno de ejecución .NET Core 1.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.9-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.8-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.7-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.5-linux-centos-x64-binaries)
* Runtime de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.0.4-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.10 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.10-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.9 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.9-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.8 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.8-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.5 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.5-linux-centos-x64-binaries)
* SDK de .NET Core 1.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.4-linux-centos-x64-binaries)
* SDK de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-centos-x64-binaries)
* SDK de .NET Core 1.0.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-centos-x64-binaries)

---

## <a name="install-net-core-for-supported-suse-linux-enterprise-server-and-opensuse-distributionsversions-64-bit"></a>Instalar .NET Core para versiones o distribuciones compatibles de SUSE Linux Enterprise Server y OpenSUSE (64 bits)

Para instalar .NET Core 2.x para versiones o distribuciones compatibles de SUSE Linux Enterprise Server y OpenSUSE (64 bits):

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 2.x en versiones o distribuciones compatibles de SUSE Linux Enterprise Server y OpenSUSE (64 bits):

**.NET Core 2.0**

**SUSE Linux Enterprise Server**

* Runtime de .NET Core 2.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.9)
* Runtime de .NET Core 2.0.8 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.8)
* Runtime de .NET Core 2.0.7 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.7)
* Entorno de ejecución .NET Core 2.0.6 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.6)
* Entorno de ejecución .NET Core 2.0.5 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.5)
* Runtime de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.3)
* Runtime de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.0.0)
* SDK de .NET Core 2.1.202 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.202)
* SDK de .NET Core 2.1.201 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.201)
* SDK de .NET Core 2.1.200 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.200)
* SDK de .NET Core 2.1.105 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.105)
* SDK de .NET Core 2.1.104 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.104)
* SDK de .NET Core 2.1.103 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.103)
* SDK de .NET Core 2.1.102 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.102)
* SDK de .NET Core 2.1.101 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.101)
* SDK de .NET Core 2.1.100 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.100)
* SDK de .NET Core 2.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.4)
* SDK de .NET Core 2.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.2)
* SDK de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.3)
* SDK de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.0.0)

**openSUSE**

* Runtime de .NET Core 2.0.9 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.9)
* Runtime de .NET Core 2.0.8 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.8)
* Runtime de .NET Core 2.0.7 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.7)
* Entorno de ejecución .NET Core 2.0.6 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.6)
* Entorno de ejecución .NET Core 2.0.5 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.5)
* Runtime de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.3)
* Runtime de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.0.0)
* SDK de .NET Core 2.1.202 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.202)
* SDK de .NET Core 2.1.201 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.201)
* SDK de .NET Core 2.1.200 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.200)
* SDK de .NET Core 2.1.105 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.105)
* SDK de .NET Core 2.1.103 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.103)
* SDK de .NET Core 2.1.102 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.102)
* SDK de .NET Core 2.1.101 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.101)
* SDK de .NET Core 2.1.100 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.100)
* SDK de .NET Core 2.1.4 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.4)
* SDK de .NET Core 2.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.2)
* SDK de .NET Core 2.0.3 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.3)
* SDK de .NET Core 2.0.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.0.0)
 
**.NET Core 2.1**

>[!IMPORTANT]
> Para usar .NET Core 2.1 con Visual Studio, necesita [instalar Visual Studio 2017 15.7 o una versión posterior](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017).

**SUSE Linux Enterprise Server**

* Runtime de .NET Core 2.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.2)
* SDK de .NET Core 2.1.400 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.400)
* SDK de .NET Core 2.1.302 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.302)
* Runtime de .NET Core 2.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.1)
* SDK de .NET Core 2.1.301 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.301)
* Runtime de .NET Core 2.1.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/runtime-2.1.0)
* SDK de .NET Core 2.1.300 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/sles/sdk-2.1.300)

**openSUSE**

* Runtime de .NET Core 2.1.2 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.2)
* SDK de .NET Core 2.1.400 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.400)
* SDK de .NET Core 2.1.302 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.302)
* Runtime de .NET Core 2.1.1 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.1)
* SDK de .NET Core 2.1.301 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.301)
* Runtime de .NET Core 2.1.0 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/runtime-2.1.0)
* SDK de .NET Core 2.1.300 [Vínculo de instalación](https://www.microsoft.com/net/download/linux-package-manager/opensuse/sdk-2.1.300)

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Instale .NET Core 1.x en versiones o distribuciones compatibles de SUSE Linux Enterprise Server y OpenSUSE (64 bits):

**SUSE Linux Enterprise Server 13.2**

* Entorno de ejecución .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.7-linux-opensuse-13.2-x64-binaries)
* Entorno de ejecución .NET Core 1.1.6 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-1.1.6-linux-opensuse-13.2-x64-binaries)
* SDK de .NET Core 1.1.7 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.1.7-linux-opensuse-13.2-x64-binaries)
* SDK de .NET Core 1.0.4 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.4-linux-opensuse-13.2-x64-binaries)
* SDK de .NET Core 1.0.1 [Vínculo de instalación](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-1.0.1-linux-opensuse-13.2-x64-binaries)

---

## <a name="install-net-core-for-supported-alpine-linux-versions-64-bit"></a>Instalar .NET Core para versiones compatibles de Alpine Linux (64 bits)

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

Descargue y siga las instrucciones de instalación de .NET Core 2.1 para versiones compatibles de Alpine Linux (64 bits) en los vínculos siguientes:

* Runtime de .NET Core 2.1.2 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.2-linux-x64-alpine-binaries)
* SDK de .NET Core 2.1.400 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.400-linux-x64-alpine-binaries)
* SDK de .NET Core 2.1.302 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.302-linux-x64-alpine-binaries)
* Runtime de .NET Core 2.1.1 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.1-linux-x64-alpine-binaries)
* SDK de .NET Core 2.1.301 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.301-linux-x64-alpine-binaries)
* Entorno de ejecución de .NET Core 2.1.0 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-runtime-2.1.0-linux-x64-alpine-binaries)
* SDK de .NET Core 2.1.300 [Vínculo de descarga](https://www.microsoft.com/net/download/thank-you/dotnet-sdk-2.1.300-linux-x64-alpine-binaries)

> [!IMPORTANT]
> Si tiene problemas con una instalación de .NET Core en una versión o distribución de Linux compatible, vea los siguientes temas para sus versiones o distribuciones instaladas:
> * [.NET Core 2.1 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) (Problemas conocidos de .NET Core 2.1)
> * [.NET Core 2.0 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) (Problemas conocidos de .NET Core 2.0)
> * [.NET Core 1.1 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.1) (Problemas conocidos de .NET Core 1.1)
> * [.NET Core 1.0 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0) (Problemas conocidos de .NET Core 1.0)
