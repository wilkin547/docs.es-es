---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 4164ea5a04d80ab20109168a225b793b02ee616a
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448898"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="a6f55-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a6f55-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="a6f55-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a6f55-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="a6f55-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="a6f55-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="a6f55-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="a6f55-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="a6f55-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-109">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-109">OS</span></span>                            | <span data-ttu-id="a6f55-110">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-110">Version</span></span>                        | <span data-ttu-id="a6f55-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a6f55-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="a6f55-112">Windows Client</span></span>                | <span data-ttu-id="a6f55-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a6f55-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-114">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6f55-115">Windows 10 Client</span></span>             | <span data-ttu-id="a6f55-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-116">Version 1607+</span></span>                  | <span data-ttu-id="a6f55-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-117">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-118">Windows Server</span></span>                | <span data-ttu-id="a6f55-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-119">2012 R2+</span></span>                       | <span data-ttu-id="a6f55-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-120">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-121">Nano Server</span></span>                   | <span data-ttu-id="a6f55-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-122">Version 1803+</span></span>                  | <span data-ttu-id="a6f55-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-123">x64, ARM32</span></span>      |

<span data-ttu-id="a6f55-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="a6f55-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a6f55-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a6f55-126">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="a6f55-126">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-127">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-127">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-128">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-128">OS</span></span>                            | <span data-ttu-id="a6f55-129">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-129">Version</span></span>                        | <span data-ttu-id="a6f55-130">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-130">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a6f55-131">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="a6f55-131">Windows Client</span></span>                | <span data-ttu-id="a6f55-132">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-132">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a6f55-133">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-133">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-134">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6f55-134">Windows 10 Client</span></span>             | <span data-ttu-id="a6f55-135">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-135">Version 1607+</span></span>                  | <span data-ttu-id="a6f55-136">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-136">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-137">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-137">Windows Server</span></span>                | <span data-ttu-id="a6f55-138">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-138">2012 R2+</span></span>                       | <span data-ttu-id="a6f55-139">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-139">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-140">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-140">Nano Server</span></span>                   | <span data-ttu-id="a6f55-141">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-141">Version 1803+</span></span>                  | <span data-ttu-id="a6f55-142">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-142">x64, ARM32</span></span>      |

<span data-ttu-id="a6f55-143">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-143">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="a6f55-144">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a6f55-144">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a6f55-145">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="a6f55-145">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-146">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-146">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-147">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-147">OS</span></span>                            | <span data-ttu-id="a6f55-148">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-148">Version</span></span>                        | <span data-ttu-id="a6f55-149">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-149">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a6f55-150">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="a6f55-150">Windows Client</span></span>                | <span data-ttu-id="a6f55-151">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-151">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a6f55-152">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-152">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-153">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6f55-153">Windows 10 Client</span></span>             | <span data-ttu-id="a6f55-154">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-154">Version 1607+</span></span>                  | <span data-ttu-id="a6f55-155">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-155">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-156">Windows Server</span></span>                | <span data-ttu-id="a6f55-157">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-157">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a6f55-158">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-158">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-159">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-159">Nano Server</span></span>                   | <span data-ttu-id="a6f55-160">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-160">Version 1803+</span></span>                   | <span data-ttu-id="a6f55-161">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-161">x64, ARM32</span></span>      |

<span data-ttu-id="a6f55-162">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-162">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a6f55-163">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-163">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a6f55-164">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="a6f55-164">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-165">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-165">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-166">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-166">OS</span></span>                            | <span data-ttu-id="a6f55-167">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-167">Version</span></span>                        | <span data-ttu-id="a6f55-168">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-168">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="a6f55-169">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="a6f55-169">Windows Client</span></span>                | <span data-ttu-id="a6f55-170">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-170">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="a6f55-171">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-171">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-172">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="a6f55-172">Windows 10 Client</span></span>             | <span data-ttu-id="a6f55-173">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-173">Version 1607+</span></span>                  | <span data-ttu-id="a6f55-174">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-174">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-175">Windows Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-175">Windows Server</span></span>                | <span data-ttu-id="a6f55-176">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-176">2008 R2 SP1+</span></span>                   | <span data-ttu-id="a6f55-177">x64, x86</span><span class="sxs-lookup"><span data-stu-id="a6f55-177">x64, x86</span></span>        |
| <span data-ttu-id="a6f55-178">Nano Server</span><span class="sxs-lookup"><span data-stu-id="a6f55-178">Nano Server</span></span>                   | <span data-ttu-id="a6f55-179">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-179">Version 1803+</span></span>                  | <span data-ttu-id="a6f55-180">x64,</span><span class="sxs-lookup"><span data-stu-id="a6f55-180">x64,</span></span>            |

