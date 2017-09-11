---
title: Requisitos previos para .NET Core en Linux
description: "Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux."
keywords: .NET, .NET Core, Linux, debian, ubuntu, RHEL, centOS,
author: jralexander
ms.author: johalex
ms.date: 09/01/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: c33b1241-ab66-4583-9eba-52cf51146f5a
ms.translationtype: HT
ms.sourcegitcommit: 7bbb8405f39a52d2798fd1dbc78f3116cb3bedbb
ms.openlocfilehash: 9864ffa31caa007cb649a9e6e8913863d9cb2c35
ms.contentlocale: es-es
ms.lasthandoff: 09/05/2017

---

# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="7ed6a-104">Requisitos previos para .NET Core en Linux</span><span class="sxs-lookup"><span data-stu-id="7ed6a-104">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="7ed6a-105">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-105">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="7ed6a-106">Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-106">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="7ed6a-107">Línea de comandos con su editor favorito</span><span class="sxs-lookup"><span data-stu-id="7ed6a-107">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="7ed6a-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="7ed6a-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

## <a name="supported-linux-versions"></a><span data-ttu-id="7ed6a-109">Versiones de Linux compatibles</span><span class="sxs-lookup"><span data-stu-id="7ed6a-109">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-110">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-110">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7ed6a-111">.NET Core 2.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-111">.NET Core 2.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="7ed6a-112">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-112">There is a single Linux build (per chip architecture) for supported Linux distros.</span></span>

<span data-ttu-id="7ed6a-113">.NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux x64:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-113">NET Core 2.x is supported on the following Linux x64 distributions/versions:</span></span>

 * <span data-ttu-id="7ed6a-114">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-114">Red Hat Enterprise Linux 7</span></span>
 * <span data-ttu-id="7ed6a-115">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-115">CentOS 7</span></span>
 * <span data-ttu-id="7ed6a-116">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-116">Oracle Linux 7</span></span>
 * <span data-ttu-id="7ed6a-117">Fedora 25, Fedora 26</span><span class="sxs-lookup"><span data-stu-id="7ed6a-117">Fedora 25, Fedora 26</span></span>
 * <span data-ttu-id="7ed6a-118">Debian 8.7 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7ed6a-118">Debian 8.7 or later versions</span></span> 
 * <span data-ttu-id="7ed6a-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span><span class="sxs-lookup"><span data-stu-id="7ed6a-119">Ubuntu 17.04, Ubuntu 16.04, Ubuntu 14.04</span></span>
 * <span data-ttu-id="7ed6a-120">Linux Mint 18, Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="7ed6a-120">Linux Mint 18, Linux Mint 17</span></span>
 * <span data-ttu-id="7ed6a-121">openSUSE 42.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7ed6a-121">openSUSE 42.2 or later versions</span></span>
 * <span data-ttu-id="7ed6a-122">SUSE Enterprise Linux (SLES) 12 SP2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7ed6a-122">SUSE Enterprise Linux (SLES) 12 SP2 or later versions</span></span>

