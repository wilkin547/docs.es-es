---
title: Requisitos previos para .NET Core en Linux
description: "Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/07/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.openlocfilehash: 04fdf26e150e6d489c0641588563f69f24835615
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="bd443-104">Requisitos previos para .NET Core en Linux</span><span class="sxs-lookup"><span data-stu-id="bd443-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="bd443-105">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux.</span><span class="sxs-lookup"><span data-stu-id="bd443-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="bd443-106">Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:</span><span class="sxs-lookup"><span data-stu-id="bd443-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="bd443-107">Línea de comandos con su editor favorito</span><span class="sxs-lookup"><span data-stu-id="bd443-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="bd443-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="bd443-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="bd443-109">Versiones de Linux compatibles</span><span class="sxs-lookup"><span data-stu-id="bd443-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="bd443-111">.NET Core 2.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="bd443-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="bd443-112">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="bd443-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="bd443-113">NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="bd443-113">NET Core 2.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

 * <span data-ttu-id="bd443-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="bd443-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="bd443-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bd443-115">CentOS 7</span></span>
 * <span data-ttu-id="bd443-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="bd443-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="bd443-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="bd443-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="bd443-118">Debian 8.7 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bd443-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="bd443-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="bd443-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="bd443-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="bd443-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="bd443-121">openSUSE 42.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bd443-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="bd443-122">SUSE Enterprise Linux (SLES) 12 SP2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bd443-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="bd443-123">Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="bd443-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bd443-125">NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="bd443-125">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="bd443-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="bd443-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="bd443-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="bd443-127">CentOS 7</span></span>
* <span data-ttu-id="bd443-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="bd443-128">Oracle Linux 7</span></span>
* <span data-ttu-id="bd443-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="bd443-129">Fedora 24</span></span>
* <span data-ttu-id="bd443-130">Debian 8.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="bd443-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="bd443-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="bd443-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="bd443-132">Ubuntu 16.10 es compatible con la última versión de revisión de .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="bd443-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="bd443-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="bd443-133">Linux Mint 17</span></span>
* <span data-ttu-id="bd443-134">openSUSE 42.1 o versiones posteriores (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="bd443-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="bd443-135">Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="bd443-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="bd443-136">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="bd443-136">Linux distribution dependencies</span></span>

<span data-ttu-id="bd443-137">A continuación está diseñados para ser ejemplos.</span><span class="sxs-lookup"><span data-stu-id="bd443-137">The following are intended to be examples.</span></span> <span data-ttu-id="bd443-138">Los nombres y versiones exactas pueden variar ligeramente en la distribución de Linux de elección.</span><span class="sxs-lookup"><span data-stu-id="bd443-138">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="bd443-139">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="bd443-139">Ubuntu</span></span>

<span data-ttu-id="bd443-140">Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="bd443-140">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="bd443-141">libunwind8</span><span class="sxs-lookup"><span data-stu-id="bd443-141">libunwind8</span></span>
* <span data-ttu-id="bd443-142">liblttng ust0</span><span class="sxs-lookup"><span data-stu-id="bd443-142">liblttng-ust0</span></span>
* <span data-ttu-id="bd443-143">libcurl3</span><span class="sxs-lookup"><span data-stu-id="bd443-143">libcurl3</span></span>
* <span data-ttu-id="bd443-144">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="bd443-144">libssl1.0.0</span></span>
* <span data-ttu-id="bd443-145">libuuid1</span><span class="sxs-lookup"><span data-stu-id="bd443-145">libuuid1</span></span>
* <span data-ttu-id="bd443-146">libkrb5</span><span class="sxs-lookup"><span data-stu-id="bd443-146">libkrb5</span></span>
* <span data-ttu-id="bd443-147">zlib1g</span><span class="sxs-lookup"><span data-stu-id="bd443-147">zlib1g</span></span>
* <span data-ttu-id="bd443-148">libicu52 (para 14.X)</span><span class="sxs-lookup"><span data-stu-id="bd443-148">libicu52 (for 14.X)</span></span>
* <span data-ttu-id="bd443-149">libicu55 (para 16.X)</span><span class="sxs-lookup"><span data-stu-id="bd443-149">libicu55 (for 16.X)</span></span>
* <span data-ttu-id="bd443-150">libicu57 (para 17.X)</span><span class="sxs-lookup"><span data-stu-id="bd443-150">libicu57 (for 17.X)</span></span>

### <a name="centos"></a><span data-ttu-id="bd443-151">CentOS</span><span class="sxs-lookup"><span data-stu-id="bd443-151">CentOS</span></span>

<span data-ttu-id="bd443-152">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="bd443-152">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="bd443-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="bd443-153">libunwind</span></span>
* <span data-ttu-id="bd443-154">lttng ust</span><span class="sxs-lookup"><span data-stu-id="bd443-154">lttng-ust</span></span>
* <span data-ttu-id="bd443-155">libcurl</span><span class="sxs-lookup"><span data-stu-id="bd443-155">libcurl</span></span>
* <span data-ttu-id="bd443-156">bibliotecas OpenSSL</span><span class="sxs-lookup"><span data-stu-id="bd443-156">openssl-libs</span></span>
* <span data-ttu-id="bd443-157">libuuid</span><span class="sxs-lookup"><span data-stu-id="bd443-157">libuuid</span></span>
* <span data-ttu-id="bd443-158">bibliotecas de krb5</span><span class="sxs-lookup"><span data-stu-id="bd443-158">krb5-libs</span></span>
* <span data-ttu-id="bd443-159">libicu</span><span class="sxs-lookup"><span data-stu-id="bd443-159">libicu</span></span>
* <span data-ttu-id="bd443-160">zlib</span><span class="sxs-lookup"><span data-stu-id="bd443-160">zlib</span></span>

<span data-ttu-id="bd443-161">Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).</span><span class="sxs-lookup"><span data-stu-id="bd443-161">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="bd443-162">Instalación de las dependencias de .NET Core con los instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="bd443-162">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="bd443-163">Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="bd443-163">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="bd443-164">Los instaladores nativos requieren acceso de administrador (sudo) para el servidor.</span><span class="sxs-lookup"><span data-stu-id="bd443-164">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="bd443-165">La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas.</span><span class="sxs-lookup"><span data-stu-id="bd443-165">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="bd443-166">Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-166">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="bd443-167">En Linux, existen dos opciones de paquete de instalador:</span><span class="sxs-lookup"><span data-stu-id="bd443-167">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="bd443-168">Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.</span><span class="sxs-lookup"><span data-stu-id="bd443-168">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="bd443-169">Usar los propios paquetes, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="bd443-169">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="bd443-170">Instalaciones de scripting con el script del instalador de .NET Core</span><span class="sxs-lookup"><span data-stu-id="bd443-170">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="bd443-171">Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="bd443-171">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="bd443-172">Puede descargar la secuencia de comandos: https://dot.net/v1/dotnet-install.sh</span><span class="sxs-lookup"><span data-stu-id="bd443-172">You can download the script from: https://dot.net/v1/dotnet-install.sh</span></span>

