---
title: Requisitos previos para .NET Core en Linux
description: "Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: johalex
ms.author: johalex
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: dd1557d3a43a13c8103c82dfa467aa889fcf3bbb
ms.openlocfilehash: 2ee303424721b7e1ecb8473c5f957ca929a8742f
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a>Requisitos previos para .NET Core en Linux

En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux. Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:

* [Línea de comandos](tutorials/using-with-xplat-cli.md)
* [Visual Studio Code](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a>Versiones de Linux compatibles

.NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux:

 * Red Hat Enterprise Linux 7 x64
 * CentOS 7 x64
 * Oracle Linux 7 x64
 * Fedora 25, 26 x64
 * Debian 9, 8.7+ x64 
 * Ubuntu 17.04, 16.04, 14.04  x64
 * Linux Mint 18, 17 x64
 * openSUSE 42.2+ x64
 * SUSE Enterprise Linux (SLES) 12 SP2+ x64

.NET Core 1.x se admite en las siguientes versiones o distribuciones de Linux:

* Red Hat Enterprise Linux / CentOS / Oracle Linux 7 x64
* Fedora 24 x64
* Debian 8.2+ x64
* Ubuntu / Linux Mint 14.04, 16.04, 16.10*, 17 x64
* openSUSE 42.1 (1.1) x64
> [!NOTE]
> Ubuntu / Linux 16.10 es compatible con la última versión de revisión de .NET Core 1.1

Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.

Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.
## <a name="linux-distribution-dependencies"></a>Dependencias de distribución de Linux
### <a name="ubuntu"></a>Ubuntu
Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:

* libunwind8
* libunwind8-dev
* gettext
* libicu-dev
* liblttng-ust-dev
* libcurl4-openssl-dev
* libssl-dev
* uuid-dev
* unzip

### <a name="centos"></a>CentOS
Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:
* deltarpm
* epel-release
* unzip
* libunwind
* gettext
* libcurl-devel
* openssl-devel
* zlib
* libicu-devel

## <a name="installing-net-core-prerequisites-with-the-native-installers"></a>Instalación de los requisitos previos de .NET Core con los instaladores nativos

Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles. Los instaladores nativos requieren acceso de administrador (sudo) para el servidor. La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas. Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.

En Linux, existen dos opciones de paquete de instalador: 
* Usar un administrador de paquetes basado en la fuente, como apt-get para Ubuntu o yum para CentOS. 
* Usar los propios paquetes, DEB o RPM. 

### <a name="scripting-installs-with-the-net-core-installer-script"></a>Instalaciones de scripting con el script del instalador de .NET Core 

Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido. Puede descargar los scripts del [repositorio de GitHub de CLI](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain). 

El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas. Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.

> [!IMPORTANT]
> Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.

## <a name="install-net-core-dependencies-for-red-hat-enterprise-linux-rhel-7-server"></a>Instalar dependencias de .NET Core para Red Hat Enterprise Linux (RHEL) 7 Server

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

### <a name="verify-and-enable-the-net-channel-for-rhel-7-server"></a>Comprobar y habilitar el canal .NET para RHEL 7 Server
Para instalar las dependencias de .NET Core en RHEL Server:

1. Habilite el canal .NET para Red Hat, disponible en su suscripción a RHEL 7 Server. 
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
3. Instalar .NET Core 1.1 (y todas las dependencias):
    ```bash
    yum install rh-dotnetcore11
    scl enable rh-dotnetcore11 bash
    ```
4. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --help
     ```
> [!NOTE]
> Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.


## <a name="install-net-core-for-ubuntu-1404-1604-1610--linux-mint-17-18-64-bit"></a>Instalar .NET Core para Ubuntu 14.04, 16.04, 16.10 y Linux Mint 17, 18 (64 bit)

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

### <a name="add-the-dotnet-apt-get-feed"></a>Agregar la fuente dotnet apt-get

1. Configure la versión deseada de la fuente del paquete de host.

   **Ubuntu 14.04 / Linux Mint 17**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.04 / Linux Mint 18**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
    **Ubuntu 16.10**
    ```bash
    sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list' 
    sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
    sudo apt-get update
    ```
2. Instale .NET Core.
# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Después de la instalación de la fuente del paquete de host, instale .NET Core 2.0 en Ubuntu o Linux Mint:
```bash
sudo apt-get install dotnet-sdk-2.0.0
```
# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Después de la instalación de la fuente del paquete de host, instale .NET Core 1.x en Ubuntu o Linux Mint:
```bash
sudo apt-get install dotnet-dev-1.0.4
```
---
3. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

 ```bash
     dotnet --help
 ```
## <a name="install-net-core-for-debian-8-or-9-64-bit"></a>Instale .NET Core para Debian 8 o 9 (64 bit).

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

Para instalar .NET Core en Debian 8 o 9 (64 bit):
1. Obtenga los requisitos previos. 
    ```bash
    sudo apt-get install curl libunwind8 gettext
    ```
2. Descargue los archivos binarios del SDK de .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)   

```bash
     curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)   