<span data-ttu-id="a6f55-181">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-181">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="a6f55-182">Windows 7, Vista, 8.1, Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a6f55-182">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="a6f55-183">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="a6f55-183">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="a6f55-184">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="a6f55-184">Windows 7 SP1</span></span>
- <span data-ttu-id="a6f55-185">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="a6f55-185">Windows Vista SP 2</span></span>
- <span data-ttu-id="a6f55-186">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-186">Windows 8.1</span></span>
- <span data-ttu-id="a6f55-187">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="a6f55-187">Windows Server 2008 R2</span></span>
- <span data-ttu-id="a6f55-188">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="a6f55-188">Windows Server 2012 R2</span></span>

<span data-ttu-id="a6f55-189">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6f55-189">Install the following:</span></span>

- <span data-ttu-id="a6f55-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="a6f55-190">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="a6f55-191">KB2533623</span><span class="sxs-lookup"><span data-stu-id="a6f55-191">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="a6f55-192">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6f55-192">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="a6f55-193">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="a6f55-193">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="a6f55-194">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="a6f55-194">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="a6f55-195">\- o -</span><span class="sxs-lookup"><span data-stu-id="a6f55-195">\- or -</span></span>
>
> <span data-ttu-id="a6f55-196">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="a6f55-196">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="a6f55-197">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-197">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="a6f55-198">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6f55-198">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="a6f55-199">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6f55-199">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a6f55-200">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="a6f55-200">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-201">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-201">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-202">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-202">OS</span></span>                             | <span data-ttu-id="a6f55-203">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-203">Version</span></span>               | <span data-ttu-id="a6f55-204">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-204">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="a6f55-205">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-205">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="a6f55-206">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="a6f55-206">6, 7, 8</span></span>               | <span data-ttu-id="a6f55-207">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-207">x64</span></span> |
| <span data-ttu-id="a6f55-208">CentOS</span><span class="sxs-lookup"><span data-stu-id="a6f55-208">CentOS</span></span>                         | <span data-ttu-id="a6f55-209">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-209">7+</span></span>                    | <span data-ttu-id="a6f55-210">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-210">x64</span></span> |
| <span data-ttu-id="a6f55-211">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-211">Oracle Linux</span></span>                   | <span data-ttu-id="a6f55-212">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-212">7+</span></span>                    | <span data-ttu-id="a6f55-213">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-213">x64</span></span> |
| <span data-ttu-id="a6f55-214">Fedora</span><span class="sxs-lookup"><span data-stu-id="a6f55-214">Fedora</span></span>                         | <span data-ttu-id="a6f55-215">29+</span><span class="sxs-lookup"><span data-stu-id="a6f55-215">29+</span></span>                   | <span data-ttu-id="a6f55-216">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-216">x64</span></span> |
| <span data-ttu-id="a6f55-217">Debian</span><span class="sxs-lookup"><span data-stu-id="a6f55-217">Debian</span></span>                         | <span data-ttu-id="a6f55-218">9+</span><span class="sxs-lookup"><span data-stu-id="a6f55-218">9+</span></span>                    | <span data-ttu-id="a6f55-219">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-219">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a6f55-220">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a6f55-220">Ubuntu</span></span>                         | <span data-ttu-id="a6f55-221">16.04+</span><span class="sxs-lookup"><span data-stu-id="a6f55-221">16.04+</span></span>                | <span data-ttu-id="a6f55-222">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-222">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a6f55-223">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a6f55-223">Linux Mint</span></span>                     | <span data-ttu-id="a6f55-224">18+</span><span class="sxs-lookup"><span data-stu-id="a6f55-224">18+</span></span>                   | <span data-ttu-id="a6f55-225">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-225">x64</span></span> |
| <span data-ttu-id="a6f55-226">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a6f55-226">openSUSE</span></span>                       | <span data-ttu-id="a6f55-227">15+</span><span class="sxs-lookup"><span data-stu-id="a6f55-227">15+</span></span>                   | <span data-ttu-id="a6f55-228">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-228">x64</span></span> |
| <span data-ttu-id="a6f55-229">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a6f55-229">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="a6f55-230">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a6f55-230">12 SP2+</span></span>               | <span data-ttu-id="a6f55-231">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-231">x64</span></span> |
| <span data-ttu-id="a6f55-232">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-232">Alpine Linux</span></span>                   | <span data-ttu-id="a6f55-233">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-233">3.10+</span></span>                 | <span data-ttu-id="a6f55-234">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-234">x64, ARM64</span></span> |

