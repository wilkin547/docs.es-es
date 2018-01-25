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
ms.workload: dotnetcore
ms.openlocfilehash: d3c5dde443f848831f7c0585633339c35213357b
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/20/2018
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="4e118-104">Requisitos previos para .NET Core en Linux</span><span class="sxs-lookup"><span data-stu-id="4e118-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="4e118-105">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux.</span><span class="sxs-lookup"><span data-stu-id="4e118-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="4e118-106">Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:</span><span class="sxs-lookup"><span data-stu-id="4e118-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="4e118-107">Línea de comandos con su editor favorito</span><span class="sxs-lookup"><span data-stu-id="4e118-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="4e118-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="4e118-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="4e118-109">Versiones de Linux compatibles</span><span class="sxs-lookup"><span data-stu-id="4e118-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4e118-111">.NET Core 2.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="4e118-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="4e118-112">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="4e118-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="4e118-113">NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="4e118-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="4e118-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="4e118-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="4e118-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="4e118-115">CentOS 7</span></span>
 * <span data-ttu-id="4e118-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="4e118-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="4e118-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="4e118-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="4e118-118">Debian 8.7 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4e118-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="4e118-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="4e118-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="4e118-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="4e118-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="4e118-121">openSUSE 42.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4e118-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="4e118-122">SUSE Enterprise Linux (SLES) 12 SP2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4e118-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="4e118-123">Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="4e118-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4e118-125">NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="4e118-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="4e118-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="4e118-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="4e118-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="4e118-127">CentOS 7</span></span>
