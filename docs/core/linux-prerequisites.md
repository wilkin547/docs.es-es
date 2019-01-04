---
title: Requisitos previos para .NET Core en Linux
description: Versiones de Linux admitidas y dependencias de .NET Core para desarrollar, implementar y ejecutar aplicaciones .NET Core en máquinas Linux.
author: thraka
ms.author: adegeo
ms.date: 12/14/2018
ms.openlocfilehash: 7a2b0b3af97500ab0988e5de7a44713a8c05ccb9
ms.sourcegitcommit: 3d0c29b878f00caec288dfecb3a5c959de5aa629
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/20/2018
ms.locfileid: "53656055"
---
# <a name="prerequisites-for-net-core-on-linux"></a><span data-ttu-id="e6f5a-103">Requisitos previos para .NET Core en Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-103">Prerequisites for .NET Core on Linux</span></span>

<span data-ttu-id="e6f5a-104">En este artículo se muestran las dependencias necesarias para desarrollar aplicaciones de .NET Core en Linux.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-104">This article shows the dependencies needed to develop .NET Core applications on Linux.</span></span> <span data-ttu-id="e6f5a-105">Las versiones o distribuciones de Linux y las dependencias admitidas que aparecen a continuación se aplican a las dos formas de desarrollo de aplicaciones de .NET Core en Linux:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-105">The supported Linux distributions/versions, and dependencies that follow apply to the two ways of developing .NET Core apps on Linux:</span></span>