```bash
     curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
```
---
3. Extraiga los archivos binarios del SDK de .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Agregue dotnet a su ruta de acceso.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --help
     ```

## <a name="install-net-core-for-fedora-24-25-or-26-64-bit"></a>Instalar .NET Core para Fedora 24, 25 o 26 (64 bits)

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

Para instalar .NET Core para Fedora 26,25(.NET Core 2.x) o 24 (.NET Core 1.x): 
1. Obtenga los requisitos previos. 
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Descargue el archivo binario del SDK de .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**Fedora 26 o 25**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**Fedora 24**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
```

---
3. Extraiga los archivos binarios del SDK de .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Agregue dotnet a su ruta de acceso.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a>Instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits)

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

Para instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits):

1. Obtenga los requisitos previos.
    ```bash
    sudo dnf install libunwind libicu
    ```
2. Descargue el archivo binario del SDK de .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
```

---
3. Extraiga los archivos binarios del SDK de .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Agregue dotnet a su ruta de acceso.
    ```bash
    sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --help
     ```
## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit-net-core-2x-and-opensuse-64-bit"></a>Instalar .NET Core para SUSE Linux Enterprise Server (64 bits) (.NET Core 2.x) y openSUSE (64 bits)

> [!Warning]
> Antes de comenzar, quite cualquier versión anterior de .NET Core de su sistema.

Para instalar .NET Core para SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bits) y openSUSE 42.2 en NET Core 2.x, u openSUSE 42.1 (64 bits) en .NET Core 1.x:

1. Obtenga los requisitos previos.
    ```bash
    sudo zypper install libunwind libicu
    ```
2. Descargue el archivo binario del SDK de .NET Core (tarball).

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

**SLES 12 SP2, openSUSE 42.2**

```bash
curl -sSL -o dotnet.tar.gz https://aka.ms/dotnet-sdk-2.0.0-linux-x64
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

**openSUSE 42.1**

```bash
curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
```

---
3. Extraiga los archivos binarios del SDK de .NET Core.
    ```bash
    sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
    ```
4. Agregue dotnet a su ruta de acceso.
    ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
    ```
5. Ejecute el comando `dotnet --help` para comprobar que la instalación se ha realizado correctamente.

     ```bash
     dotnet --help
     ```

> [!IMPORTANT]
> Si tiene problemas con la instalación de .NET Core 2.x en una versión o distribución de Linux compatible, vea el tema [Problemas conocidos de la versión 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) para sus versiones o distribuciones instaladas.
> [!IMPORTANT]
> Si tiene problemas con la instalación de .NET Core 1.x en una versión o distribución de Linux compatible, vea los temas [Problemas conocidos de la versión 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [Problemas conocidos de la versión 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) para sus versiones o distribuciones instaladas.