<span data-ttu-id="bd443-173">El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas.</span><span class="sxs-lookup"><span data-stu-id="bd443-173">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="bd443-174">Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.</span><span class="sxs-lookup"><span data-stu-id="bd443-174">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd443-175">Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="bd443-175">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="bd443-176">Instalación de .NET Core para Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="bd443-176">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="bd443-177">Para instalar .NET Core en RHEL 7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-177">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="bd443-178">Habilite el canal .NET para Red Hat, disponible en su suscripción a RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="bd443-178">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="bd443-179">Para Red Hat Enterprise 7 Server, use:</span><span class="sxs-lookup"><span data-stu-id="bd443-179">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="bd443-180">Para Red Hat Enterprise 7 Workstation, use:</span><span class="sxs-lookup"><span data-stu-id="bd443-180">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="bd443-181">Para el nodo de ejecución de HPC de Red Hat Enterprise 7, use:</span><span class="sxs-lookup"><span data-stu-id="bd443-181">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="bd443-182">Instale la herramienta de scl.</span><span class="sxs-lookup"><span data-stu-id="bd443-182">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="bd443-183">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-183">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-184">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-184">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="bd443-185">Para instalar el SDK y el runtime de .NET Core 2.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-185">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="bd443-186">Para habilitar el SDK o el runtime de .NET Core 2.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-186">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-187">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-187">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bd443-188">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="bd443-188">**.NET Core 1.1**</span></span>

<span data-ttu-id="bd443-189">Para instalar el SDK y el runtime de .NET Core 1.1, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-189">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="bd443-190">Para habilitar el SDK y el runtime de .NET Core 1.1 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-190">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="bd443-191">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="bd443-191">**.NET Core 1.0**</span></span>

