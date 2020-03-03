---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: ca86b3c158bb38c1293cd4303dcf4c00ea9175b1
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157820"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="6f317-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6f317-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="6f317-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f317-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="6f317-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="6f317-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="6f317-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6f317-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="6f317-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="6f317-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-109">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-109">OS</span></span>                            | <span data-ttu-id="6f317-110">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-110">Version</span></span>                        | <span data-ttu-id="6f317-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6f317-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="6f317-112">Windows Client</span></span>                | <span data-ttu-id="6f317-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="6f317-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6f317-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-114">x64, x86</span></span>        |
| <span data-ttu-id="6f317-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f317-115">Windows 10 Client</span></span>             | <span data-ttu-id="6f317-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-116">Version 1607+</span></span>                  | <span data-ttu-id="6f317-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-117">x64, x86</span></span>        |
| <span data-ttu-id="6f317-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6f317-118">Windows Server</span></span>                | <span data-ttu-id="6f317-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-119">2012 R2+</span></span>                       | <span data-ttu-id="6f317-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-120">x64, x86</span></span>        |
| <span data-ttu-id="6f317-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6f317-121">Nano Server</span></span>                   | <span data-ttu-id="6f317-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-122">Version 1803+</span></span>                  | <span data-ttu-id="6f317-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-123">x64, ARM32</span></span>      |

<span data-ttu-id="6f317-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="6f317-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6f317-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="6f317-126">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="6f317-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-127">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-128">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-128">OS</span></span>                            | <span data-ttu-id="6f317-129">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-129">Version</span></span>                        | <span data-ttu-id="6f317-130">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6f317-131">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="6f317-131">Windows Client</span></span>                | <span data-ttu-id="6f317-132">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="6f317-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6f317-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-133">x64, x86</span></span>        |
| <span data-ttu-id="6f317-134">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f317-134">Windows 10 Client</span></span>             | <span data-ttu-id="6f317-135">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-135">Version 1607+</span></span>                  | <span data-ttu-id="6f317-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-136">x64, x86</span></span>        |
| <span data-ttu-id="6f317-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6f317-137">Windows Server</span></span>                | <span data-ttu-id="6f317-138">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-138">2012 R2+</span></span>                       | <span data-ttu-id="6f317-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-139">x64, x86</span></span>        |
| <span data-ttu-id="6f317-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6f317-140">Nano Server</span></span>                   | <span data-ttu-id="6f317-141">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-141">Version 1803+</span></span>                  | <span data-ttu-id="6f317-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-142">x64, ARM32</span></span>      |

<span data-ttu-id="6f317-143">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="6f317-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6f317-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6f317-145">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="6f317-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-146">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-147">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-147">OS</span></span>                            | <span data-ttu-id="6f317-148">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-148">Version</span></span>                        | <span data-ttu-id="6f317-149">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6f317-150">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="6f317-150">Windows Client</span></span>                | <span data-ttu-id="6f317-151">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="6f317-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6f317-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-152">x64, x86</span></span>        |
| <span data-ttu-id="6f317-153">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f317-153">Windows 10 Client</span></span>             | <span data-ttu-id="6f317-154">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-154">Version 1607+</span></span>                  | <span data-ttu-id="6f317-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-155">x64, x86</span></span>        |
| <span data-ttu-id="6f317-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6f317-156">Windows Server</span></span>                | <span data-ttu-id="6f317-157">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6f317-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-158">x64, x86</span></span>        |
| <span data-ttu-id="6f317-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6f317-159">Nano Server</span></span>                   | <span data-ttu-id="6f317-160">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-160">Version 1803+</span></span>                   | <span data-ttu-id="6f317-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-161">x64, ARM32</span></span>      |

<span data-ttu-id="6f317-162">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="6f317-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6f317-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6f317-164">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="6f317-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-165">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-166">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-166">OS</span></span>                            | <span data-ttu-id="6f317-167">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-167">Version</span></span>                        | <span data-ttu-id="6f317-168">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="6f317-169">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="6f317-169">Windows Client</span></span>                | <span data-ttu-id="6f317-170">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="6f317-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="6f317-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-171">x64, x86</span></span>        |
| <span data-ttu-id="6f317-172">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="6f317-172">Windows 10 Client</span></span>             | <span data-ttu-id="6f317-173">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-173">Version 1607+</span></span>                  | <span data-ttu-id="6f317-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-174">x64, x86</span></span>        |
| <span data-ttu-id="6f317-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="6f317-175">Windows Server</span></span>                | <span data-ttu-id="6f317-176">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="6f317-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="6f317-177">x64, x86</span></span>        |
| <span data-ttu-id="6f317-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="6f317-178">Nano Server</span></span>                   | <span data-ttu-id="6f317-179">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-179">Version 1803+</span></span>                  | <span data-ttu-id="6f317-180">x64,</span><span class="sxs-lookup"><span data-stu-id="6f317-180">x64,</span></span>            |

