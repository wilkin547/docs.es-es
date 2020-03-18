---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78157820"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="617a5-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="617a5-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="617a5-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="617a5-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="617a5-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="617a5-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="617a5-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="617a5-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="617a5-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="617a5-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-109">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-109">OS</span></span>                            | <span data-ttu-id="617a5-110">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-110">Version</span></span>                        | <span data-ttu-id="617a5-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="617a5-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="617a5-112">Windows Client</span></span>                | <span data-ttu-id="617a5-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="617a5-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="617a5-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-114">x64, x86</span></span>        |
| <span data-ttu-id="617a5-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="617a5-115">Windows 10 Client</span></span>             | <span data-ttu-id="617a5-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-116">Version 1607+</span></span>                  | <span data-ttu-id="617a5-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-117">x64, x86</span></span>        |
| <span data-ttu-id="617a5-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="617a5-118">Windows Server</span></span>                | <span data-ttu-id="617a5-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-119">2012 R2+</span></span>                       | <span data-ttu-id="617a5-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-120">x64, x86</span></span>        |
| <span data-ttu-id="617a5-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="617a5-121">Nano Server</span></span>                   | <span data-ttu-id="617a5-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-122">Version 1803+</span></span>                  | <span data-ttu-id="617a5-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-123">x64, ARM32</span></span>      |

<span data-ttu-id="617a5-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="617a5-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="617a5-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="617a5-126">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="617a5-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-127">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-128">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-128">OS</span></span>                            | <span data-ttu-id="617a5-129">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-129">Version</span></span>                        | <span data-ttu-id="617a5-130">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="617a5-131">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="617a5-131">Windows Client</span></span>                | <span data-ttu-id="617a5-132">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="617a5-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="617a5-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-133">x64, x86</span></span>        |
| <span data-ttu-id="617a5-134">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="617a5-134">Windows 10 Client</span></span>             | <span data-ttu-id="617a5-135">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-135">Version 1607+</span></span>                  | <span data-ttu-id="617a5-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-136">x64, x86</span></span>        |
| <span data-ttu-id="617a5-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="617a5-137">Windows Server</span></span>                | <span data-ttu-id="617a5-138">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-138">2012 R2+</span></span>                       | <span data-ttu-id="617a5-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-139">x64, x86</span></span>        |
| <span data-ttu-id="617a5-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="617a5-140">Nano Server</span></span>                   | <span data-ttu-id="617a5-141">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-141">Version 1803+</span></span>                  | <span data-ttu-id="617a5-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-142">x64, ARM32</span></span>      |

<span data-ttu-id="617a5-143">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="617a5-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="617a5-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="617a5-145">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="617a5-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-146">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-147">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-147">OS</span></span>                            | <span data-ttu-id="617a5-148">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-148">Version</span></span>                        | <span data-ttu-id="617a5-149">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="617a5-150">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="617a5-150">Windows Client</span></span>                | <span data-ttu-id="617a5-151">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="617a5-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="617a5-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-152">x64, x86</span></span>        |
| <span data-ttu-id="617a5-153">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="617a5-153">Windows 10 Client</span></span>             | <span data-ttu-id="617a5-154">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-154">Version 1607+</span></span>                  | <span data-ttu-id="617a5-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-155">x64, x86</span></span>        |
| <span data-ttu-id="617a5-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="617a5-156">Windows Server</span></span>                | <span data-ttu-id="617a5-157">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="617a5-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-158">x64, x86</span></span>        |
| <span data-ttu-id="617a5-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="617a5-159">Nano Server</span></span>                   | <span data-ttu-id="617a5-160">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-160">Version 1803+</span></span>                   | <span data-ttu-id="617a5-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-161">x64, ARM32</span></span>      |

<span data-ttu-id="617a5-162">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="617a5-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="617a5-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="617a5-164">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="617a5-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-165">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-166">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-166">OS</span></span>                            | <span data-ttu-id="617a5-167">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-167">Version</span></span>                        | <span data-ttu-id="617a5-168">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="617a5-169">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="617a5-169">Windows Client</span></span>                | <span data-ttu-id="617a5-170">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="617a5-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="617a5-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-171">x64, x86</span></span>        |
| <span data-ttu-id="617a5-172">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="617a5-172">Windows 10 Client</span></span>             | <span data-ttu-id="617a5-173">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-173">Version 1607+</span></span>                  | <span data-ttu-id="617a5-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-174">x64, x86</span></span>        |
| <span data-ttu-id="617a5-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="617a5-175">Windows Server</span></span>                | <span data-ttu-id="617a5-176">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="617a5-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="617a5-177">x64, x86</span></span>        |
| <span data-ttu-id="617a5-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="617a5-178">Nano Server</span></span>                   | <span data-ttu-id="617a5-179">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-179">Version 1803+</span></span>                  | <span data-ttu-id="617a5-180">x64,</span><span class="sxs-lookup"><span data-stu-id="617a5-180">x64,</span></span>            |