<span data-ttu-id="bd443-192">Para instalar el SDK y el runtime de .NET Core 1.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-192">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="bd443-193">Para habilitar el SDK y el runtime de .NET Core 1.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="bd443-193">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="bd443-194">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-194">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="bd443-195">Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.</span><span class="sxs-lookup"><span data-stu-id="bd443-195">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="bd443-196">Instale .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-196">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="bd443-197">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-197">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-198">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-198">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="bd443-199">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="bd443-199">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="bd443-200">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="bd443-200">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="bd443-201">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="bd443-201">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="bd443-202">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="bd443-202">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="bd443-203">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="bd443-203">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="bd443-204">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-204">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="bd443-205">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-205">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-206">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-206">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="bd443-207">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="bd443-207">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="bd443-208">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="bd443-208">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="bd443-209">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="bd443-209">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="bd443-210">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="bd443-210">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="bd443-211">Instale .NET Core 1.x en Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="bd443-211">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="bd443-212">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-212">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="bd443-213">Instalación .NET Core para Debian 8 o Debian 9 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-213">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="bd443-214">Para instalar .NET Core para Debian 8 o Debian 9 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="bd443-214">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="bd443-215">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-215">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="bd443-216">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="bd443-216">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-217">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-217">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="bd443-218">Instale los componentes del sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-218">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="bd443-219">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="bd443-219">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="bd443-220">Registre la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd443-220">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="bd443-221">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="bd443-221">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="bd443-222">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="bd443-222">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="bd443-223">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-223">Install .NET Core SDK.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="bd443-224">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-224">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```
   
7. <span data-ttu-id="bd443-225">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-225">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```   
  

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-226">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-226">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="bd443-227">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="bd443-227">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="bd443-228">Descargue los archivos binarios del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="bd443-228">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="bd443-229">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-229">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="bd443-230">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-230">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

6. <span data-ttu-id="bd443-231">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-231">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="bd443-232">Instalación de .NET Core para Fedora 24, Fedora 25 o Fedora 26 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-232">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="bd443-233">Para instalar .NET Core 2.x en Fedora 26 o Fedora 25, o bien .NET Core 1.x en Fedora 24:</span><span class="sxs-lookup"><span data-stu-id="bd443-233">To install .NET Core 2.x on Fedora 26 or Fedora 25, or .NET Core 1.x on Fedora 24:</span></span>

1. <span data-ttu-id="bd443-234">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-234">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="bd443-235">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="bd443-235">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-236">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-236">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="bd443-237">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="bd443-237">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="bd443-238">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd443-238">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="bd443-239">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="bd443-239">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="bd443-240">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-240">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="bd443-241">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-241">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-242">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-242">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="bd443-243">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="bd443-243">**Fedora 24**</span></span>

2. <span data-ttu-id="bd443-244">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="bd443-244">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="bd443-245">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="bd443-245">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="bd443-246">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-246">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="bd443-247">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-247">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="bd443-248">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-248">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="bd443-249">Instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-249">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="bd443-250">Para instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="bd443-250">To install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="bd443-251">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-251">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="bd443-252">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="bd443-252">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-253">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-253">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="bd443-254">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd443-254">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="bd443-255">Agregue la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd443-255">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="bd443-256">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-256">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="bd443-257">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-257">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-258">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-258">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="bd443-259">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="bd443-259">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="bd443-260">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="bd443-260">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="bd443-261">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-261">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="bd443-262">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-262">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="bd443-263">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-263">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="bd443-264">Instale .NET Core para SUSE Linux Enterprise Server (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-264">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="bd443-265">Para instalar .NET Core 2.x para SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="bd443-265">To install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="bd443-266">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-266">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="bd443-267">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="bd443-267">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="bd443-268">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-268">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="bd443-269">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-269">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="bd443-270">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-270">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="bd443-271">Instalación de .NET Core para openSUSE (64 bits)</span><span class="sxs-lookup"><span data-stu-id="bd443-271">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="bd443-272">Para instalar .NET Core 2.x para openSUSE o .NET Core 1.x para openSUSE (64 bits):</span><span class="sxs-lookup"><span data-stu-id="bd443-272">To install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="bd443-273">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="bd443-273">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="bd443-274">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="bd443-274">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="bd443-275">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="bd443-275">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="bd443-276">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bd443-276">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="bd443-277">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="bd443-277">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="bd443-278">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-278">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="bd443-279">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-279">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="bd443-280">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="bd443-280">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="bd443-281">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="bd443-281">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="bd443-282">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="bd443-282">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="bd443-283">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="bd443-283">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="bd443-284">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="bd443-284">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="bd443-285">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="bd443-285">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="bd443-286">Si tiene problemas con la instalación de .NET Core 2.x en una versión o distribución de Linux compatible, vea el tema [Problemas conocidos de la versión 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="bd443-286">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="bd443-287">Si tiene problemas con la instalación de .NET Core 1.x en una versión o distribución de Linux compatible, vea los temas [Problemas conocidos de la versión 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [Problemas conocidos de la versión 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="bd443-287">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>
