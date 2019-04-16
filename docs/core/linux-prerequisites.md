---
title: Requisitos previos para .NET Core en Linux
description: Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 29256259c66b909ad65691230bd652f38583184e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59084918"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="3afc6-103">Requisitos previos para .NET Core en Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="3afc6-104">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux.</span><span class="sxs-lookup"><span data-stu-id="3afc6-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="3afc6-105">Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:</span><span class="sxs-lookup"><span data-stu-id="3afc6-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="3afc6-106">Línea de comandos con su editor favorito</span><span class="sxs-lookup"><span data-stu-id="3afc6-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="3afc6-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="3afc6-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="3afc6-108">El paquete del SDK de .NET Core no es necesario para entornos o servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="3afc6-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="3afc6-109">Solo se necesita el paquete del entorno de ejecución .NET Core para las aplicaciones que se implementan en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="3afc6-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="3afc6-110">El entorno de ejecución .NET Core se implementa con aplicaciones como parte de una implementación independiente, aunque se debe implementar para aplicaciones implementadas por separado dependientes del marco.</span><span class="sxs-lookup"><span data-stu-id="3afc6-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="3afc6-111">Para obtener más información sobre las implementaciones independientes y dependientes del marco, vea [Implementación de aplicaciones .NET Core](./deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="3afc6-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="3afc6-112">Consulte también [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones independientes de Linux) para obtener instrucciones específicas.</span><span class="sxs-lookup"><span data-stu-id="3afc6-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="3afc6-113">Versiones de Linux compatibles</span><span class="sxs-lookup"><span data-stu-id="3afc6-113">Supported Linux versions</span></span>