<span data-ttu-id="a6f55-235">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-235">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="a6f55-236">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="a6f55-236">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f55-237">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a6f55-237">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="a6f55-238">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="a6f55-238">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="a6f55-239">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="a6f55-239">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="a6f55-240">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="a6f55-240">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="a6f55-241">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6f55-241">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="a6f55-242">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6f55-242">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a6f55-243">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="a6f55-243">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-244">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-244">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-245">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-245">OS</span></span>                             | <span data-ttu-id="a6f55-246">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-246">Version</span></span>               | <span data-ttu-id="a6f55-247">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-247">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="a6f55-248">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-248">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="a6f55-249">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="a6f55-249">6, 7, 8</span></span>               | <span data-ttu-id="a6f55-250">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-250">x64</span></span> |
| <span data-ttu-id="a6f55-251">CentOS</span><span class="sxs-lookup"><span data-stu-id="a6f55-251">CentOS</span></span>                         | <span data-ttu-id="a6f55-252">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-252">7+</span></span>                    | <span data-ttu-id="a6f55-253">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-253">x64</span></span> |
| <span data-ttu-id="a6f55-254">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-254">Oracle Linux</span></span>                   | <span data-ttu-id="a6f55-255">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-255">7+</span></span>                    | <span data-ttu-id="a6f55-256">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-256">x64</span></span> |
| <span data-ttu-id="a6f55-257">Fedora</span><span class="sxs-lookup"><span data-stu-id="a6f55-257">Fedora</span></span>                         | <span data-ttu-id="a6f55-258">29+</span><span class="sxs-lookup"><span data-stu-id="a6f55-258">29+</span></span>                   | <span data-ttu-id="a6f55-259">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-259">x64</span></span> |
| <span data-ttu-id="a6f55-260">Debian</span><span class="sxs-lookup"><span data-stu-id="a6f55-260">Debian</span></span>                         | <span data-ttu-id="a6f55-261">9+</span><span class="sxs-lookup"><span data-stu-id="a6f55-261">9+</span></span>                    | <span data-ttu-id="a6f55-262">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-262">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a6f55-263">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a6f55-263">Ubuntu</span></span>                         | <span data-ttu-id="a6f55-264">16.04+</span><span class="sxs-lookup"><span data-stu-id="a6f55-264">16.04+</span></span>                | <span data-ttu-id="a6f55-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="a6f55-266">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a6f55-266">Linux Mint</span></span>                     | <span data-ttu-id="a6f55-267">18+</span><span class="sxs-lookup"><span data-stu-id="a6f55-267">18+</span></span>                   | <span data-ttu-id="a6f55-268">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-268">x64</span></span> |
| <span data-ttu-id="a6f55-269">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a6f55-269">openSUSE</span></span>                       | <span data-ttu-id="a6f55-270">15+</span><span class="sxs-lookup"><span data-stu-id="a6f55-270">15+</span></span>                   | <span data-ttu-id="a6f55-271">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-271">x64</span></span> |
| <span data-ttu-id="a6f55-272">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a6f55-272">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="a6f55-273">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a6f55-273">12 SP2+</span></span>               | <span data-ttu-id="a6f55-274">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-274">x64</span></span> |
| <span data-ttu-id="a6f55-275">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-275">Alpine Linux</span></span>                   | <span data-ttu-id="a6f55-276">3.8+</span><span class="sxs-lookup"><span data-stu-id="a6f55-276">3.8+</span></span>                  | <span data-ttu-id="a6f55-277">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="a6f55-277">x64, ARM64</span></span> |