<span data-ttu-id="617a5-181">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="617a5-182">Windows 7, Vista, 8.1, Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="617a5-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="617a5-183">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="617a5-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="617a5-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="617a5-184">Windows 7 SP1</span></span>
- <span data-ttu-id="617a5-185">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="617a5-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="617a5-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="617a5-186">Windows 8.1</span></span>
- <span data-ttu-id="617a5-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="617a5-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="617a5-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="617a5-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="617a5-189">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="617a5-189">Install the following:</span></span>

- <span data-ttu-id="617a5-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="617a5-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="617a5-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="617a5-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="617a5-192">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="617a5-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="617a5-193">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="617a5-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="617a5-194">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="617a5-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="617a5-195">\- o -</span><span class="sxs-lookup"><span data-stu-id="617a5-195">\- or -</span></span>
>
> <span data-ttu-id="617a5-196">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="617a5-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="617a5-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="617a5-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="617a5-198">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="617a5-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="617a5-199">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="617a5-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="617a5-200">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="617a5-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-201">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-202">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-202">OS</span></span>                             | <span data-ttu-id="617a5-203">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-203">Version</span></span>               | <span data-ttu-id="617a5-204">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="617a5-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="617a5-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="617a5-206">6, 7, 8</span></span>               | <span data-ttu-id="617a5-207">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-207">x64</span></span> |
| <span data-ttu-id="617a5-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="617a5-208">CentOS</span></span>                         | <span data-ttu-id="617a5-209">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-209">7+</span></span>                    | <span data-ttu-id="617a5-210">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-210">x64</span></span> |
| <span data-ttu-id="617a5-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-211">Oracle Linux</span></span>                   | <span data-ttu-id="617a5-212">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-212">7+</span></span>                    | <span data-ttu-id="617a5-213">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-213">x64</span></span> |
| <span data-ttu-id="617a5-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="617a5-214">Fedora</span></span>                         | <span data-ttu-id="617a5-215">29+</span><span class="sxs-lookup"><span data-stu-id="617a5-215">29+</span></span>                   | <span data-ttu-id="617a5-216">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-216">x64</span></span> |
| <span data-ttu-id="617a5-217">Debian</span><span class="sxs-lookup"><span data-stu-id="617a5-217">Debian</span></span>                         | <span data-ttu-id="617a5-218">9+</span><span class="sxs-lookup"><span data-stu-id="617a5-218">9+</span></span>                    | <span data-ttu-id="617a5-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="617a5-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="617a5-220">Ubuntu</span></span>                         | <span data-ttu-id="617a5-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="617a5-221">16.04+</span></span>                | <span data-ttu-id="617a5-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="617a5-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="617a5-223">Linux Mint</span></span>                     | <span data-ttu-id="617a5-224">18+</span><span class="sxs-lookup"><span data-stu-id="617a5-224">18+</span></span>                   | <span data-ttu-id="617a5-225">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-225">x64</span></span> |
| <span data-ttu-id="617a5-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="617a5-226">openSUSE</span></span>                       | <span data-ttu-id="617a5-227">15+</span><span class="sxs-lookup"><span data-stu-id="617a5-227">15+</span></span>                   | <span data-ttu-id="617a5-228">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-228">x64</span></span> |
| <span data-ttu-id="617a5-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="617a5-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="617a5-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="617a5-230">12 SP2+</span></span>               | <span data-ttu-id="617a5-231">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-231">x64</span></span> |
| <span data-ttu-id="617a5-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-232">Alpine Linux</span></span>                   | <span data-ttu-id="617a5-233">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-233">3.10+</span></span>                 | <span data-ttu-id="617a5-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-234">x64, ARM64</span></span> |