<span data-ttu-id="6f317-181">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="6f317-182">Windows 7, Vista, 8.1, Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6f317-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="6f317-183">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="6f317-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="6f317-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="6f317-184">Windows 7 SP1</span></span>
- <span data-ttu-id="6f317-185">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="6f317-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="6f317-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6f317-186">Windows 8.1</span></span>
- <span data-ttu-id="6f317-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6f317-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="6f317-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6f317-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="6f317-189">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f317-189">Install the following:</span></span>

- <span data-ttu-id="6f317-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="6f317-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="6f317-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="6f317-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="6f317-192">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f317-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="6f317-193">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="6f317-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="6f317-194">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="6f317-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="6f317-195">\- o -</span><span class="sxs-lookup"><span data-stu-id="6f317-195">\- or -</span></span>
>
> <span data-ttu-id="6f317-196">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="6f317-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="6f317-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="6f317-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="6f317-198">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f317-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="6f317-199">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="6f317-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6f317-200">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="6f317-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-201">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-202">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-202">OS</span></span>                             | <span data-ttu-id="6f317-203">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-203">Version</span></span>               | <span data-ttu-id="6f317-204">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="6f317-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="6f317-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6f317-206">6, 7, 8</span></span>               | <span data-ttu-id="6f317-207">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-207">x64</span></span> |
| <span data-ttu-id="6f317-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="6f317-208">CentOS</span></span>                         | <span data-ttu-id="6f317-209">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-209">7+</span></span>                    | <span data-ttu-id="6f317-210">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-210">x64</span></span> |
| <span data-ttu-id="6f317-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-211">Oracle Linux</span></span>                   | <span data-ttu-id="6f317-212">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-212">7+</span></span>                    | <span data-ttu-id="6f317-213">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-213">x64</span></span> |
| <span data-ttu-id="6f317-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="6f317-214">Fedora</span></span>                         | <span data-ttu-id="6f317-215">29+</span><span class="sxs-lookup"><span data-stu-id="6f317-215">29+</span></span>                   | <span data-ttu-id="6f317-216">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-216">x64</span></span> |
| <span data-ttu-id="6f317-217">Debian</span><span class="sxs-lookup"><span data-stu-id="6f317-217">Debian</span></span>                         | <span data-ttu-id="6f317-218">9+</span><span class="sxs-lookup"><span data-stu-id="6f317-218">9+</span></span>                    | <span data-ttu-id="6f317-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6f317-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f317-220">Ubuntu</span></span>                         | <span data-ttu-id="6f317-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="6f317-221">16.04+</span></span>                | <span data-ttu-id="6f317-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6f317-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6f317-223">Linux Mint</span></span>                     | <span data-ttu-id="6f317-224">18+</span><span class="sxs-lookup"><span data-stu-id="6f317-224">18+</span></span>                   | <span data-ttu-id="6f317-225">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-225">x64</span></span> |
| <span data-ttu-id="6f317-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6f317-226">openSUSE</span></span>                       | <span data-ttu-id="6f317-227">15+</span><span class="sxs-lookup"><span data-stu-id="6f317-227">15+</span></span>                   | <span data-ttu-id="6f317-228">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-228">x64</span></span> |
| <span data-ttu-id="6f317-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6f317-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="6f317-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6f317-230">12 SP2+</span></span>               | <span data-ttu-id="6f317-231">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-231">x64</span></span> |
| <span data-ttu-id="6f317-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-232">Alpine Linux</span></span>                   | <span data-ttu-id="6f317-233">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-233">3.10+</span></span>                 | <span data-ttu-id="6f317-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-234">x64, ARM64</span></span> |