<span data-ttu-id="a6f55-278">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-278">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="a6f55-279">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="a6f55-279">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="a6f55-280">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="a6f55-280">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="a6f55-281">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6f55-281">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="a6f55-282">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6f55-282">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a6f55-283">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="a6f55-283">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-284">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-284">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-285">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-285">OS</span></span>                             |  <span data-ttu-id="a6f55-286">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-286">Version</span></span>                |  <span data-ttu-id="a6f55-287">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-287">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a6f55-288">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-288">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a6f55-289">6, 7</span><span class="sxs-lookup"><span data-stu-id="a6f55-289">6, 7</span></span>                   | <span data-ttu-id="a6f55-290">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-290">x64</span></span> |
| <span data-ttu-id="a6f55-291">CentOS</span><span class="sxs-lookup"><span data-stu-id="a6f55-291">CentOS</span></span>                         |  <span data-ttu-id="a6f55-292">7</span><span class="sxs-lookup"><span data-stu-id="a6f55-292">7</span></span>                      | <span data-ttu-id="a6f55-293">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-293">x64</span></span> |
| <span data-ttu-id="a6f55-294">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-294">Oracle Linux</span></span>                   |  <span data-ttu-id="a6f55-295">7</span><span class="sxs-lookup"><span data-stu-id="a6f55-295">7</span></span>                      | <span data-ttu-id="a6f55-296">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-296">x64</span></span> |
| <span data-ttu-id="a6f55-297">Fedora</span><span class="sxs-lookup"><span data-stu-id="a6f55-297">Fedora</span></span>                         |  <span data-ttu-id="a6f55-298">29, 30</span><span class="sxs-lookup"><span data-stu-id="a6f55-298">29, 30</span></span>                 | <span data-ttu-id="a6f55-299">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-299">x64</span></span> |
| <span data-ttu-id="a6f55-300">Debian</span><span class="sxs-lookup"><span data-stu-id="a6f55-300">Debian</span></span>                         |  <span data-ttu-id="a6f55-301">9</span><span class="sxs-lookup"><span data-stu-id="a6f55-301">9</span></span>                      | <span data-ttu-id="a6f55-302">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-302">x64, ARM32</span></span> |
| <span data-ttu-id="a6f55-303">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a6f55-303">Ubuntu</span></span>                         |  <span data-ttu-id="a6f55-304">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="a6f55-304">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="a6f55-305">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-305">x64, ARM32</span></span> |
| <span data-ttu-id="a6f55-306">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a6f55-306">Linux Mint</span></span>                     |  <span data-ttu-id="a6f55-307">17, 18</span><span class="sxs-lookup"><span data-stu-id="a6f55-307">17, 18</span></span>                 | <span data-ttu-id="a6f55-308">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-308">x64</span></span> |
| <span data-ttu-id="a6f55-309">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a6f55-309">openSUSE</span></span>                       |  <span data-ttu-id="a6f55-310">15+</span><span class="sxs-lookup"><span data-stu-id="a6f55-310">15+</span></span>                    | <span data-ttu-id="a6f55-311">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-311">x64</span></span> |
| <span data-ttu-id="a6f55-312">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a6f55-312">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a6f55-313">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a6f55-313">12 SP2+</span></span>                | <span data-ttu-id="a6f55-314">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-314">x64</span></span> |
| <span data-ttu-id="a6f55-315">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-315">Alpine Linux</span></span>                   |  <span data-ttu-id="a6f55-316">3.8+</span><span class="sxs-lookup"><span data-stu-id="a6f55-316">3.8+</span></span>                   | <span data-ttu-id="a6f55-317">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-317">x64</span></span> |

