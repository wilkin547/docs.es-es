---
title: Requisitos previos para .NET Core en Linux
description: "Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 12/06/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.workload:
- dotnetcore
ms.openlocfilehash: 913d3869559b10af508e695a06d06021f8f90175
ms.sourcegitcommit: adcf9bdafeaa6bc243af7bf70b45f3df954f256a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a>Requisitos previos para .NET Core en Linux

En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux. Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:

* [Línea de comandos con su editor favorito](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Versiones de Linux compatibles

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

.NET Core 2.0 considera a Linux como un único sistema operativo. Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.

NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):

 * Red Hat Enterprise Linux 7
 * CentOS 7
 * Oracle Linux 7
 * Fedora 25, Fedora 26
 * Debian 8.7 o versiones posteriores 
 * Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04
 * Linux Mint 18, Linux Mint 17
 * openSUSE 42.2 o versiones posteriores
 * SUSE Enterprise Linux (SLES) 12 SP2 o versiones posteriores

Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):

* Red Hat Enterprise Linux 7
* CentOS 7
* Oracle Linux 7
* Fedora 24
* Debian 8.2 o versiones posteriores
* Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*
 * Ubuntu 16.10 es compatible con la última versión de revisión de .NET Core 1.1
* Linux Mint 17
* openSUSE 42.1 o versiones posteriores (.NET Core 1.1)

Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.

---

## <a name="linux-distribution-dependencies"></a>Dependencias de distribución de Linux

Los siguientes están diseñados a modo de ejemplos. Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.

### <a name="ubuntu"></a>Ubuntu

Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:

* libunwind8
* liblttng-ust0
* libcurl3
* libssl1.0.0
* libuuid1
* libkrb5-3
* zlib1g
* libicu52 (para 14.X)
* libicu55 (para 16.X)
* libicu57 (para 17.X)

### <a name="centos"></a>CentOS

Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:

* libunwind
* lttng-ust
* libcurl
* openssl-libs
* libuuid
* krb5-libs
* libicu
* zlib

Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).

## <a name="installing-net-core-dependencies-with-the-native-installers"></a>Instalación de las dependencias de .NET Core con los instaladores nativos

Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles. Los instaladores nativos requieren acceso de administrador (sudo) para el servidor. La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas. Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.

En Linux, existen dos opciones de paquete de instalador:

* Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.
* Usar los propios paquetes, DEB o RPM.

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Instalaciones de scripting con el script del instalador de .NET Core

Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido. Puede descargar el script desde: https://dot.net/v1/dotnet-install.sh

El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas. Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.

> [!IMPORTANT]
> Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a>Instalación de .NET Core para Red Hat Enterprise Linux (RHEL) 7

Para instalar .NET Core en RHEL 7, haga lo siguiente:

1. Habilite el canal .NET para Red Hat, disponible en su suscripción a RHEL 7.
    * Para Red Hat Enterprise 7 Server, use:
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * Para Red Hat Enterprise 7 Workstation, use:
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * Para el nodo de ejecución de HPC de Red Hat Enterprise 7, use:
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. Instale la herramienta de scl.

    ```bash
    yum install scl-utils
    ```
    
3. Instale .NET Core.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Para instalar el SDK y el runtime de .NET Core 2.0, haga lo siguiente:

   ```bash
   yum install rh-dotnet20
   ```

Para habilitar el SDK o el runtime de .NET Core 2.0 en su entorno, haga lo siguiente:

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**.NET Core 1.1**

Para instalar el SDK y el runtime de .NET Core 1.1, haga lo siguiente:

   ```bash
   yum install rh-dotnetcore11
   ```

Para habilitar el SDK y el runtime de .NET Core 1.1 en su entorno, haga lo siguiente:

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

**.NET Core 1.0**

Para instalar el SDK y el runtime de .NET Core 1.0, haga lo siguiente:

   ```bash
   yum install rh-dotnetcore10
   ```

Para habilitar el SDK y el runtime de .NET Core 1.0 en su entorno, haga lo siguiente:

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --version
     ```

Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a>Instale .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bits)

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registre la clave de producto de Microsoft como de confianza.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. Configure la versión deseada de la fuente del paquete de host.

   **Ubuntu 17.10**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   **Ubuntu 17.04**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 16.04 / Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   **Ubuntu 14.04 / Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. Instale .NET Core.

   ```bash
   sudo apt-get install dotnet-sdk-2.1.4
   ```

4. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Configure la versión deseada de la fuente del paquete de host.

   **Ubuntu 16.10**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  **Ubuntu 16.04 / Linux Mint 18**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   **Ubuntu 14.04 / Linux Mint 17**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. Instale .NET Core 1.x en Ubuntu o Linux Mint:

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a>Instalación .NET Core para Debian 8 o Debian 9 (64 bits)

Para instalar .NET Core para Debian 8 o Debian 9 (64 bits):

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Instale los componentes del sistema.

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. Registre la clave de producto de Microsoft como de confianza.

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. Registre la fuente de producto de Microsoft.

   **Debian 9 (Stretch)**

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   **Debian 8 (Jessie)**
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. Instale el SDK de .NET Core.

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. Agregue dotnet a su ruta de acceso.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Obtenga los requisitos previos.

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. Descargue los archivos binarios del SDK de .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. Extraiga los archivos binarios del SDK de .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a>Instalación de .NET Core para Fedora 24, Fedora 25 o Fedora 26 (64 bits)

Para instalar .NET Core 2.x en Fedora 26 o Fedora 25, o bien .NET Core 1.x en Fedora 24:

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 o Fedora 25**

2. Registre la fuente de firma de Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Agregue la fuente de producto dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Instale el SDK de .NET Core.

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

2. Obtenga los requisitos previos.

   ```bash
   sudo dnf install libunwind libicu
   ```

3. Descargue el archivo binario del SDK de .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. Extraiga los archivos binarios del SDK de .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits)

Para instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits):

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registre la fuente de firma de Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Agregue la fuente de producto de Microsoft.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. Instale el SDK de .NET Core.

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Obtenga los requisitos previos.

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. Descargue el archivo binario del SDK de .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. Extraiga los archivos binarios del SDK de .NET Core.

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a>Instale .NET Core para SUSE Linux Enterprise Server (64 bits)

Para instalar .NET Core 2.x para SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bits):

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

2. Agregue la fuente de producto dotnet.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. Instale el SDK de .NET Core.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. Agregue dotnet a su ruta de acceso.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a>Instalación de .NET Core para openSUSE (64 bits)

Para instalar .NET Core 2.x para openSUSE o .NET Core 1.x para openSUSE (64 bits):

1. Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.

> [!NOTE]
> Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

2. Registre la fuente de firma de Microsoft.

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. Agregue la fuente de producto dotnet.

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. Instale el SDK de .NET Core.

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

2. Obtenga los requisitos previos.

   ```bash
   sudo zypper install libunwind libicu
   ```

3. Descargue el archivo binario del SDK de .NET Core (tarball).

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. Extraiga los archivos binarios del SDK de .NET Core.
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. Agregue dotnet a su ruta de acceso.

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> Si tiene problemas con la instalación de .NET Core 2.x en una versión o distribución de Linux compatible, vea el tema [Problemas conocidos de la versión 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) para sus versiones o distribuciones instaladas. 
>
> Si tiene problemas con la instalación de .NET Core 1.x en una versión o distribución de Linux compatible, vea los temas [Problemas conocidos de la versión 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [Problemas conocidos de la versión 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) para sus versiones o distribuciones instaladas.