* <span data-ttu-id="4e118-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="4e118-128">Oracle Linux 7</span></span>
* <span data-ttu-id="4e118-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="4e118-129">Fedora 24</span></span>
* <span data-ttu-id="4e118-130">Debian 8.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="4e118-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="4e118-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="4e118-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="4e118-132">Ubuntu 16.10 es compatible con la última versión de revisión de .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="4e118-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="4e118-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="4e118-133">Linux Mint 17</span></span>
* <span data-ttu-id="4e118-134">openSUSE 42.1 o versiones posteriores (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="4e118-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="4e118-135">Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="4e118-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="4e118-136">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="4e118-136">Linux distribution dependencies</span></span>

<span data-ttu-id="4e118-137">Los siguientes están diseñados a modo de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="4e118-137">The following are intended to be examples.</span></span> <span data-ttu-id="4e118-138">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="4e118-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="4e118-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="4e118-139">Ubuntu</span></span>

<span data-ttu-id="4e118-140">Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="4e118-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="4e118-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="4e118-141">libunwind8</span></span>
* <span data-ttu-id="4e118-142">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="4e118-142">liblttng-ust0</span></span>
* <span data-ttu-id="4e118-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="4e118-143">libcurl3</span></span>
* <span data-ttu-id="4e118-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="4e118-144">libssl1.0.0</span></span>
* <span data-ttu-id="4e118-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="4e118-145">libuuid1</span></span>
* <span data-ttu-id="4e118-146">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="4e118-146">libkrb5-3</span></span>
* <span data-ttu-id="4e118-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="4e118-147">zlib1g</span></span>
* <span data-ttu-id="4e118-148">libicu52 (para 14.X)</span><span class="sxs-lookup"><span data-stu-id="4e118-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="4e118-149">libicu55 (para 16.X)</span><span class="sxs-lookup"><span data-stu-id="4e118-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="4e118-150">libicu57 (para 17.X)</span><span class="sxs-lookup"><span data-stu-id="4e118-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="4e118-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="4e118-151">CentOS</span></span>

<span data-ttu-id="4e118-152">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="4e118-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="4e118-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="4e118-153">libunwind</span></span>
* <span data-ttu-id="4e118-154">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="4e118-154">lttng-ust</span></span>
* <span data-ttu-id="4e118-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="4e118-155">libcurl</span></span>
* <span data-ttu-id="4e118-156">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="4e118-156">openssl-libs</span></span>
* <span data-ttu-id="4e118-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="4e118-157">libuuid</span></span>
* <span data-ttu-id="4e118-158">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="4e118-158">krb5-libs</span></span>
* <span data-ttu-id="4e118-159">libicu</span><span class="sxs-lookup"><span data-stu-id="4e118-159">libicu</span></span>
* <span data-ttu-id="4e118-160">zlib</span><span class="sxs-lookup"><span data-stu-id="4e118-160">zlib</span></span>

<span data-ttu-id="4e118-161">Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).</span><span class="sxs-lookup"><span data-stu-id="4e118-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="4e118-162">Instalación de las dependencias de .NET Core con los instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="4e118-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="4e118-163">Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="4e118-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="4e118-164">Los instaladores nativos requieren acceso de administrador (sudo) para el servidor.</span><span class="sxs-lookup"><span data-stu-id="4e118-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="4e118-165">La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas.</span><span class="sxs-lookup"><span data-stu-id="4e118-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="4e118-166">Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="4e118-167">En Linux, existen dos opciones de paquete de instalador:</span><span class="sxs-lookup"><span data-stu-id="4e118-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="4e118-168">Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.</span><span class="sxs-lookup"><span data-stu-id="4e118-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="4e118-169">Usar los propios paquetes, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="4e118-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="4e118-170">Instalaciones de scripting con el script del instalador de .NET Core</span><span class="sxs-lookup"><span data-stu-id="4e118-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="4e118-171">Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="4e118-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="4e118-172">Puede descargar el script desde: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="4e118-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="4e118-173">El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas.</span><span class="sxs-lookup"><span data-stu-id="4e118-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="4e118-174">Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.</span><span class="sxs-lookup"><span data-stu-id="4e118-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e118-175">Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="4e118-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="4e118-176">Instalación de .NET Core para Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="4e118-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="4e118-177">Para instalar .NET Core en RHEL 7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="4e118-178">Habilite el canal .NET para Red Hat, disponible en su suscripción a RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="4e118-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="4e118-179">Para Red Hat Enterprise 7 Server, use:</span><span class="sxs-lookup"><span data-stu-id="4e118-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="4e118-180">Para Red Hat Enterprise 7 Workstation, use:</span><span class="sxs-lookup"><span data-stu-id="4e118-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="4e118-181">Para el nodo de ejecución de HPC de Red Hat Enterprise 7, use:</span><span class="sxs-lookup"><span data-stu-id="4e118-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="4e118-182">Instale la herramienta de scl.</span><span class="sxs-lookup"><span data-stu-id="4e118-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="4e118-183">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4e118-185">Para instalar el SDK y el runtime de .NET Core 2.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="4e118-186">Para habilitar el SDK o el runtime de .NET Core 2.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4e118-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="4e118-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="4e118-189">Para instalar el SDK y el runtime de .NET Core 1.1, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="4e118-190">Para habilitar el SDK y el runtime de .NET Core 1.1 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="4e118-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="4e118-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="4e118-192">Para instalar el SDK y el runtime de .NET Core 1.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="4e118-193">Para habilitar el SDK y el runtime de .NET Core 1.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="4e118-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="4e118-194">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="4e118-195">Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.</span><span class="sxs-lookup"><span data-stu-id="4e118-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="4e118-196">Instale .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="4e118-197">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="4e118-199">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="4e118-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="4e118-200">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="4e118-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="4e118-201">**Ubuntu 17.10**</span><span class="sxs-lookup"><span data-stu-id="4e118-201">**Ubuntu 17.10**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-artful-prod artful main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```
   <span data-ttu-id="4e118-202">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="4e118-202">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="4e118-203">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="4e118-203">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="4e118-204">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="4e118-204">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="4e118-205">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-205">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.1.3
   ```

4. <span data-ttu-id="4e118-206">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-206">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-207">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-207">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="4e118-208">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="4e118-208">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="4e118-209">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="4e118-209">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="4e118-210">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="4e118-210">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="4e118-211">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="4e118-211">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="4e118-212">Instale .NET Core 1.x en Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="4e118-212">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="4e118-213">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-213">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="4e118-214">Instalación .NET Core para Debian 8 o Debian 9 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-214">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="4e118-215">Para instalar .NET Core para Debian 8 o Debian 9 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="4e118-215">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="4e118-216">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-216">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="4e118-217">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="4e118-217">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-218">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-218">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="4e118-219">Instale los componentes del sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-219">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="4e118-220">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="4e118-220">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="4e118-221">Registre la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e118-221">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="4e118-222">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="4e118-222">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="4e118-223">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="4e118-223">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="4e118-224">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-224">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="4e118-225">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-225">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="4e118-226">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-226">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-227">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-227">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="4e118-228">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4e118-228">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="4e118-229">Descargue los archivos binarios del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="4e118-229">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="4e118-230">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-230">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="4e118-231">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-231">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="4e118-232">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-232">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="4e118-233">Instalación de .NET Core para Fedora 24, Fedora 25 o Fedora 26 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-233">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="4e118-234">Para instalar .NET Core 2.x en Fedora 26 o Fedora 25, o bien .NET Core 1.x en Fedora 24:</span><span class="sxs-lookup"><span data-stu-id="4e118-234">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="4e118-235">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-235">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="4e118-236">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="4e118-236">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-237">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-237">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="4e118-238">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="4e118-238">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="4e118-239">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e118-239">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="4e118-240">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="4e118-240">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="4e118-241">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-241">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="4e118-242">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-242">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-243">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-243">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="4e118-244">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="4e118-244">**Fedora 24**</span></span>

2. <span data-ttu-id="4e118-245">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4e118-245">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="4e118-246">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="4e118-246">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="4e118-247">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-247">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="4e118-248">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-248">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="4e118-249">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-249">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="4e118-250">Instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-250">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="4e118-251">Para instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="4e118-251">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="4e118-252">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-252">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="4e118-253">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="4e118-253">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-254">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-254">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="4e118-255">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e118-255">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="4e118-256">Agregue la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e118-256">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="4e118-257">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-257">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="4e118-258">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-258">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-259">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-259">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="4e118-260">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4e118-260">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="4e118-261">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="4e118-261">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="4e118-262">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-262">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="4e118-263">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-263">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="4e118-264">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-264">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="4e118-265">Instale .NET Core para SUSE Linux Enterprise Server (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-265">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="4e118-266">Para instalar .NET Core 2.x para SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="4e118-266">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="4e118-267">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-267">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="4e118-268">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="4e118-268">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="4e118-269">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-269">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="4e118-270">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-270">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="4e118-271">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-271">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="4e118-272">Instalación de .NET Core para openSUSE (64 bits)</span><span class="sxs-lookup"><span data-stu-id="4e118-272">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="4e118-273">Para instalar .NET Core 2.x para openSUSE o .NET Core 1.x para openSUSE (64 bits):</span><span class="sxs-lookup"><span data-stu-id="4e118-273">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="4e118-274">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="4e118-274">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="4e118-275">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="4e118-275">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="4e118-276">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="4e118-276">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="4e118-277">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4e118-277">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="4e118-278">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="4e118-278">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="4e118-279">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-279">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="4e118-280">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-280">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="4e118-281">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="4e118-281">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="4e118-282">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="4e118-282">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="4e118-283">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="4e118-283">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="4e118-284">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4e118-284">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="4e118-285">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="4e118-285">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="4e118-286">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e118-286">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="4e118-287">Si tiene problemas con la instalación de .NET Core 2.x en una versión o distribución de Linux compatible, vea el tema [Problemas conocidos de la versión 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="4e118-287">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="4e118-288">Si tiene problemas con la instalación de .NET Core 1.x en una versión o distribución de Linux compatible, vea los temas [Problemas conocidos de la versión 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [Problemas conocidos de la versión 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="4e118-288">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