<span data-ttu-id="6f317-235">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="6f317-236">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="6f317-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f317-237">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="6f317-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="6f317-238">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="6f317-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="6f317-239">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="6f317-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="6f317-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="6f317-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="6f317-241">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f317-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="6f317-242">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="6f317-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6f317-243">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="6f317-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-244">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-245">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-245">OS</span></span>                             | <span data-ttu-id="6f317-246">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-246">Version</span></span>               | <span data-ttu-id="6f317-247">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="6f317-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="6f317-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6f317-249">6, 7, 8</span></span>               | <span data-ttu-id="6f317-250">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-250">x64</span></span> |
| <span data-ttu-id="6f317-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="6f317-251">CentOS</span></span>                         | <span data-ttu-id="6f317-252">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-252">7+</span></span>                    | <span data-ttu-id="6f317-253">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-253">x64</span></span> |
| <span data-ttu-id="6f317-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-254">Oracle Linux</span></span>                   | <span data-ttu-id="6f317-255">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-255">7+</span></span>                    | <span data-ttu-id="6f317-256">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-256">x64</span></span> |
| <span data-ttu-id="6f317-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="6f317-257">Fedora</span></span>                         | <span data-ttu-id="6f317-258">29+</span><span class="sxs-lookup"><span data-stu-id="6f317-258">29+</span></span>                   | <span data-ttu-id="6f317-259">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-259">x64</span></span> |
| <span data-ttu-id="6f317-260">Debian</span><span class="sxs-lookup"><span data-stu-id="6f317-260">Debian</span></span>                         | <span data-ttu-id="6f317-261">9+</span><span class="sxs-lookup"><span data-stu-id="6f317-261">9+</span></span>                    | <span data-ttu-id="6f317-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6f317-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f317-263">Ubuntu</span></span>                         | <span data-ttu-id="6f317-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="6f317-264">16.04+</span></span>                | <span data-ttu-id="6f317-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="6f317-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6f317-266">Linux Mint</span></span>                     | <span data-ttu-id="6f317-267">18+</span><span class="sxs-lookup"><span data-stu-id="6f317-267">18+</span></span>                   | <span data-ttu-id="6f317-268">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-268">x64</span></span> |
| <span data-ttu-id="6f317-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6f317-269">openSUSE</span></span>                       | <span data-ttu-id="6f317-270">15+</span><span class="sxs-lookup"><span data-stu-id="6f317-270">15+</span></span>                   | <span data-ttu-id="6f317-271">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-271">x64</span></span> |
| <span data-ttu-id="6f317-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6f317-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="6f317-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6f317-273">12 SP2+</span></span>               | <span data-ttu-id="6f317-274">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-274">x64</span></span> |
| <span data-ttu-id="6f317-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-275">Alpine Linux</span></span>                   | <span data-ttu-id="6f317-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="6f317-276">3.8+</span></span>                  | <span data-ttu-id="6f317-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="6f317-277">x64, ARM64</span></span> |

<span data-ttu-id="6f317-278">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="6f317-279">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="6f317-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="6f317-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="6f317-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="6f317-281">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f317-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="6f317-282">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="6f317-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6f317-283">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="6f317-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-284">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-285">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-285">OS</span></span>                             |  <span data-ttu-id="6f317-286">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-286">Version</span></span>                |  <span data-ttu-id="6f317-287">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="6f317-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="6f317-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="6f317-289">6, 7</span></span>                   | <span data-ttu-id="6f317-290">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-290">x64</span></span> |
| <span data-ttu-id="6f317-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="6f317-291">CentOS</span></span>                         |  <span data-ttu-id="6f317-292">7</span><span class="sxs-lookup"><span data-stu-id="6f317-292">7</span></span>                      | <span data-ttu-id="6f317-293">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-293">x64</span></span> |
| <span data-ttu-id="6f317-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-294">Oracle Linux</span></span>                   |  <span data-ttu-id="6f317-295">7</span><span class="sxs-lookup"><span data-stu-id="6f317-295">7</span></span>                      | <span data-ttu-id="6f317-296">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-296">x64</span></span> |
| <span data-ttu-id="6f317-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="6f317-297">Fedora</span></span>                         |  <span data-ttu-id="6f317-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="6f317-298">29, 30</span></span>                 | <span data-ttu-id="6f317-299">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-299">x64</span></span> |
| <span data-ttu-id="6f317-300">Debian</span><span class="sxs-lookup"><span data-stu-id="6f317-300">Debian</span></span>                         |  <span data-ttu-id="6f317-301">9</span><span class="sxs-lookup"><span data-stu-id="6f317-301">9</span></span>                      | <span data-ttu-id="6f317-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-302">x64, ARM32</span></span> |
| <span data-ttu-id="6f317-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f317-303">Ubuntu</span></span>                         |  <span data-ttu-id="6f317-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="6f317-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="6f317-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-305">x64, ARM32</span></span> |
| <span data-ttu-id="6f317-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6f317-306">Linux Mint</span></span>                     |  <span data-ttu-id="6f317-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="6f317-307">17, 18</span></span>                 | <span data-ttu-id="6f317-308">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-308">x64</span></span> |
| <span data-ttu-id="6f317-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6f317-309">openSUSE</span></span>                       |  <span data-ttu-id="6f317-310">15+</span><span class="sxs-lookup"><span data-stu-id="6f317-310">15+</span></span>                    | <span data-ttu-id="6f317-311">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-311">x64</span></span> |
| <span data-ttu-id="6f317-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6f317-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="6f317-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6f317-313">12 SP2+</span></span>                | <span data-ttu-id="6f317-314">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-314">x64</span></span> |
| <span data-ttu-id="6f317-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-315">Alpine Linux</span></span>                   |  <span data-ttu-id="6f317-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="6f317-316">3.8+</span></span>                   | <span data-ttu-id="6f317-317">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-317">x64</span></span> |