<span data-ttu-id="a6f55-318">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-318">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="a6f55-319">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-319">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="a6f55-320">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="a6f55-320">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="a6f55-321">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="a6f55-321">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="a6f55-322">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="a6f55-322">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-323">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-323">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-324">SO</span><span class="sxs-lookup"><span data-stu-id="a6f55-324">OS</span></span>                             |  <span data-ttu-id="a6f55-325">Versión</span><span class="sxs-lookup"><span data-stu-id="a6f55-325">Version</span></span>                |  <span data-ttu-id="a6f55-326">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-326">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="a6f55-327">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-327">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="a6f55-328">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="a6f55-328">6, 7, 8</span></span>                | <span data-ttu-id="a6f55-329">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-329">x64</span></span> |
| <span data-ttu-id="a6f55-330">CentOS</span><span class="sxs-lookup"><span data-stu-id="a6f55-330">CentOS</span></span>                         |  <span data-ttu-id="a6f55-331">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-331">7+</span></span>                     | <span data-ttu-id="a6f55-332">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-332">x64</span></span> |
| <span data-ttu-id="a6f55-333">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-333">Oracle Linux</span></span>                   |  <span data-ttu-id="a6f55-334">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="a6f55-334">7+</span></span>                     | <span data-ttu-id="a6f55-335">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-335">x64</span></span> |
| <span data-ttu-id="a6f55-336">Fedora</span><span class="sxs-lookup"><span data-stu-id="a6f55-336">Fedora</span></span>                         |  <span data-ttu-id="a6f55-337">29+</span><span class="sxs-lookup"><span data-stu-id="a6f55-337">29+</span></span>                    | <span data-ttu-id="a6f55-338">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-338">x64</span></span> |
| <span data-ttu-id="a6f55-339">Debian</span><span class="sxs-lookup"><span data-stu-id="a6f55-339">Debian</span></span>                         |  <span data-ttu-id="a6f55-340">9</span><span class="sxs-lookup"><span data-stu-id="a6f55-340">9</span></span>                      | <span data-ttu-id="a6f55-341">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-341">x64, ARM32</span></span> |
| <span data-ttu-id="a6f55-342">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a6f55-342">Ubuntu</span></span>                         |  <span data-ttu-id="a6f55-343">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="a6f55-343">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="a6f55-344">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="a6f55-344">x64, ARM32</span></span> |
| <span data-ttu-id="a6f55-345">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="a6f55-345">Linux Mint</span></span>                     |  <span data-ttu-id="a6f55-346">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="a6f55-346">17+</span></span>                    | <span data-ttu-id="a6f55-347">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-347">x64</span></span> |
| <span data-ttu-id="a6f55-348">openSUSE</span><span class="sxs-lookup"><span data-stu-id="a6f55-348">openSUSE</span></span>                       |  <span data-ttu-id="a6f55-349">15+</span><span class="sxs-lookup"><span data-stu-id="a6f55-349">15+</span></span>                    | <span data-ttu-id="a6f55-350">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-350">x64</span></span> |
| <span data-ttu-id="a6f55-351">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="a6f55-351">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="a6f55-352">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="a6f55-352">12 SP2+</span></span>                | <span data-ttu-id="a6f55-353">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-353">x64</span></span> |
| <span data-ttu-id="a6f55-354">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-354">Alpine Linux</span></span>                   |  <span data-ttu-id="a6f55-355">3.8+</span><span class="sxs-lookup"><span data-stu-id="a6f55-355">3.8+</span></span>                   | <span data-ttu-id="a6f55-356">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-356">x64</span></span> |

<span data-ttu-id="a6f55-357">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-357">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="a6f55-358">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="a6f55-358">Linux distribution dependencies</span></span>

<span data-ttu-id="a6f55-359">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="a6f55-359">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6f55-360">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="a6f55-360">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="a6f55-361">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="a6f55-361">Ubuntu</span></span>

<span data-ttu-id="a6f55-362">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6f55-362">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="a6f55-363">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="a6f55-363">liblttng-ust0</span></span>
- <span data-ttu-id="a6f55-364">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-364">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="a6f55-365">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-365">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="a6f55-366">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="a6f55-366">libssl1.0.0</span></span>
- <span data-ttu-id="a6f55-367">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="a6f55-367">libkrb5-3</span></span>
- <span data-ttu-id="a6f55-368">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a6f55-368">zlib1g</span></span>
- <span data-ttu-id="a6f55-369">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-369">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="a6f55-370">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-370">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="a6f55-371">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-371">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="a6f55-372">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="a6f55-372">libicu60 (for 18.x)</span></span>