<span data-ttu-id="617a5-235">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="617a5-236">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="617a5-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="617a5-237">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="617a5-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="617a5-238">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="617a5-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="617a5-239">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="617a5-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="617a5-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="617a5-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="617a5-241">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="617a5-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="617a5-242">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="617a5-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="617a5-243">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="617a5-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-244">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-245">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-245">OS</span></span>                             | <span data-ttu-id="617a5-246">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-246">Version</span></span>               | <span data-ttu-id="617a5-247">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="617a5-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="617a5-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="617a5-249">6, 7, 8</span></span>               | <span data-ttu-id="617a5-250">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-250">x64</span></span> |
| <span data-ttu-id="617a5-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="617a5-251">CentOS</span></span>                         | <span data-ttu-id="617a5-252">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-252">7+</span></span>                    | <span data-ttu-id="617a5-253">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-253">x64</span></span> |
| <span data-ttu-id="617a5-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-254">Oracle Linux</span></span>                   | <span data-ttu-id="617a5-255">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-255">7+</span></span>                    | <span data-ttu-id="617a5-256">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-256">x64</span></span> |
| <span data-ttu-id="617a5-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="617a5-257">Fedora</span></span>                         | <span data-ttu-id="617a5-258">29+</span><span class="sxs-lookup"><span data-stu-id="617a5-258">29+</span></span>                   | <span data-ttu-id="617a5-259">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-259">x64</span></span> |
| <span data-ttu-id="617a5-260">Debian</span><span class="sxs-lookup"><span data-stu-id="617a5-260">Debian</span></span>                         | <span data-ttu-id="617a5-261">9+</span><span class="sxs-lookup"><span data-stu-id="617a5-261">9+</span></span>                    | <span data-ttu-id="617a5-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="617a5-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="617a5-263">Ubuntu</span></span>                         | <span data-ttu-id="617a5-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="617a5-264">16.04+</span></span>                | <span data-ttu-id="617a5-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="617a5-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="617a5-266">Linux Mint</span></span>                     | <span data-ttu-id="617a5-267">18+</span><span class="sxs-lookup"><span data-stu-id="617a5-267">18+</span></span>                   | <span data-ttu-id="617a5-268">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-268">x64</span></span> |
| <span data-ttu-id="617a5-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="617a5-269">openSUSE</span></span>                       | <span data-ttu-id="617a5-270">15+</span><span class="sxs-lookup"><span data-stu-id="617a5-270">15+</span></span>                   | <span data-ttu-id="617a5-271">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-271">x64</span></span> |
| <span data-ttu-id="617a5-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="617a5-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="617a5-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="617a5-273">12 SP2+</span></span>               | <span data-ttu-id="617a5-274">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-274">x64</span></span> |
| <span data-ttu-id="617a5-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-275">Alpine Linux</span></span>                   | <span data-ttu-id="617a5-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="617a5-276">3.8+</span></span>                  | <span data-ttu-id="617a5-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="617a5-277">x64, ARM64</span></span> |

<span data-ttu-id="617a5-278">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="617a5-279">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="617a5-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="617a5-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="617a5-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="617a5-281">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="617a5-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="617a5-282">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="617a5-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="617a5-283">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="617a5-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-284">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-285">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-285">OS</span></span>                             |  <span data-ttu-id="617a5-286">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-286">Version</span></span>                |  <span data-ttu-id="617a5-287">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="617a5-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="617a5-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="617a5-289">6, 7</span></span>                   | <span data-ttu-id="617a5-290">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-290">x64</span></span> |
| <span data-ttu-id="617a5-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="617a5-291">CentOS</span></span>                         |  <span data-ttu-id="617a5-292">7</span><span class="sxs-lookup"><span data-stu-id="617a5-292">7</span></span>                      | <span data-ttu-id="617a5-293">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-293">x64</span></span> |
| <span data-ttu-id="617a5-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-294">Oracle Linux</span></span>                   |  <span data-ttu-id="617a5-295">7</span><span class="sxs-lookup"><span data-stu-id="617a5-295">7</span></span>                      | <span data-ttu-id="617a5-296">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-296">x64</span></span> |
| <span data-ttu-id="617a5-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="617a5-297">Fedora</span></span>                         |  <span data-ttu-id="617a5-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="617a5-298">29, 30</span></span>                 | <span data-ttu-id="617a5-299">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-299">x64</span></span> |
| <span data-ttu-id="617a5-300">Debian</span><span class="sxs-lookup"><span data-stu-id="617a5-300">Debian</span></span>                         |  <span data-ttu-id="617a5-301">9</span><span class="sxs-lookup"><span data-stu-id="617a5-301">9</span></span>                      | <span data-ttu-id="617a5-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-302">x64, ARM32</span></span> |
| <span data-ttu-id="617a5-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="617a5-303">Ubuntu</span></span>                         |  <span data-ttu-id="617a5-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="617a5-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="617a5-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-305">x64, ARM32</span></span> |
| <span data-ttu-id="617a5-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="617a5-306">Linux Mint</span></span>                     |  <span data-ttu-id="617a5-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="617a5-307">17, 18</span></span>                 | <span data-ttu-id="617a5-308">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-308">x64</span></span> |
| <span data-ttu-id="617a5-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="617a5-309">openSUSE</span></span>                       |  <span data-ttu-id="617a5-310">15+</span><span class="sxs-lookup"><span data-stu-id="617a5-310">15+</span></span>                    | <span data-ttu-id="617a5-311">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-311">x64</span></span> |
| <span data-ttu-id="617a5-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="617a5-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="617a5-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="617a5-313">12 SP2+</span></span>                | <span data-ttu-id="617a5-314">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-314">x64</span></span> |
| <span data-ttu-id="617a5-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-315">Alpine Linux</span></span>                   |  <span data-ttu-id="617a5-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="617a5-316">3.8+</span></span>                   | <span data-ttu-id="617a5-317">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-317">x64</span></span> |