<span data-ttu-id="6f317-318">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="6f317-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="6f317-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="6f317-320">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="6f317-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="6f317-321">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="6f317-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="6f317-322">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="6f317-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-323">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-324">SO</span><span class="sxs-lookup"><span data-stu-id="6f317-324">OS</span></span>                             |  <span data-ttu-id="6f317-325">Versión</span><span class="sxs-lookup"><span data-stu-id="6f317-325">Version</span></span>                |  <span data-ttu-id="6f317-326">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="6f317-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="6f317-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="6f317-328">6, 7, 8</span></span>                | <span data-ttu-id="6f317-329">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-329">x64</span></span> |
| <span data-ttu-id="6f317-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="6f317-330">CentOS</span></span>                         |  <span data-ttu-id="6f317-331">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-331">7+</span></span>                     | <span data-ttu-id="6f317-332">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-332">x64</span></span> |
| <span data-ttu-id="6f317-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-333">Oracle Linux</span></span>                   |  <span data-ttu-id="6f317-334">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="6f317-334">7+</span></span>                     | <span data-ttu-id="6f317-335">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-335">x64</span></span> |
| <span data-ttu-id="6f317-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="6f317-336">Fedora</span></span>                         |  <span data-ttu-id="6f317-337">29+</span><span class="sxs-lookup"><span data-stu-id="6f317-337">29+</span></span>                    | <span data-ttu-id="6f317-338">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-338">x64</span></span> |
| <span data-ttu-id="6f317-339">Debian</span><span class="sxs-lookup"><span data-stu-id="6f317-339">Debian</span></span>                         |  <span data-ttu-id="6f317-340">9</span><span class="sxs-lookup"><span data-stu-id="6f317-340">9</span></span>                      | <span data-ttu-id="6f317-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-341">x64, ARM32</span></span> |
| <span data-ttu-id="6f317-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f317-342">Ubuntu</span></span>                         |  <span data-ttu-id="6f317-343">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="6f317-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="6f317-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="6f317-344">x64, ARM32</span></span> |
| <span data-ttu-id="6f317-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="6f317-345">Linux Mint</span></span>                     |  <span data-ttu-id="6f317-346">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="6f317-346">17+</span></span>                    | <span data-ttu-id="6f317-347">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-347">x64</span></span> |
| <span data-ttu-id="6f317-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="6f317-348">openSUSE</span></span>                       |  <span data-ttu-id="6f317-349">15+</span><span class="sxs-lookup"><span data-stu-id="6f317-349">15+</span></span>                    | <span data-ttu-id="6f317-350">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-350">x64</span></span> |
| <span data-ttu-id="6f317-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="6f317-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="6f317-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="6f317-352">12 SP2+</span></span>                | <span data-ttu-id="6f317-353">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-353">x64</span></span> |
| <span data-ttu-id="6f317-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-354">Alpine Linux</span></span>                   |  <span data-ttu-id="6f317-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="6f317-355">3.8+</span></span>                   | <span data-ttu-id="6f317-356">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-356">x64</span></span> |

<span data-ttu-id="6f317-357">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="6f317-358">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="6f317-358">Linux distribution dependencies</span></span>