<span data-ttu-id="7ed6a-123">Vea [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) (.NET Core 2.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 2.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-123">See [.NET Core 2.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md) for the complete list of .NET Core 2.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-124">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-124">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7ed6a-125">.NET Core 1.x se admite en las siguientes versiones o distribuciones de Linux x64:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-125">.NET Core 1.x is supported on the following Linux x64 distributions/versions:</span></span>

* <span data-ttu-id="7ed6a-126">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-126">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="7ed6a-127">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-127">CentOS 7</span></span>
* <span data-ttu-id="7ed6a-128">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-128">Oracle Linux 7</span></span>
* <span data-ttu-id="7ed6a-129">Fedora 24</span><span class="sxs-lookup"><span data-stu-id="7ed6a-129">Fedora 24</span></span>
* <span data-ttu-id="7ed6a-130">Debian 8.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="7ed6a-130">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="7ed6a-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span><span class="sxs-lookup"><span data-stu-id="7ed6a-131">Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10\*</span></span>
 * <span data-ttu-id="7ed6a-132">Ubuntu 16.10 es compatible con la última versión de revisión de .NET Core 1.1</span><span class="sxs-lookup"><span data-stu-id="7ed6a-132">Ubuntu 16.10 is supported by the latest patch release of .NET Core 1.1</span></span>
* <span data-ttu-id="7ed6a-133">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="7ed6a-133">Linux Mint 17</span></span>
* <span data-ttu-id="7ed6a-134">openSUSE 42.1 o versiones posteriores (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-134">openSUSE 42.1 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="7ed6a-135">Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-135">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="7ed6a-136">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="7ed6a-136">Linux distribution dependencies</span></span>

### <a name="ubuntu"></a><span data-ttu-id="7ed6a-137">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="7ed6a-137">Ubuntu</span></span>

<span data-ttu-id="7ed6a-138">Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-138">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7ed6a-139">libunwind8</span><span class="sxs-lookup"><span data-stu-id="7ed6a-139">libunwind8</span></span>
* <span data-ttu-id="7ed6a-140">libunwind8-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-140">libunwind8-dev</span></span>
* <span data-ttu-id="7ed6a-141">gettext</span><span class="sxs-lookup"><span data-stu-id="7ed6a-141">gettext</span></span>
* <span data-ttu-id="7ed6a-142">libicu-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-142">libicu-dev</span></span>
* <span data-ttu-id="7ed6a-143">liblttng-ust-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-143">liblttng-ust-dev</span></span>
* <span data-ttu-id="7ed6a-144">libcurl4-openssl-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-144">libcurl4-openssl-dev</span></span>
* <span data-ttu-id="7ed6a-145">libssl-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-145">libssl-dev</span></span>
* <span data-ttu-id="7ed6a-146">uuid-dev</span><span class="sxs-lookup"><span data-stu-id="7ed6a-146">uuid-dev</span></span>
* <span data-ttu-id="7ed6a-147">unzip</span><span class="sxs-lookup"><span data-stu-id="7ed6a-147">unzip</span></span>

### <a name="centos"></a><span data-ttu-id="7ed6a-148">CentOS</span><span class="sxs-lookup"><span data-stu-id="7ed6a-148">CentOS</span></span>

<span data-ttu-id="7ed6a-149">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-149">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="7ed6a-150">deltarpm</span><span class="sxs-lookup"><span data-stu-id="7ed6a-150">deltarpm</span></span>
* <span data-ttu-id="7ed6a-151">epel-release</span><span class="sxs-lookup"><span data-stu-id="7ed6a-151">epel-release</span></span>
* <span data-ttu-id="7ed6a-152">unzip</span><span class="sxs-lookup"><span data-stu-id="7ed6a-152">unzip</span></span>
* <span data-ttu-id="7ed6a-153">libunwind</span><span class="sxs-lookup"><span data-stu-id="7ed6a-153">libunwind</span></span>
* <span data-ttu-id="7ed6a-154">gettext</span><span class="sxs-lookup"><span data-stu-id="7ed6a-154">gettext</span></span>
* <span data-ttu-id="7ed6a-155">libcurl-devel</span><span class="sxs-lookup"><span data-stu-id="7ed6a-155">libcurl-devel</span></span>
* <span data-ttu-id="7ed6a-156">openssl-devel</span><span class="sxs-lookup"><span data-stu-id="7ed6a-156">openssl-devel</span></span>
* <span data-ttu-id="7ed6a-157">zlib</span><span class="sxs-lookup"><span data-stu-id="7ed6a-157">zlib</span></span>
* <span data-ttu-id="7ed6a-158">libicu-devel</span><span class="sxs-lookup"><span data-stu-id="7ed6a-158">libicu-devel</span></span>

<span data-ttu-id="7ed6a-159">Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-159">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="7ed6a-160">Instalación de las dependencias de .NET Core con los instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="7ed6a-160">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="7ed6a-161">Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-161">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="7ed6a-162">Los instaladores nativos requieren acceso de administrador (sudo) para el servidor.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-162">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="7ed6a-163">La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-163">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="7ed6a-164">Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-164">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="7ed6a-165">En Linux, existen dos opciones de paquete de instalador:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-165">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="7ed6a-166">Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-166">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="7ed6a-167">Usar los propios paquetes, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-167">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="7ed6a-168">Instalaciones de scripting con el script del instalador de .NET Core</span><span class="sxs-lookup"><span data-stu-id="7ed6a-168">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="7ed6a-169">Los scripts de `dotnet-install` se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de CLI y del entorno de tiempo de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-169">The `dotnet-install` scripts are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="7ed6a-170">Puede descargar los scripts del [repositorio de GitHub de CLI](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-170">You can download the scripts from the [CLI GitHub repo](https://github.com/dotnet/cli/tree/rel/1.0.0/scripts/obtain).</span></span>

<span data-ttu-id="7ed6a-171">El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-171">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="7ed6a-172">Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-172">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ed6a-173">Antes de ejecutar el script, instale las [dependencias](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md) necesarias.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-173">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

## <a name="install-net-core-for-red-hat-enterprise-linux-rhel-7"></a><span data-ttu-id="7ed6a-174">Instalación de .NET Core para Red Hat Enterprise Linux (RHEL) 7</span><span class="sxs-lookup"><span data-stu-id="7ed6a-174">Install .NET Core for Red Hat Enterprise Linux (RHEL) 7</span></span>

<span data-ttu-id="7ed6a-175">Para instalar .NET Core en RHEL 7, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-175">To install .NET Core on RHEL 7:</span></span>

1. <span data-ttu-id="7ed6a-176">Habilite el canal .NET para Red Hat, disponible en su suscripción a RHEL 7.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-176">Enable the Red Hat .NET channel, available under your RHEL 7 subscription.</span></span>
    * <span data-ttu-id="7ed6a-177">Para Red Hat Enterprise 7 Server, use:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-177">For Red Hat Enterprise 7 Server, use:</span></span>
    
         ```bash
         subscription-manager repos --enable=rhel-7-server-dotnet-rpms
         ```
    
    * <span data-ttu-id="7ed6a-178">Para Red Hat Enterprise 7 Workstation, use:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-178">For Red Hat Enterprise 7 Workstation, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-workstation-dotnet-rpms
         ```
    
    * <span data-ttu-id="7ed6a-179">Para el nodo de ejecución de HPC de Red Hat Enterprise 7, use:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-179">For Red Hat Enterprise 7 HPC Compute Node, use:</span></span>
    
        ```bash
        subscription-manager repos --enable=rhel-7-hpc-node-dotnet-rpms
        ```

2. <span data-ttu-id="7ed6a-180">Instale la herramienta de scl.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-180">Install the scl tool.</span></span>

    ```bash
    yum install scl-utils
    ```
    
3. <span data-ttu-id="7ed6a-181">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-181">Install .NET Core</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-182">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-182">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7ed6a-183">Para instalar el SDK y el runtime de .NET Core 2.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-183">Install .NET Core 2.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnet20
   ```

<span data-ttu-id="7ed6a-184">Para habilitar el SDK o el runtime de .NET Core 2.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-184">Enable .NET Core 2.0 SDK/Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnet20 bash
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-185">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-185">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7ed6a-186">**.NET Core 1.1**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-186">**.NET Core 1.1**</span></span>

<span data-ttu-id="7ed6a-187">Para instalar el SDK y el runtime de .NET Core 1.1, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-187">Install .NET Core 1.1 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore11
   ```

<span data-ttu-id="7ed6a-188">Para habilitar el SDK y el runtime de .NET Core 1.1 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-188">Enable .NET Core 1.1 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore11 bash
   ```

<span data-ttu-id="7ed6a-189">**.NET Core 1.0**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-189">**.NET Core 1.0**</span></span>

<span data-ttu-id="7ed6a-190">Para instalar el SDK y el runtime de .NET Core 1.0, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-190">Install .NET Core 1.0 SDK and Runtime:</span></span>

   ```bash
   yum install rh-dotnetcore10
   ```

<span data-ttu-id="7ed6a-191">Para habilitar el SDK y el runtime de .NET Core 1.0 en su entorno, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-191">Enable .NET Core 1.0 SDK and Runtime for your environment:</span></span>

   ```bash
   scl enable rh-dotnetcore10 bash
   ```

---
4. <span data-ttu-id="7ed6a-192">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-192">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

     ```bash
     dotnet --version
     ```

<span data-ttu-id="7ed6a-193">Para obtener ayuda de registro de acceso al canal .NET para Red Hat, vea [Capítulo 1 de la guía de introducción de .NET Core 1.1](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) en Red Hat.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-193">For Red Hat .NET channel access registration help, see [Chapter 1 of the .NET Core 1.1 Getting Started Guide](https://access.redhat.com/documentation/en/net-core/1.1/paged/getting-started-guide/) at Red Hat.</span></span>

## <a name="install-net-core-for-ubuntu-1404-ubuntu-1604-ubuntu-1610--linux-mint-17-linux-mint-18-64-bit"></a><span data-ttu-id="7ed6a-194">Instale .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-194">Install .NET Core for Ubuntu 14.04, Ubuntu 16.04, Ubuntu 16.10 & Linux Mint 17, Linux Mint 18 (64 bit)</span></span>

1. <span data-ttu-id="7ed6a-195">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-195">Remove any **previous preview** versions of .NET Core from your system.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-196">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-196">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7ed6a-197">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-197">Register the Microsoft Product key as trusted.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```

3. <span data-ttu-id="7ed6a-198">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-198">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="7ed6a-199">**Ubuntu 17.04**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-199">**Ubuntu 17.04**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-zesty-prod zesty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="7ed6a-200">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-200">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-xenial-prod xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

   <span data-ttu-id="7ed6a-201">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-201">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-ubuntu-trusty-prod trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-get update
   ```

4. <span data-ttu-id="7ed6a-202">Instale .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-202">Install .NET Core.</span></span>

   ```bash
   sudo apt-get install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="7ed6a-203">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-203">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-204">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-204">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7ed6a-205">Configure la versión deseada de la fuente del paquete de host.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-205">Set up the desired version host package feed.</span></span>

   <span data-ttu-id="7ed6a-206">**Ubuntu 16.10**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-206">**Ubuntu 16.10**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ yakkety main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

  <span data-ttu-id="7ed6a-207">**Ubuntu 16.04 / Linux Mint 18**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-207">**Ubuntu 16.04 / Linux Mint 18**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ xenial main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```
    
   <span data-ttu-id="7ed6a-208">**Ubuntu 14.04 / Linux Mint 17**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-208">**Ubuntu 14.04 / Linux Mint 17**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://apt-mo.trafficmanager.net/repos/dotnet-release/ trusty main" > /etc/apt/sources.list.d/dotnetdev.list'
   sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv-keys B02C46DF417A0893
   sudo apt-get update
   ```

3. <span data-ttu-id="7ed6a-209">Instale .NET Core 1.x en Ubuntu o Linux Mint:</span><span class="sxs-lookup"><span data-stu-id="7ed6a-209">Install .NET Core 1.x on Ubuntu or Linux Mint:</span></span>

   ```bash
   sudo apt-get install dotnet-dev-1.0.4
   ```

4. <span data-ttu-id="7ed6a-210">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-210">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

---

 ## <a name="install-net-core-for-debian-8-or-debian-9-64-bit"></a><span data-ttu-id="7ed6a-211">Instalación .NET Core para Debian 8 o Debian 9 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-211">Install .NET Core for Debian 8 or Debian 9 (64 bit)</span></span>

<span data-ttu-id="7ed6a-212">Para instalar .NET Core para Debian 8 o Debian 9 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="7ed6a-212">To install .NET Core on Debian 8 or Debian 9 (64 bit):</span></span>

1. <span data-ttu-id="7ed6a-213">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-213">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed6a-214">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-214">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-215">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-215">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7ed6a-216">Instale los componentes del sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-216">Install system components.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install curl libunwind8 gettext apt-transport-https
   ```
   
3. <span data-ttu-id="7ed6a-217">Registre la clave de producto de Microsoft como de confianza.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-217">Register the trusted Microsoft Product key.</span></span>

   ```bash
   curl https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.gpg
   sudo mv microsoft.gpg /etc/apt/trusted.gpg.d/microsoft.gpg
   ```
   
4. <span data-ttu-id="7ed6a-218">Registre la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-218">Register the Microsoft Product feed.</span></span>

   <span data-ttu-id="7ed6a-219">**Debian 9 (Stretch)**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-219">**Debian 9 (Stretch)**</span></span>

   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-stretch-prod stretch main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
   <span data-ttu-id="7ed6a-220">**Debian 8 (Jessie)**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-220">**Debian 8 (Jessie)**</span></span>
   
   ```bash
   sudo sh -c 'echo "deb [arch=amd64] https://packages.microsoft.com/repos/microsoft-debian-jessie-prod jessie main" > /etc/apt/sources.list.d/dotnetdev.list'
   ```
   
5. <span data-ttu-id="7ed6a-221">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-221">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo apt-get update
   sudo apt-get install dotnet-sdk-2.0.0
   ```

6. <span data-ttu-id="7ed6a-222">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-222">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-223">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-223">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7ed6a-224">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-224">Get the prerequisites.</span></span>

   ```bash
   sudo apt-get install curl libunwind8 gettext
   ```

3. <span data-ttu-id="7ed6a-225">Descargue los archivos binarios del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-225">Download the .NET Core SDK binaries (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848826
   ```

4. <span data-ttu-id="7ed6a-226">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-226">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7ed6a-227">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-227">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="7ed6a-228">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-228">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-fedora-24-fedora-25-or-fedora-26-64-bit"></a><span data-ttu-id="7ed6a-229">Instalación de .NET Core para Fedora 24, Fedora 25 o Fedora 26 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-229">Install .NET Core for Fedora 24, Fedora 25, or Fedora 26 (64 bit)</span></span>

<span data-ttu-id="7ed6a-230">Para instalar .NET Core para Fedora 26, Fedora 25 (.NET Core 2.x) o Fedora 24 (.NET Core 1.x):</span><span class="sxs-lookup"><span data-stu-id="7ed6a-230">To Install .NET Core for Fedora 26, Fedora 25 (.NET Core 2.x) or Fedora 24 (.NET Core 1.x):</span></span>

1. <span data-ttu-id="7ed6a-231">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-231">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed6a-232">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-232">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-233">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-233">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="7ed6a-234">**Fedora 26 o Fedora 25**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-234">**Fedora 26 or Fedora 25**</span></span>

2. <span data-ttu-id="7ed6a-235">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-235">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7ed6a-236">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-236">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="7ed6a-237">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-237">Install the .NET Core SDK.</span></span>

   ```bash
   sudo dnf update
   sudo dnf install libunwind libicu
   sudo dnf install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7ed6a-238">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-238">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-239">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-239">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="7ed6a-240">**Fedora 24**</span><span class="sxs-lookup"><span data-stu-id="7ed6a-240">**Fedora 24**</span></span>

2. <span data-ttu-id="7ed6a-241">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-241">Get the prerequisites.</span></span>

   ```bash
   sudo dnf install libunwind libicu
   ```

3. <span data-ttu-id="7ed6a-242">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-242">Download the .NET Core SDK binary  (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848833
   ```

4. <span data-ttu-id="7ed6a-243">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-243">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7ed6a-244">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-244">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="7ed6a-245">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-245">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-centos-71-64-bit--oracle-linux-71-64-bit"></a><span data-ttu-id="7ed6a-246">Instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-246">Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit)</span></span>

<span data-ttu-id="7ed6a-247">Para instalar .NET Core para CentOS 7.1 (64 bits) y Oracle Linux 7.1 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="7ed6a-247">To Install .NET Core for CentOS 7.1 (64 bit) & Oracle Linux 7.1 (64 bit):</span></span>

1. <span data-ttu-id="7ed6a-248">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-248">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed6a-249">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-249">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-250">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-250">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7ed6a-251">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-251">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7ed6a-252">Agregue la fuente de producto de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-252">Add the Microsoft Product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/yum.repos.d/dotnetdev.repo'
   ```

4. <span data-ttu-id="7ed6a-253">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-253">Install the .NET Core SDK.</span></span>

   ```bash
   sudo yum update
   sudo yum install libunwind libicu
   sudo yum install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7ed6a-254">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-254">Add dotnet to your PATH</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-255">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-255">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7ed6a-256">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-256">Get the prerequisites.</span></span>

   ```bash
   sudo yum install libunwind libicu
   ```
   
3. <span data-ttu-id="7ed6a-257">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-257">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848821
   ```

4. <span data-ttu-id="7ed6a-258">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-258">Extract the .NET Core SDK binaries.</span></span>

   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7ed6a-259">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-259">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```

---

6. <span data-ttu-id="7ed6a-260">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-260">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

## <a name="install-net-core-for-suse-linux-enterprise-server-64-bit"></a><span data-ttu-id="7ed6a-261">Instale .NET Core para SUSE Linux Enterprise Server (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-261">Install .NET Core for SUSE Linux Enterprise Server (64 bit)</span></span>

<span data-ttu-id="7ed6a-262">Para instalar .NET Core 2.x para SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bits):</span><span class="sxs-lookup"><span data-stu-id="7ed6a-262">To Install .NET Core 2.x for SUSE Linux Enterprise Server (SLES) 12 SP2 (64 bit):</span></span>

1. <span data-ttu-id="7ed6a-263">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-263">Remove any **previous preview** versions of .NET Core from your system.</span></span>

2. <span data-ttu-id="7ed6a-264">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-264">Add the dotnet product feed.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ```

3. <span data-ttu-id="7ed6a-265">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-265">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

4. <span data-ttu-id="7ed6a-266">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-266">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

5. <span data-ttu-id="7ed6a-267">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-267">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```
   
## <a name="install-net-core-for-opensuse-64-bit"></a><span data-ttu-id="7ed6a-268">Instalación de .NET Core para openSUSE (64 bits)</span><span class="sxs-lookup"><span data-stu-id="7ed6a-268">Install .NET Core for openSUSE (64 bit)</span></span>

<span data-ttu-id="7ed6a-269">Para instalar .NET Core 2.x para openSUSE o .NET Core 1.x para openSUSE (64 bits):</span><span class="sxs-lookup"><span data-stu-id="7ed6a-269">To Install .NET Core 2.x for openSUSE or .NET Core 1.x for openSUSE (64 bit):</span></span>

1. <span data-ttu-id="7ed6a-270">Quite cualquier **versión preliminar anterior** de .NET Core de su sistema.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-270">Remove any **previous preview** versions of .NET Core from your system.</span></span>

> [!NOTE]
> <span data-ttu-id="7ed6a-271">Es necesario un directorio controlado por el usuario para instalaciones del sistema Linux de tar.gz.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-271">A user-controlled directory is required for Linux system installs from tar.gz.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="7ed6a-272">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-272">.NET Core 2.x</span></span>](#tab/netcore2x)

2. <span data-ttu-id="7ed6a-273">Registre la fuente de firma de Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-273">Register the Microsoft signature key.</span></span>

   ```bash
   sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
   ```

3. <span data-ttu-id="7ed6a-274">Agregue la fuente de producto dotnet.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-274">Add the dotnet product feed.</span></span>

   ```bash
   sudo sh -c 'echo -e "[packages-microsoft-com-prod]\nname=packages-microsoft-com-prod \nbaseurl=https://packages.microsoft.com/yumrepos/microsoft-rhel7.3-prod\nenabled=1\ngpgcheck=1\ngpgkey=https://packages.microsoft.com/keys/microsoft.asc" > /etc/zypp/repos.d/dotnetdev.repo'
   ``` 

4. <span data-ttu-id="7ed6a-275">Instale el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-275">Install the .NET Core SDK.</span></span>

   ```bash
   sudo zypper update
   sudo zypper install libunwind libicu
   sudo zypper install dotnet-sdk-2.0.0
   ```

5. <span data-ttu-id="7ed6a-276">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-276">Add dotnet to your PATH.</span></span>

   ```bash
   export PATH=$PATH:$HOME/dotnet
   ```

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="7ed6a-277">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="7ed6a-277">.NET Core 1.x</span></span>](#tab/netcore1x)

2. <span data-ttu-id="7ed6a-278">Obtenga los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-278">Get the prerequisites.</span></span>

   ```bash
   sudo zypper install libunwind libicu
   ```

3. <span data-ttu-id="7ed6a-279">Descargue el archivo binario del SDK de .NET Core (tarball).</span><span class="sxs-lookup"><span data-stu-id="7ed6a-279">Download the .NET Core SDK binary (tarball).</span></span>

   ```bash
   curl -sSL -o dotnet.tar.gz https://go.microsoft.com/fwlink/?linkid=848824
   ```

4. <span data-ttu-id="7ed6a-280">Extraiga los archivos binarios del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-280">Extract the .NET Core SDK binaries.</span></span>
   
   ```bash
   sudo mkdir -p /opt/dotnet && sudo tar zxf dotnet.tar.gz -C /opt/dotnet
   ```

5. <span data-ttu-id="7ed6a-281">Agregue dotnet a su ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-281">Add dotnet to your PATH.</span></span>

   ```bash
   sudo ln -s /opt/dotnet/dotnet /usr/local/bin
   ```
   
---

6. <span data-ttu-id="7ed6a-282">Ejecute el comando `dotnet --version` para comprobar que la instalación se ha realizado correctamente.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-282">Run the `dotnet --version` command to prove the installation succeeded.</span></span>

   ```bash
   dotnet --version
   ```

> [!IMPORTANT]
> <span data-ttu-id="7ed6a-283">Si tiene problemas con la instalación de .NET Core 2.x en una versión o distribución de Linux compatible, vea el tema [Problemas conocidos de la versión 2.0](https://github.com/dotnet/core/tree/master/release-notes/2.0) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-283">If you have problems with the .NET Core 2.x installation on a supported Linux distribution/version, consult the [2.0 Known issues](https://github.com/dotnet/core/tree/master/release-notes/2.0) topic for your installed distributions/versions.</span></span> 
>
> <span data-ttu-id="7ed6a-284">Si tiene problemas con la instalación de .NET Core 1.x en una versión o distribución de Linux compatible, vea los temas [Problemas conocidos de la versión 1.0.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) y [Problemas conocidos de la versión 1.0.1](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) para sus versiones o distribuciones instaladas.</span><span class="sxs-lookup"><span data-stu-id="7ed6a-284">If you have problems with the .NET Core 1.x installation on a supported Linux distribution/version, consult the [1.0.0 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.0-known-issues.md) and [1.0.1 Known Issues](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0.1-known-issues.md) topics for your installed distributions/versions.</span></span>