# [<a name="net-core-2x"></a><span data-ttu-id="3afc6-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="3afc6-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="3afc6-115">.NET Core 2.x considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3afc6-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="3afc6-116">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="3afc6-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="3afc6-117">Para los vínculos de descarga y más información, consulte [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Descargas de .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Descargas de .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="3afc6-117">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="3afc6-118">.NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="3afc6-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="3afc6-119">Red Hat Enterprise Linux 7.6 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-120">CentOS 7 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="3afc6-121">Oracle Linux 7 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="3afc6-122">Fedora 28, 27 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="3afc6-123">Debian 9 (64 bits, `arm32`), 8.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-124">Ubuntu 18.04 (64 bits, `arm32`), 16.04, 14.04 - 64-bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-125">Linux Mint 18, 17 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-126">openSUSE 42.3 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="3afc6-128">Alpine Linux 3.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="3afc6-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="3afc6-129">Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) y [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1 y .NET Core 2.2, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3afc6-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# [<a name="net-core-1x"></a><span data-ttu-id="3afc6-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="3afc6-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="3afc6-131">Para los vínculos de descarga y más información, consulte [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Descargas de .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Descargas de .NET Core 1.0).</span><span class="sxs-lookup"><span data-stu-id="3afc6-131">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="3afc6-132">NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="3afc6-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="3afc6-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="3afc6-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="3afc6-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="3afc6-134">CentOS 7</span></span>
* <span data-ttu-id="3afc6-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="3afc6-135">Oracle Linux 7</span></span>
* <span data-ttu-id="3afc6-136">Fedora 28 (.NET Core 1.1), 27</span><span class="sxs-lookup"><span data-stu-id="3afc6-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="3afc6-137">Debian 8.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3afc6-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="3afc6-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="3afc6-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="3afc6-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="3afc6-139">Linux Mint 17</span></span>
* <span data-ttu-id="3afc6-140">openSUSE 42.3 o versiones posteriores (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="3afc6-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="3afc6-141">Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3afc6-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# [<a name="net-core-30-preview-1"></a><span data-ttu-id="3afc6-142">.NET Core 3.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="3afc6-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="3afc6-143">.NET Core 3.0 (versión preliminar 1) considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="3afc6-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="3afc6-144">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="3afc6-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="3afc6-145">Para obtener vínculos de descarga y más información, vea [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) (Descargas de .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="3afc6-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="3afc6-146">.NET Core 3.0 (versión preliminar 1) se admite en las siguientes versiones o distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="3afc6-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="3afc6-147">SO</span><span class="sxs-lookup"><span data-stu-id="3afc6-147">OS</span></span>                            | <span data-ttu-id="3afc6-148">Versión</span><span class="sxs-lookup"><span data-stu-id="3afc6-148">Version</span></span>               | <span data-ttu-id="3afc6-149">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="3afc6-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="3afc6-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="3afc6-151">6</span><span class="sxs-lookup"><span data-stu-id="3afc6-151">6</span></span>                     | <span data-ttu-id="3afc6-152">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-152">x64</span></span>
<span data-ttu-id="3afc6-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="3afc6-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="3afc6-154">CentOS</span></span><br><span data-ttu-id="3afc6-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-155">Oracle Linux</span></span>  | <span data-ttu-id="3afc6-156">7</span><span class="sxs-lookup"><span data-stu-id="3afc6-156">7</span></span>                     | <span data-ttu-id="3afc6-157">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-157">x64</span></span>
<span data-ttu-id="3afc6-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="3afc6-158">Fedora</span></span>                        | <span data-ttu-id="3afc6-159">28</span><span class="sxs-lookup"><span data-stu-id="3afc6-159">28</span></span>                    | <span data-ttu-id="3afc6-160">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-160">x64</span></span>
<span data-ttu-id="3afc6-161">Debian</span><span class="sxs-lookup"><span data-stu-id="3afc6-161">Debian</span></span>                        | <span data-ttu-id="3afc6-162">9</span><span class="sxs-lookup"><span data-stu-id="3afc6-162">9</span></span>                     | <span data-ttu-id="3afc6-163">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="3afc6-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="3afc6-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="3afc6-164">Ubuntu</span></span>                        | <span data-ttu-id="3afc6-165">16.04+, 18.04+</span><span class="sxs-lookup"><span data-stu-id="3afc6-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="3afc6-166">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="3afc6-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="3afc6-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="3afc6-167">Linux Mint</span></span>                    | <span data-ttu-id="3afc6-168">18</span><span class="sxs-lookup"><span data-stu-id="3afc6-168">18</span></span>                    | <span data-ttu-id="3afc6-169">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-169">x64</span></span>
<span data-ttu-id="3afc6-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="3afc6-170">openSUSE</span></span>                      | <span data-ttu-id="3afc6-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="3afc6-171">42.3+</span></span>                 | <span data-ttu-id="3afc6-172">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-172">x64</span></span>
<span data-ttu-id="3afc6-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="3afc6-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="3afc6-174">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="3afc6-174">12 SP2+</span></span>               | <span data-ttu-id="3afc6-175">x64</span><span class="sxs-lookup"><span data-stu-id="3afc6-175">x64</span></span>
<span data-ttu-id="3afc6-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-176">Alpine Linux</span></span>                  | <span data-ttu-id="3afc6-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="3afc6-177">3.8+</span></span>                  | <span data-ttu-id="3afc6-178">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="3afc6-178">x64, ARM64</span></span>

<span data-ttu-id="3afc6-179">\* La compatibilidad con ARM32 y ARM64 empieza con Debian 9 y Ubuntu 16.04.</span><span class="sxs-lookup"><span data-stu-id="3afc6-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="3afc6-180">Las versiones anteriores de estas distribuciones no se admiten en chips ARM.</span><span class="sxs-lookup"><span data-stu-id="3afc6-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="3afc6-181">Vea [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 3.0, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="3afc6-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="3afc6-182">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="3afc6-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="3afc6-183">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="3afc6-183">Linux distribution dependencies</span></span>

<span data-ttu-id="3afc6-184">Los siguientes están diseñados a modo de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="3afc6-184">The following are intended to be examples.</span></span> <span data-ttu-id="3afc6-185">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="3afc6-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="3afc6-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="3afc6-186">Ubuntu</span></span>

<span data-ttu-id="3afc6-187">Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="3afc6-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="3afc6-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="3afc6-188">liblttng-ust0</span></span>
* <span data-ttu-id="3afc6-189">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-189">libcurl3 (for 14.x and 16.x)</span></span>
* <span data-ttu-id="3afc6-190">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-190">libcurl4 (for 18.x)</span></span>
* <span data-ttu-id="3afc6-191">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="3afc6-191">libssl1.0.0</span></span>
* <span data-ttu-id="3afc6-192">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="3afc6-192">libkrb5-3</span></span>
* <span data-ttu-id="3afc6-193">zlib1g</span><span class="sxs-lookup"><span data-stu-id="3afc6-193">zlib1g</span></span>
* <span data-ttu-id="3afc6-194">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-194">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="3afc6-195">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-195">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="3afc6-196">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-196">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="3afc6-197">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="3afc6-197">libicu60 (for 18.x)</span></span>

<span data-ttu-id="3afc6-198">Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="3afc6-198">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="3afc6-199">libunwind8</span><span class="sxs-lookup"><span data-stu-id="3afc6-199">libunwind8</span></span>
* <span data-ttu-id="3afc6-200">libuuid1</span><span class="sxs-lookup"><span data-stu-id="3afc6-200">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="3afc6-201">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="3afc6-201">CentOS and Fedora</span></span>

<span data-ttu-id="3afc6-202">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="3afc6-202">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="3afc6-203">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="3afc6-203">lttng-ust</span></span>
* <span data-ttu-id="3afc6-204">libcurl</span><span class="sxs-lookup"><span data-stu-id="3afc6-204">libcurl</span></span>
* <span data-ttu-id="3afc6-205">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="3afc6-205">openssl-libs</span></span>
* <span data-ttu-id="3afc6-206">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="3afc6-206">krb5-libs</span></span>
* <span data-ttu-id="3afc6-207">libicu</span><span class="sxs-lookup"><span data-stu-id="3afc6-207">libicu</span></span>
* <span data-ttu-id="3afc6-208">zlib</span><span class="sxs-lookup"><span data-stu-id="3afc6-208">zlib</span></span>

<span data-ttu-id="3afc6-209">Usuarios de Fedora: si la versión de openssl >= 1.1, es necesario instalar compat-openssl10.</span><span class="sxs-lookup"><span data-stu-id="3afc6-209">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="3afc6-210">Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="3afc6-210">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="3afc6-211">libunwind</span><span class="sxs-lookup"><span data-stu-id="3afc6-211">libunwind</span></span>
* <span data-ttu-id="3afc6-212">libuuid</span><span class="sxs-lookup"><span data-stu-id="3afc6-212">libuuid</span></span>

<span data-ttu-id="3afc6-213">Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).</span><span class="sxs-lookup"><span data-stu-id="3afc6-213">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="3afc6-214">Instalación de las dependencias de .NET Core con los instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="3afc6-214">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="3afc6-215">Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="3afc6-215">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="3afc6-216">Los instaladores nativos requieren acceso de administrador (sudo) para el servidor.</span><span class="sxs-lookup"><span data-stu-id="3afc6-216">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="3afc6-217">La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas.</span><span class="sxs-lookup"><span data-stu-id="3afc6-217">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="3afc6-218">Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="3afc6-218">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="3afc6-219">En Linux, existen dos opciones de paquete de instalador:</span><span class="sxs-lookup"><span data-stu-id="3afc6-219">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="3afc6-220">Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.</span><span class="sxs-lookup"><span data-stu-id="3afc6-220">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="3afc6-221">Usar los propios paquetes, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="3afc6-221">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="3afc6-222">Instalaciones de scripting con el script del instalador de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3afc6-222">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="3afc6-223">Los [scripts de dotnet-install](./tools/dotnet-install-script.md) se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de la CLI y del entorno de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="3afc6-223">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="3afc6-224">Puede descargar el script de [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span><span class="sxs-lookup"><span data-stu-id="3afc6-224">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="3afc6-225">El valor predeterminado del script es instalar la versión más reciente "LTS", que actualmente es .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="3afc6-225">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="3afc6-226">Para instalar .NET Core 2.1, ejecute el script con el modificador siguiente:</span><span class="sxs-lookup"><span data-stu-id="3afc6-226">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="3afc6-227">El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas.</span><span class="sxs-lookup"><span data-stu-id="3afc6-227">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="3afc6-228">Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.</span><span class="sxs-lookup"><span data-stu-id="3afc6-228">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="3afc6-229">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="3afc6-229">Troubleshoot</span></span>

<span data-ttu-id="3afc6-230">Si tiene problemas con una instalación de .NET Core en una versión o distribución de Linux compatible, vea los siguientes temas para sus versiones o distribuciones instaladas:</span><span class="sxs-lookup"><span data-stu-id="3afc6-230">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* [<span data-ttu-id="3afc6-231">.NET Core 3.0 known issues (Problemas conocidos de .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="3afc6-231">.NET Core 3.0 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/3.0)
* [<span data-ttu-id="3afc6-232">.NET Core 2.2 known issues (Problemas conocidos de .NET Core 2.2)</span><span class="sxs-lookup"><span data-stu-id="3afc6-232">.NET Core 2.2 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.2)
* [<span data-ttu-id="3afc6-233">.NET Core 2.1 known issues (Problemas conocidos de .NET Core 2.1)</span><span class="sxs-lookup"><span data-stu-id="3afc6-233">.NET Core 2.1 known issues</span></span>](https://github.com/dotnet/core/tree/master/release-notes/2.1)
* [<span data-ttu-id="3afc6-234">.NET Core 1.1 known issues (Problemas conocidos de .NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="3afc6-234">.NET Core 1.1 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.1)
* [<span data-ttu-id="3afc6-235">.NET Core 1.0 known issues (Problemas conocidos de .NET Core 1.0)</span><span class="sxs-lookup"><span data-stu-id="3afc6-235">.NET Core 1.0 known issues</span></span>](https://github.com/dotnet/core/blob/master/release-notes/1.0)