<span data-ttu-id="a6f55-373">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6f55-373">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a6f55-374">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-374">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="a6f55-375">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="a6f55-375">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a6f55-376">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="a6f55-376">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a6f55-377">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="a6f55-377">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="a6f55-378">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="a6f55-378">CentOS and Fedora</span></span>

<span data-ttu-id="a6f55-379">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="a6f55-379">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="a6f55-380">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="a6f55-380">lttng-ust</span></span>
- <span data-ttu-id="a6f55-381">libcurl</span><span class="sxs-lookup"><span data-stu-id="a6f55-381">libcurl</span></span>
- <span data-ttu-id="a6f55-382">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="a6f55-382">openssl-libs</span></span>
- <span data-ttu-id="a6f55-383">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="a6f55-383">krb5-libs</span></span>
- <span data-ttu-id="a6f55-384">libicu</span><span class="sxs-lookup"><span data-stu-id="a6f55-384">libicu</span></span>
- <span data-ttu-id="a6f55-385">zlib</span><span class="sxs-lookup"><span data-stu-id="a6f55-385">zlib</span></span>

<span data-ttu-id="a6f55-386">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="a6f55-386">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="a6f55-387">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6f55-387">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="a6f55-388">libunwind</span><span class="sxs-lookup"><span data-stu-id="a6f55-388">libunwind</span></span>
- <span data-ttu-id="a6f55-389">libuuid</span><span class="sxs-lookup"><span data-stu-id="a6f55-389">libuuid</span></span>

<span data-ttu-id="a6f55-390">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-390">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="a6f55-391">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="a6f55-391">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="a6f55-392">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-392">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="a6f55-393">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="a6f55-393">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="a6f55-394">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="a6f55-394">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="a6f55-395">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="a6f55-395">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="a6f55-396">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="a6f55-396">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="a6f55-397">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a6f55-397">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a6f55-398">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a6f55-398">.NET Core Version</span></span> | <span data-ttu-id="a6f55-399">macOS</span><span class="sxs-lookup"><span data-stu-id="a6f55-399">macOS</span></span>                 | <span data-ttu-id="a6f55-400">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a6f55-400">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="a6f55-401">3.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-401">3.1</span></span>               | <span data-ttu-id="a6f55-402">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-402">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a6f55-403">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-403">x64</span></span> | [<span data-ttu-id="a6f55-404">Más información</span><span class="sxs-lookup"><span data-stu-id="a6f55-404">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="a6f55-405">3.0</span><span class="sxs-lookup"><span data-stu-id="a6f55-405">3.0</span></span>               | <span data-ttu-id="a6f55-406">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a6f55-407">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-407">x64</span></span> | [<span data-ttu-id="a6f55-408">Más información</span><span class="sxs-lookup"><span data-stu-id="a6f55-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="a6f55-409">2.2</span><span class="sxs-lookup"><span data-stu-id="a6f55-409">2.2</span></span>               | <span data-ttu-id="a6f55-410">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-410">Sierra (10.12+)</span></span>       | <span data-ttu-id="a6f55-411">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-411">x64</span></span> | [<span data-ttu-id="a6f55-412">Más información</span><span class="sxs-lookup"><span data-stu-id="a6f55-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="a6f55-413">2.1</span><span class="sxs-lookup"><span data-stu-id="a6f55-413">2.1</span></span>               | <span data-ttu-id="a6f55-414">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a6f55-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="a6f55-415">x64</span><span class="sxs-lookup"><span data-stu-id="a6f55-415">x64</span></span> | [<span data-ttu-id="a6f55-416">Más información</span><span class="sxs-lookup"><span data-stu-id="a6f55-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

## <a name="libgdiplus"></a><span data-ttu-id="a6f55-417">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="a6f55-417">libgdiplus</span></span>

<span data-ttu-id="a6f55-418">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="a6f55-418">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="a6f55-419">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="a6f55-419">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="a6f55-420">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="a6f55-420">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="a6f55-421">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a6f55-421">Next steps</span></span>

- <span data-ttu-id="a6f55-422">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a6f55-422">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="a6f55-423">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="a6f55-423">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