* [<span data-ttu-id="e6f5a-106">Línea de comandos con su editor favorito</span><span class="sxs-lookup"><span data-stu-id="e6f5a-106">Command-line with your favorite editor</span></span>](tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="e6f5a-107">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="e6f5a-107">Visual Studio Code</span></span>](https://code.visualstudio.com/)

> [!NOTE]
> <span data-ttu-id="e6f5a-108">El paquete del SDK de .NET Core no es necesario para entornos o servidores de producción.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-108">The .NET Core SDK package is not required for production servers/environments.</span></span> <span data-ttu-id="e6f5a-109">Solo se necesita el paquete del entorno de ejecución .NET Core para las aplicaciones que se implementan en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-109">Only the .NET Core runtime package is needed for apps deployed to production environments.</span></span> <span data-ttu-id="e6f5a-110">El entorno de ejecución .NET Core se implementa con aplicaciones como parte de una implementación independiente, aunque se debe implementar para aplicaciones implementadas por separado dependientes del marco.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-110">The .NET Core runtime is deployed with apps as part of a self-contained deployment, however, it must be deployed for Framework-dependent deployed apps separately.</span></span> <span data-ttu-id="e6f5a-111">Para obtener más información sobre las implementaciones independientes y dependientes del marco, vea [Implementación de aplicaciones .NET Core](./deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-111">For more information about framework-dependent and self-contained deployment types, see [.NET Core application deployment](./deploying/index.md).</span></span> <span data-ttu-id="e6f5a-112">Consulte también [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones independientes de Linux) para obtener instrucciones específicas.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-112">Also see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) for specific guidelines.</span></span>

## <a name="supported-linux-versions"></a><span data-ttu-id="e6f5a-113">Versiones de Linux compatibles</span><span class="sxs-lookup"><span data-stu-id="e6f5a-113">Supported Linux versions</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="e6f5a-114">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="e6f5a-114">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="e6f5a-115">.NET Core 2.x considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-115">.NET Core 2.x treats Linux as a single operating system.</span></span> <span data-ttu-id="e6f5a-116">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-116">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="e6f5a-117">Para los vínculos de descarga y más información, consulte [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) (Descargas de .NET Core 2.2) o [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1) (Descargas de .NET Core 2.1).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-117">For download links and more information, see [.NET Core 2.2 downloads](https://www.microsoft.com/net/download/dotnet-core/2.2) or [.NET Core 2.1 downloads](https://www.microsoft.com/net/download/dotnet-core/2.1).</span></span>

<span data-ttu-id="e6f5a-118">.NET Core 2.x se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-118">.NET Core 2.x is supported on the following Linux distributions/versions:</span></span>

* <span data-ttu-id="e6f5a-119">Red Hat Enterprise Linux 7.6 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-119">Red Hat Enterprise Linux 7, 6 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-120">CentOS 7 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-120">CentOS 7  - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="e6f5a-121">Oracle Linux 7 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-121">Oracle Linux 7 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="e6f5a-122">Fedora 28, 27 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-122">Fedora 28, 27 - 64-bit (`x86_64` or `amd64`)</span></span> 
* <span data-ttu-id="e6f5a-123">Debian 9 (64 bits, `arm32`), 8.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-123">Debian 9 (64-bit, `arm32`), 8.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-124">Ubuntu 18.04 (64 bits, `arm32`), 16.04, 14.04 - 64-bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-124">Ubuntu 18.04 (64-bit, `arm32`), 16.04, 14.04 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-125">Linux Mint 18, 17 - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-125">Linux Mint 18, 17 - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-126">openSUSE 42.3 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-126">openSUSE 42.3 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-127">SUSE Enterprise Linux (SLES) 12 Service Pack 2 or later - 64-bit (`x86_64` or `amd64`)</span></span>
* <span data-ttu-id="e6f5a-128">Alpine Linux 3.7 o versiones posteriores - 64 bits (`x86_64` o `amd64`)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-128">Alpine Linux 3.7 or later versions - 64-bit (`x86_64` or `amd64`)</span></span>

<span data-ttu-id="e6f5a-129">Vea [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) (.NET Core 2.1: versiones de SO compatibles) y [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) (.NET Core 2.2: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 2.1 y .NET Core 2.2, versiones del sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-129">See [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) and [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) for the complete list of .NET Core 2.1 and .NET Core 2.2 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="e6f5a-130">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="e6f5a-130">.NET Core 1.x</span></span>](#tab/netcore1x)

<span data-ttu-id="e6f5a-131">Para los vínculos de descarga y más información, consulte [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) (Descargas de .NET Core 1.1) o [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0) (Descargas de .NET Core 1.0).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-131">For download links and more information, see [.NET Core 1.1 downloads](https://www.microsoft.com/net/download/dotnet-core/1.1) or [.NET Core 1.0 downloads](https://www.microsoft.com/net/download/dotnet-core/1.0).</span></span>

<span data-ttu-id="e6f5a-132">NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux de 64 bits (`x86_64` o `amd64`):</span><span class="sxs-lookup"><span data-stu-id="e6f5a-132">.NET Core 1.x is supported on the following Linux 64-bit (`x86_64` or `amd64`) distributions/versions:</span></span>

* <span data-ttu-id="e6f5a-133">Red Hat Enterprise Linux 7</span><span class="sxs-lookup"><span data-stu-id="e6f5a-133">Red Hat Enterprise Linux 7</span></span>
* <span data-ttu-id="e6f5a-134">CentOS 7</span><span class="sxs-lookup"><span data-stu-id="e6f5a-134">CentOS 7</span></span>
* <span data-ttu-id="e6f5a-135">Oracle Linux 7</span><span class="sxs-lookup"><span data-stu-id="e6f5a-135">Oracle Linux 7</span></span>
* <span data-ttu-id="e6f5a-136">Fedora 28 (.NET Core 1.1), 27</span><span class="sxs-lookup"><span data-stu-id="e6f5a-136">Fedora 28 (.NET Core 1.1), 27</span></span>
* <span data-ttu-id="e6f5a-137">Debian 8.2 o versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e6f5a-137">Debian 8.2 or later versions</span></span>
* <span data-ttu-id="e6f5a-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span><span class="sxs-lookup"><span data-stu-id="e6f5a-138">Ubuntu 18.04 (.NET Core 1.1), 16.04, 14.04</span></span>
* <span data-ttu-id="e6f5a-139">Linux Mint 17</span><span class="sxs-lookup"><span data-stu-id="e6f5a-139">Linux Mint 17</span></span>
* <span data-ttu-id="e6f5a-140">openSUSE 42.3 o versiones posteriores (.NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-140">openSUSE 42.3 or later versions (.NET Core 1.1)</span></span>

<span data-ttu-id="e6f5a-141">Vea [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) (.NET Core 1.x: versiones de SO compatibles) para obtener una lista completa de sistemas operativos compatibles con .NET Core 1.x, fuera de las versiones de sistema operativo compatibles y los vínculos de directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-141">See [.NET Core 1.x Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md) for the complete list of .NET Core 1.x supported operating systems, out of support OS versions, and lifecycle policy links.</span></span>

# <a name="net-core-30-preview-1tabnetcore30"></a>[<span data-ttu-id="e6f5a-142">.NET Core 3.0 (versión preliminar 1)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-142">.NET Core 3.0 Preview 1</span></span>](#tab/netcore30)

<span data-ttu-id="e6f5a-143">.NET Core 3.0 (versión preliminar 1) considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-143">.NET Core 3.0 Preview 1 treats Linux as a single operating system.</span></span> <span data-ttu-id="e6f5a-144">Hay una compilación de Linux única (según la arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-144">There is a single Linux build (per chip architecture) for supported Linux distributions.</span></span> 

<span data-ttu-id="e6f5a-145">Para obtener vínculos de descarga y más información, vea [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0) (Descargas de .NET Core 3.0).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-145">For download links and more information, see [.NET Core 3.0 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.0).</span></span>

<span data-ttu-id="e6f5a-146">.NET Core 3.0 (versión preliminar 1) se admite en las siguientes versiones o distribuciones de Linux.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-146">.NET Core 3.0 Preview 1 is supported on the following Linux distributions/versions.</span></span> 

<span data-ttu-id="e6f5a-147">SO</span><span class="sxs-lookup"><span data-stu-id="e6f5a-147">OS</span></span>                            | <span data-ttu-id="e6f5a-148">Versión</span><span class="sxs-lookup"><span data-stu-id="e6f5a-148">Version</span></span>               | <span data-ttu-id="e6f5a-149">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="e6f5a-149">Architectures</span></span>  
------------------------------|-----------------------|----------------
<span data-ttu-id="e6f5a-150">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-150">Red Hat Enterprise Linux</span></span>      | <span data-ttu-id="e6f5a-151">6</span><span class="sxs-lookup"><span data-stu-id="e6f5a-151">6</span></span>                     | <span data-ttu-id="e6f5a-152">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-152">x64</span></span>
<span data-ttu-id="e6f5a-153">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-153">Red Hat Enterprise Linux</span></span><br><span data-ttu-id="e6f5a-154">CentOS</span><span class="sxs-lookup"><span data-stu-id="e6f5a-154">CentOS</span></span><br><span data-ttu-id="e6f5a-155">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-155">Oracle Linux</span></span>  | <span data-ttu-id="e6f5a-156">7</span><span class="sxs-lookup"><span data-stu-id="e6f5a-156">7</span></span>                     | <span data-ttu-id="e6f5a-157">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-157">x64</span></span>
<span data-ttu-id="e6f5a-158">Fedora</span><span class="sxs-lookup"><span data-stu-id="e6f5a-158">Fedora</span></span>                        | <span data-ttu-id="e6f5a-159">28</span><span class="sxs-lookup"><span data-stu-id="e6f5a-159">28</span></span>                    | <span data-ttu-id="e6f5a-160">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-160">x64</span></span>
<span data-ttu-id="e6f5a-161">Debian</span><span class="sxs-lookup"><span data-stu-id="e6f5a-161">Debian</span></span>                        | <span data-ttu-id="e6f5a-162">9</span><span class="sxs-lookup"><span data-stu-id="e6f5a-162">9</span></span>                     | <span data-ttu-id="e6f5a-163">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="e6f5a-163">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="e6f5a-164">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e6f5a-164">Ubuntu</span></span>                        | <span data-ttu-id="e6f5a-165">16.04+, 18.04+</span><span class="sxs-lookup"><span data-stu-id="e6f5a-165">16.04+, 18.04+</span></span>        | <span data-ttu-id="e6f5a-166">x64, ARM32\*, ARM64\*</span><span class="sxs-lookup"><span data-stu-id="e6f5a-166">x64, ARM32\*, ARM64\*</span></span>
<span data-ttu-id="e6f5a-167">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="e6f5a-167">Linux Mint</span></span>                    | <span data-ttu-id="e6f5a-168">18</span><span class="sxs-lookup"><span data-stu-id="e6f5a-168">18</span></span>                    | <span data-ttu-id="e6f5a-169">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-169">x64</span></span>
<span data-ttu-id="e6f5a-170">openSUSE</span><span class="sxs-lookup"><span data-stu-id="e6f5a-170">openSUSE</span></span>                      | <span data-ttu-id="e6f5a-171">42.3+</span><span class="sxs-lookup"><span data-stu-id="e6f5a-171">42.3+</span></span>                 | <span data-ttu-id="e6f5a-172">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-172">x64</span></span>
<span data-ttu-id="e6f5a-173">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-173">SUSE Enterprise Linux (SLES)</span></span>  | <span data-ttu-id="e6f5a-174">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="e6f5a-174">12 SP2+</span></span>               | <span data-ttu-id="e6f5a-175">x64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-175">x64</span></span>
<span data-ttu-id="e6f5a-176">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-176">Alpine Linux</span></span>                  | <span data-ttu-id="e6f5a-177">3.8+</span><span class="sxs-lookup"><span data-stu-id="e6f5a-177">3.8+</span></span>                  | <span data-ttu-id="e6f5a-178">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="e6f5a-178">x64, ARM64</span></span>

<span data-ttu-id="e6f5a-179">\* La compatibilidad con ARM32 y ARM64 empieza con Debian 9 y Ubuntu 16.04.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-179">\* ARM32 and ARM64 support starts with Debian 9 and Ubuntu 16.04.</span></span> <span data-ttu-id="e6f5a-180">Las versiones anteriores de estas distribuciones no se admiten en chips ARM.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-180">Earlier versions of those distros are not supported on ARM chips.</span></span>

<span data-ttu-id="e6f5a-181">Vea [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) (.NET Core 3.0: versiones de SO compatibles) para obtener la lista completa de sistemas operativos, distribuciones y versiones compatibles con .NET Core 3.0, las versiones de sistema operativo no compatibles y vínculos de la directiva de ciclo de vida.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-181">See [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) for the complete list of .NET Core 3.0 supported operating systems, distributions and versions, out of support OS versions, and lifecycle policy links.</span></span>

<span data-ttu-id="e6f5a-182">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-182">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>



---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="e6f5a-183">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="e6f5a-183">Linux distribution dependencies</span></span>

<span data-ttu-id="e6f5a-184">Los siguientes están diseñados a modo de ejemplos.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-184">The following are intended to be examples.</span></span> <span data-ttu-id="e6f5a-185">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-185">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="e6f5a-186">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="e6f5a-186">Ubuntu</span></span>

<span data-ttu-id="e6f5a-187">Las distribuciones de Ubuntu necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-187">Ubuntu distributions require the following libraries installed:</span></span>

* <span data-ttu-id="e6f5a-188">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="e6f5a-188">liblttng-ust0</span></span>
* <span data-ttu-id="e6f5a-189">libcurl3</span><span class="sxs-lookup"><span data-stu-id="e6f5a-189">libcurl3</span></span>
* <span data-ttu-id="e6f5a-190">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="e6f5a-190">libssl1.0.0</span></span>
* <span data-ttu-id="e6f5a-191">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="e6f5a-191">libkrb5-3</span></span>
* <span data-ttu-id="e6f5a-192">zlib1g</span><span class="sxs-lookup"><span data-stu-id="e6f5a-192">zlib1g</span></span>
* <span data-ttu-id="e6f5a-193">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-193">libicu52 (for 14.x)</span></span>
* <span data-ttu-id="e6f5a-194">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-194">libicu55 (for 16.x)</span></span>
* <span data-ttu-id="e6f5a-195">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-195">libicu57 (for 17.x)</span></span>
* <span data-ttu-id="e6f5a-196">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-196">libicu60 (for 18.x)</span></span>

<span data-ttu-id="e6f5a-197">Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-197">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="e6f5a-198">libunwind8</span><span class="sxs-lookup"><span data-stu-id="e6f5a-198">libunwind8</span></span>
* <span data-ttu-id="e6f5a-199">libuuid1</span><span class="sxs-lookup"><span data-stu-id="e6f5a-199">libuuid1</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="e6f5a-200">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="e6f5a-200">CentOS and Fedora</span></span>

<span data-ttu-id="e6f5a-201">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-201">CentOS distributions require the following libraries installed:</span></span>

* <span data-ttu-id="e6f5a-202">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="e6f5a-202">lttng-ust</span></span>
* <span data-ttu-id="e6f5a-203">libcurl</span><span class="sxs-lookup"><span data-stu-id="e6f5a-203">libcurl</span></span>
* <span data-ttu-id="e6f5a-204">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="e6f5a-204">openssl-libs</span></span>
* <span data-ttu-id="e6f5a-205">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="e6f5a-205">krb5-libs</span></span>
* <span data-ttu-id="e6f5a-206">libicu</span><span class="sxs-lookup"><span data-stu-id="e6f5a-206">libicu</span></span>
* <span data-ttu-id="e6f5a-207">zlib</span><span class="sxs-lookup"><span data-stu-id="e6f5a-207">zlib</span></span>

<span data-ttu-id="e6f5a-208">Usuarios de Fedora: si la versión de openssl >= 1.1, es necesario instalar compat-openssl10.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-208">Fedora users: If your openssl's version >= 1.1, you'll need to install compat-openssl10.</span></span>

<span data-ttu-id="e6f5a-209">Para versiones anteriores a .NET Core 2.1, también se requieren las siguientes dependencias:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-209">For versions earlier than .NET Core 2.1, following dependencies are also required:</span></span>

* <span data-ttu-id="e6f5a-210">libunwind</span><span class="sxs-lookup"><span data-stu-id="e6f5a-210">libunwind</span></span>
* <span data-ttu-id="e6f5a-211">libuuid</span><span class="sxs-lookup"><span data-stu-id="e6f5a-211">libuuid</span></span>

<span data-ttu-id="e6f5a-212">Para más información acerca de las dependencias, consulte [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md) (Aplicaciones Linux autónomas).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-212">For more information about the dependencies, see [Self-contained Linux applications](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

## <a name="installing-net-core-dependencies-with-the-native-installers"></a><span data-ttu-id="e6f5a-213">Instalación de las dependencias de .NET Core con los instaladores nativos</span><span class="sxs-lookup"><span data-stu-id="e6f5a-213">Installing .NET Core dependencies with the native installers</span></span>

<span data-ttu-id="e6f5a-214">Los instaladores nativos de .NET Core están disponibles para las versiones o distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-214">.NET Core native installers are available for supported Linux distributions/versions.</span></span> <span data-ttu-id="e6f5a-215">Los instaladores nativos requieren acceso de administrador (sudo) para el servidor.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-215">The native installers require admin (sudo) access to the server.</span></span> <span data-ttu-id="e6f5a-216">La ventaja de usar un instalador nativo es que todas las dependencias nativas de .NET Core están instaladas.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-216">The advantage of using a native installer is that all of the .NET Core native dependencies are installed.</span></span> <span data-ttu-id="e6f5a-217">Los instaladores nativos también instalan el SDK de .NET Core en todo el sistema.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-217">Native installers also install the .NET Core SDK system-wide.</span></span>

<span data-ttu-id="e6f5a-218">En Linux, existen dos opciones de paquete de instalador:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-218">On Linux, there are two installer package choices:</span></span>

* <span data-ttu-id="e6f5a-219">Use un administrador de paquetes basado en fuentes, como apt-get para Ubuntu o yum para CentOS o RHEL.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-219">Using a feed-based package manager, such as apt-get for Ubuntu, or yum for CentOS/RHEL.</span></span>
* <span data-ttu-id="e6f5a-220">Usar los propios paquetes, DEB o RPM.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-220">Using the packages themselves, DEB or RPM.</span></span>

### <a name="scripting-installs-with-the-net-core-installer-script"></a><span data-ttu-id="e6f5a-221">Instalaciones de scripting con el script del instalador de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e6f5a-221">Scripting Installs with the .NET Core installer script</span></span>

<span data-ttu-id="e6f5a-222">Los [scripts de dotnet-install](./tools/dotnet-install-script.md) se usan para realizar una instalación sin derechos administrativos de la cadena de herramientas de la CLI y del entorno de ejecución compartido.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-222">The [dotnet-install scripts](./tools/dotnet-install-script.md) are used to perform a non-admin install of the CLI toolchain and the shared runtime.</span></span> <span data-ttu-id="e6f5a-223">Puede descargar el script de [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span><span class="sxs-lookup"><span data-stu-id="e6f5a-223">You can download the script from [https://dot.net/v1/dotnet-install.sh](https://dot.net/v1/dotnet-install.sh).</span></span>

<span data-ttu-id="e6f5a-224">El valor predeterminado del script es instalar la versión más reciente "LTS", que actualmente es .NET Core 1.1.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-224">The script defaults to installing the latest "LTS" version, which is currently .NET Core 1.1.</span></span> <span data-ttu-id="e6f5a-225">Para instalar .NET Core 2.1, ejecute el script con el modificador siguiente:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-225">To install .NET Core 2.1, run the script with the following switch:</span></span>

```console
./dotnet-install.sh -c Current
```

<span data-ttu-id="e6f5a-226">El script de Bash del instalador se usa en escenarios de automatización y en instalaciones no administrativas.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-226">The installer bash script is used in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="e6f5a-227">Este script también lee modificadores de PowerShell, por lo que pueden usarse con el script en sistemas Linux y OS X.</span><span class="sxs-lookup"><span data-stu-id="e6f5a-227">This script also reads PowerShell switches, so they can be used with the script on Linux/OS X systems.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="e6f5a-228">Solucionar problemas</span><span class="sxs-lookup"><span data-stu-id="e6f5a-228">Troubleshoot</span></span>

<span data-ttu-id="e6f5a-229">Si tiene problemas con una instalación de .NET Core en una versión o distribución de Linux compatible, vea los siguientes temas para sus versiones o distribuciones instaladas:</span><span class="sxs-lookup"><span data-stu-id="e6f5a-229">If you have problems with a .NET Core installation on a supported Linux distribution/version, consult the following topics for your installed distributions/versions:</span></span>

* <span data-ttu-id="e6f5a-230">[.NET Core 3.0 known issues](https://github.com/dotnet/core/tree/master/release-notes/3.0) (Problemas conocidos de .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-230">[.NET Core 3.0 known issues](https://github.com/dotnet/core/tree/master/release-notes/3.0)</span></span>
* <span data-ttu-id="e6f5a-231">[.NET Core 2.2 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.2) (Problemas conocidos de .NET Core 2.2)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-231">[.NET Core 2.2 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.2)</span></span>
* <span data-ttu-id="e6f5a-232">[.NET Core 2.1 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1) (Problemas conocidos de .NET Core 2.1)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-232">[.NET Core 2.1 known issues](https://github.com/dotnet/core/tree/master/release-notes/2.1)</span></span>
* <span data-ttu-id="e6f5a-233">[.NET Core 1.1 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.1) (Problemas conocidos de .NET Core 1.1)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-233">[.NET Core 1.1 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.1)</span></span>
* <span data-ttu-id="e6f5a-234">[.NET Core 1.0 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0) (Problemas conocidos de .NET Core 1.0)</span><span class="sxs-lookup"><span data-stu-id="e6f5a-234">[.NET Core 1.0 known issues](https://github.com/dotnet/core/blob/master/release-notes/1.0)</span></span>