<span data-ttu-id="617a5-318">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="617a5-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="617a5-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="617a5-320">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="617a5-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="617a5-321">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="617a5-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="617a5-322">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="617a5-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-323">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-324">SO</span><span class="sxs-lookup"><span data-stu-id="617a5-324">OS</span></span>                             |  <span data-ttu-id="617a5-325">Versión</span><span class="sxs-lookup"><span data-stu-id="617a5-325">Version</span></span>                |  <span data-ttu-id="617a5-326">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="617a5-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="617a5-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="617a5-328">6, 7, 8</span></span>                | <span data-ttu-id="617a5-329">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-329">x64</span></span> |
| <span data-ttu-id="617a5-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="617a5-330">CentOS</span></span>                         |  <span data-ttu-id="617a5-331">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-331">7+</span></span>                     | <span data-ttu-id="617a5-332">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-332">x64</span></span> |
| <span data-ttu-id="617a5-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-333">Oracle Linux</span></span>                   |  <span data-ttu-id="617a5-334">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="617a5-334">7+</span></span>                     | <span data-ttu-id="617a5-335">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-335">x64</span></span> |
| <span data-ttu-id="617a5-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="617a5-336">Fedora</span></span>                         |  <span data-ttu-id="617a5-337">29+</span><span class="sxs-lookup"><span data-stu-id="617a5-337">29+</span></span>                    | <span data-ttu-id="617a5-338">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-338">x64</span></span> |
| <span data-ttu-id="617a5-339">Debian</span><span class="sxs-lookup"><span data-stu-id="617a5-339">Debian</span></span>                         |  <span data-ttu-id="617a5-340">9</span><span class="sxs-lookup"><span data-stu-id="617a5-340">9</span></span>                      | <span data-ttu-id="617a5-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-341">x64, ARM32</span></span> |
| <span data-ttu-id="617a5-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="617a5-342">Ubuntu</span></span>                         |  <span data-ttu-id="617a5-343">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="617a5-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="617a5-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="617a5-344">x64, ARM32</span></span> |
| <span data-ttu-id="617a5-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="617a5-345">Linux Mint</span></span>                     |  <span data-ttu-id="617a5-346">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="617a5-346">17+</span></span>                    | <span data-ttu-id="617a5-347">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-347">x64</span></span> |
| <span data-ttu-id="617a5-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="617a5-348">openSUSE</span></span>                       |  <span data-ttu-id="617a5-349">15+</span><span class="sxs-lookup"><span data-stu-id="617a5-349">15+</span></span>                    | <span data-ttu-id="617a5-350">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-350">x64</span></span> |
| <span data-ttu-id="617a5-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="617a5-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="617a5-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="617a5-352">12 SP2+</span></span>                | <span data-ttu-id="617a5-353">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-353">x64</span></span> |
| <span data-ttu-id="617a5-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-354">Alpine Linux</span></span>                   |  <span data-ttu-id="617a5-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="617a5-355">3.8+</span></span>                   | <span data-ttu-id="617a5-356">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-356">x64</span></span> |

<span data-ttu-id="617a5-357">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="617a5-358">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="617a5-358">Linux distribution dependencies</span></span>