<span data-ttu-id="6f317-359">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="6f317-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6f317-360">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="6f317-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="6f317-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="6f317-361">Ubuntu</span></span>

<span data-ttu-id="6f317-362">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f317-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="6f317-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="6f317-363">liblttng-ust0</span></span>
- <span data-ttu-id="6f317-364">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="6f317-365">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="6f317-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="6f317-366">libssl1.0.0</span></span>
- <span data-ttu-id="6f317-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="6f317-367">libkrb5-3</span></span>
- <span data-ttu-id="6f317-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="6f317-368">zlib1g</span></span>
- <span data-ttu-id="6f317-369">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="6f317-370">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="6f317-371">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="6f317-372">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="6f317-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="6f317-373">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f317-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="6f317-374">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="6f317-375">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6f317-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="6f317-376">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="6f317-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="6f317-377">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="6f317-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="6f317-378">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="6f317-378">CentOS and Fedora</span></span>

<span data-ttu-id="6f317-379">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="6f317-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="6f317-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="6f317-380">lttng-ust</span></span>
- <span data-ttu-id="6f317-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="6f317-381">libcurl</span></span>
- <span data-ttu-id="6f317-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="6f317-382">openssl-libs</span></span>
- <span data-ttu-id="6f317-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="6f317-383">krb5-libs</span></span>
- <span data-ttu-id="6f317-384">libicu</span><span class="sxs-lookup"><span data-stu-id="6f317-384">libicu</span></span>
- <span data-ttu-id="6f317-385">zlib</span><span class="sxs-lookup"><span data-stu-id="6f317-385">zlib</span></span>

<span data-ttu-id="6f317-386">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="6f317-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="6f317-387">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="6f317-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="6f317-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="6f317-388">libunwind</span></span>
- <span data-ttu-id="6f317-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="6f317-389">libuuid</span></span>

<span data-ttu-id="6f317-390">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="6f317-391">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f317-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="6f317-392">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="6f317-393">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6f317-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="6f317-394">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="6f317-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="6f317-395">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="6f317-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="6f317-396">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="6f317-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="6f317-397">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="6f317-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="6f317-398">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6f317-398">.NET Core Version</span></span> | <span data-ttu-id="6f317-399">macOS</span><span class="sxs-lookup"><span data-stu-id="6f317-399">macOS</span></span>                 | <span data-ttu-id="6f317-400">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="6f317-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="6f317-401">3.1</span><span class="sxs-lookup"><span data-stu-id="6f317-401">3.1</span></span>               | <span data-ttu-id="6f317-402">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="6f317-403">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-403">x64</span></span> | [<span data-ttu-id="6f317-404">Más información</span><span class="sxs-lookup"><span data-stu-id="6f317-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="6f317-405">3.0</span><span class="sxs-lookup"><span data-stu-id="6f317-405">3.0</span></span>               | <span data-ttu-id="6f317-406">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="6f317-407">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-407">x64</span></span> | [<span data-ttu-id="6f317-408">Más información</span><span class="sxs-lookup"><span data-stu-id="6f317-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="6f317-409">2.2</span><span class="sxs-lookup"><span data-stu-id="6f317-409">2.2</span></span>               | <span data-ttu-id="6f317-410">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="6f317-411">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-411">x64</span></span> | [<span data-ttu-id="6f317-412">Más información</span><span class="sxs-lookup"><span data-stu-id="6f317-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="6f317-413">2.1</span><span class="sxs-lookup"><span data-stu-id="6f317-413">2.1</span></span>               | <span data-ttu-id="6f317-414">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="6f317-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="6f317-415">x64</span><span class="sxs-lookup"><span data-stu-id="6f317-415">x64</span></span> | [<span data-ttu-id="6f317-416">Más información</span><span class="sxs-lookup"><span data-stu-id="6f317-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="6f317-417">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="6f317-417">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="6f317-418">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6f317-418">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="6f317-419">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="6f317-419">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="6f317-420">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="6f317-420">Prior released versions aren't notarized.</span></span> <span data-ttu-id="6f317-421">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="6f317-421">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="6f317-423">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-423">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="6f317-424">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="6f317-424">libgdiplus</span></span>

<span data-ttu-id="6f317-425">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="6f317-425">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="6f317-426">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="6f317-426">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="6f317-427">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="6f317-427">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="6f317-428">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="6f317-428">Next steps</span></span>

- <span data-ttu-id="6f317-429">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f317-429">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="6f317-430">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="6f317-430">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