<span data-ttu-id="617a5-359">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="617a5-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="617a5-360">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="617a5-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="617a5-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="617a5-361">Ubuntu</span></span>

<span data-ttu-id="617a5-362">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="617a5-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="617a5-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="617a5-363">liblttng-ust0</span></span>
- <span data-ttu-id="617a5-364">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="617a5-365">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="617a5-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="617a5-366">libssl1.0.0</span></span>
- <span data-ttu-id="617a5-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="617a5-367">libkrb5-3</span></span>
- <span data-ttu-id="617a5-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="617a5-368">zlib1g</span></span>
- <span data-ttu-id="617a5-369">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="617a5-370">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="617a5-371">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="617a5-372">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="617a5-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="617a5-373">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="617a5-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="617a5-374">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="617a5-375">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="617a5-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="617a5-376">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="617a5-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="617a5-377">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="617a5-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="617a5-378">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="617a5-378">CentOS and Fedora</span></span>

<span data-ttu-id="617a5-379">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="617a5-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="617a5-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="617a5-380">lttng-ust</span></span>
- <span data-ttu-id="617a5-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="617a5-381">libcurl</span></span>
- <span data-ttu-id="617a5-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="617a5-382">openssl-libs</span></span>
- <span data-ttu-id="617a5-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="617a5-383">krb5-libs</span></span>
- <span data-ttu-id="617a5-384">libicu</span><span class="sxs-lookup"><span data-stu-id="617a5-384">libicu</span></span>
- <span data-ttu-id="617a5-385">zlib</span><span class="sxs-lookup"><span data-stu-id="617a5-385">zlib</span></span>

<span data-ttu-id="617a5-386">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="617a5-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="617a5-387">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="617a5-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="617a5-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="617a5-388">libunwind</span></span>
- <span data-ttu-id="617a5-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="617a5-389">libuuid</span></span>

<span data-ttu-id="617a5-390">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="617a5-391">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="617a5-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="617a5-392">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="617a5-393">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="617a5-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="617a5-394">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="617a5-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="617a5-395">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="617a5-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="617a5-396">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="617a5-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="617a5-397">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="617a5-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="617a5-398">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="617a5-398">.NET Core Version</span></span> | <span data-ttu-id="617a5-399">macOS</span><span class="sxs-lookup"><span data-stu-id="617a5-399">macOS</span></span>                 | <span data-ttu-id="617a5-400">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="617a5-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="617a5-401">3.1</span><span class="sxs-lookup"><span data-stu-id="617a5-401">3.1</span></span>               | <span data-ttu-id="617a5-402">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="617a5-403">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-403">x64</span></span> | [<span data-ttu-id="617a5-404">Más información</span><span class="sxs-lookup"><span data-stu-id="617a5-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="617a5-405">3.0</span><span class="sxs-lookup"><span data-stu-id="617a5-405">3.0</span></span>               | <span data-ttu-id="617a5-406">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="617a5-407">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-407">x64</span></span> | [<span data-ttu-id="617a5-408">Más información</span><span class="sxs-lookup"><span data-stu-id="617a5-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="617a5-409">2.2</span><span class="sxs-lookup"><span data-stu-id="617a5-409">2.2</span></span>               | <span data-ttu-id="617a5-410">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="617a5-411">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-411">x64</span></span> | [<span data-ttu-id="617a5-412">Más información</span><span class="sxs-lookup"><span data-stu-id="617a5-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="617a5-413">2.1</span><span class="sxs-lookup"><span data-stu-id="617a5-413">2.1</span></span>               | <span data-ttu-id="617a5-414">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="617a5-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="617a5-415">x64</span><span class="sxs-lookup"><span data-stu-id="617a5-415">x64</span></span> | [<span data-ttu-id="617a5-416">Más información</span><span class="sxs-lookup"><span data-stu-id="617a5-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="617a5-417">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="617a5-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="617a5-418">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="617a5-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="617a5-419">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="617a5-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="617a5-420">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="617a5-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="617a5-421">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="617a5-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="617a5-423">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="617a5-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="617a5-424">libgdiplus</span></span>

<span data-ttu-id="617a5-425">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="617a5-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="617a5-426">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="617a5-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="617a5-427">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="617a5-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="617a5-428">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="617a5-428">Next steps</span></span>

- <span data-ttu-id="617a5-429">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="617a5-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="617a5-430">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="617a5-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
