---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 42765d4402dfa17d4e962b2ecaf7a83e91853c76
ms.sourcegitcommit: 839777281a281684a7e2906dccb3acd7f6a32023
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/24/2020
ms.locfileid: "82140992"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="c8027-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c8027-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="c8027-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c8027-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="c8027-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="c8027-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="c8027-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c8027-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c8027-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="c8027-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-109">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-109">OS</span></span>                            | <span data-ttu-id="c8027-110">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-110">Version</span></span>                        | <span data-ttu-id="c8027-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c8027-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="c8027-112">Windows Client</span></span>                | <span data-ttu-id="c8027-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="c8027-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c8027-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-114">x64, x86</span></span>        |
| <span data-ttu-id="c8027-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8027-115">Windows 10 Client</span></span>             | <span data-ttu-id="c8027-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-116">Version 1607+</span></span>                  | <span data-ttu-id="c8027-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-117">x64, x86</span></span>        |
| <span data-ttu-id="c8027-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c8027-118">Windows Server</span></span>                | <span data-ttu-id="c8027-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-119">2012 R2+</span></span>                       | <span data-ttu-id="c8027-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-120">x64, x86</span></span>        |
| <span data-ttu-id="c8027-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c8027-121">Nano Server</span></span>                   | <span data-ttu-id="c8027-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-122">Version 1803+</span></span>                  | <span data-ttu-id="c8027-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-123">x64, ARM32</span></span>      |

<span data-ttu-id="c8027-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c8027-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c8027-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c8027-126">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c8027-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c8027-127">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="c8027-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-128">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-129">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-129">OS</span></span>                            | <span data-ttu-id="c8027-130">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-130">Version</span></span>                        | <span data-ttu-id="c8027-131">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c8027-132">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="c8027-132">Windows Client</span></span>                | <span data-ttu-id="c8027-133">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="c8027-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c8027-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-134">x64, x86</span></span>        |
| <span data-ttu-id="c8027-135">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8027-135">Windows 10 Client</span></span>             | <span data-ttu-id="c8027-136">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-136">Version 1607+</span></span>                  | <span data-ttu-id="c8027-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-137">x64, x86</span></span>        |
| <span data-ttu-id="c8027-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c8027-138">Windows Server</span></span>                | <span data-ttu-id="c8027-139">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-139">2012 R2+</span></span>                       | <span data-ttu-id="c8027-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-140">x64, x86</span></span>        |
| <span data-ttu-id="c8027-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c8027-141">Nano Server</span></span>                   | <span data-ttu-id="c8027-142">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-142">Version 1803+</span></span>                  | <span data-ttu-id="c8027-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-143">x64, ARM32</span></span>      |

<span data-ttu-id="c8027-144">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c8027-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c8027-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c8027-146">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c8027-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c8027-147">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="c8027-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-148">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-149">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-149">OS</span></span>                            | <span data-ttu-id="c8027-150">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-150">Version</span></span>                        | <span data-ttu-id="c8027-151">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c8027-152">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="c8027-152">Windows Client</span></span>                | <span data-ttu-id="c8027-153">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="c8027-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c8027-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-154">x64, x86</span></span>        |
| <span data-ttu-id="c8027-155">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8027-155">Windows 10 Client</span></span>             | <span data-ttu-id="c8027-156">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-156">Version 1607+</span></span>                  | <span data-ttu-id="c8027-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-157">x64, x86</span></span>        |
| <span data-ttu-id="c8027-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c8027-158">Windows Server</span></span>                | <span data-ttu-id="c8027-159">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c8027-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-160">x64, x86</span></span>        |
| <span data-ttu-id="c8027-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c8027-161">Nano Server</span></span>                   | <span data-ttu-id="c8027-162">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-162">Version 1803+</span></span>                   | <span data-ttu-id="c8027-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-163">x64, ARM32</span></span>      |

<span data-ttu-id="c8027-164">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c8027-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c8027-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c8027-166">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="c8027-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-167">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-168">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-168">OS</span></span>                            | <span data-ttu-id="c8027-169">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-169">Version</span></span>                        | <span data-ttu-id="c8027-170">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="c8027-171">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="c8027-171">Windows Client</span></span>                | <span data-ttu-id="c8027-172">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="c8027-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="c8027-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-173">x64, x86</span></span>        |
| <span data-ttu-id="c8027-174">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="c8027-174">Windows 10 Client</span></span>             | <span data-ttu-id="c8027-175">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-175">Version 1607+</span></span>                  | <span data-ttu-id="c8027-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-176">x64, x86</span></span>        |
| <span data-ttu-id="c8027-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="c8027-177">Windows Server</span></span>                | <span data-ttu-id="c8027-178">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="c8027-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="c8027-179">x64, x86</span></span>        |
| <span data-ttu-id="c8027-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="c8027-180">Nano Server</span></span>                   | <span data-ttu-id="c8027-181">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-181">Version 1803+</span></span>                  | <span data-ttu-id="c8027-182">x64,</span><span class="sxs-lookup"><span data-stu-id="c8027-182">x64,</span></span>            |

<span data-ttu-id="c8027-183">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="c8027-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c8027-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="c8027-185">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="c8027-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="c8027-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="c8027-186">Windows 7 SP1</span></span>
- <span data-ttu-id="c8027-187">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="c8027-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="c8027-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c8027-188">Windows 8.1</span></span>
- <span data-ttu-id="c8027-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="c8027-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="c8027-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="c8027-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="c8027-191">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8027-191">Install the following:</span></span>

- <span data-ttu-id="c8027-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="c8027-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="c8027-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="c8027-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="c8027-194">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8027-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="c8027-195">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c8027-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c8027-196">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="c8027-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c8027-197">\- o -</span><span class="sxs-lookup"><span data-stu-id="c8027-197">\- or -</span></span>
>
> <span data-ttu-id="c8027-198">El programa no se puede iniciar porque falta el archivo *api-ms-win-cor-timezone-l1-1-0.dll* en el equipo.</span><span class="sxs-lookup"><span data-stu-id="c8027-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="c8027-199">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="c8027-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="c8027-200">\- o -</span><span class="sxs-lookup"><span data-stu-id="c8027-200">\- or -</span></span>
>
> <span data-ttu-id="c8027-201">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="c8027-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="c8027-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c8027-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="c8027-203">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c8027-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c8027-204">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="c8027-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c8027-205">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="c8027-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-206">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-207">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-207">OS</span></span>                             | <span data-ttu-id="c8027-208">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-208">Version</span></span>               | <span data-ttu-id="c8027-209">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c8027-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c8027-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c8027-211">6, 7, 8</span></span>               | <span data-ttu-id="c8027-212">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-212">x64</span></span> |
| <span data-ttu-id="c8027-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="c8027-213">CentOS</span></span>                         | <span data-ttu-id="c8027-214">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-214">7+</span></span>                    | <span data-ttu-id="c8027-215">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-215">x64</span></span> |
| <span data-ttu-id="c8027-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-216">Oracle Linux</span></span>                   | <span data-ttu-id="c8027-217">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-217">7+</span></span>                    | <span data-ttu-id="c8027-218">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-218">x64</span></span> |
| <span data-ttu-id="c8027-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="c8027-219">Fedora</span></span>                         | <span data-ttu-id="c8027-220">30+</span><span class="sxs-lookup"><span data-stu-id="c8027-220">30+</span></span>                   | <span data-ttu-id="c8027-221">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-221">x64</span></span> |
| <span data-ttu-id="c8027-222">Debian</span><span class="sxs-lookup"><span data-stu-id="c8027-222">Debian</span></span>                         | <span data-ttu-id="c8027-223">9+</span><span class="sxs-lookup"><span data-stu-id="c8027-223">9+</span></span>                    | <span data-ttu-id="c8027-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c8027-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8027-225">Ubuntu</span></span>                         | <span data-ttu-id="c8027-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="c8027-226">16.04+</span></span>                | <span data-ttu-id="c8027-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c8027-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c8027-228">Linux Mint</span></span>                     | <span data-ttu-id="c8027-229">18+</span><span class="sxs-lookup"><span data-stu-id="c8027-229">18+</span></span>                   | <span data-ttu-id="c8027-230">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-230">x64</span></span> |
| <span data-ttu-id="c8027-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c8027-231">openSUSE</span></span>                       | <span data-ttu-id="c8027-232">15+</span><span class="sxs-lookup"><span data-stu-id="c8027-232">15+</span></span>                   | <span data-ttu-id="c8027-233">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-233">x64</span></span> |
| <span data-ttu-id="c8027-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c8027-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c8027-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c8027-235">12 SP2+</span></span>               | <span data-ttu-id="c8027-236">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-236">x64</span></span> |
| <span data-ttu-id="c8027-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-237">Alpine Linux</span></span>                   | <span data-ttu-id="c8027-238">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-238">3.10+</span></span>                 | <span data-ttu-id="c8027-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-239">x64, ARM64</span></span> |

<span data-ttu-id="c8027-240">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="c8027-241">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="c8027-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8027-242">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="c8027-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="c8027-243">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="c8027-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="c8027-244">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="c8027-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="c8027-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="c8027-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="c8027-246">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c8027-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c8027-247">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c8027-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="c8027-248">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="c8027-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c8027-249">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="c8027-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-250">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-251">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-251">OS</span></span>                             | <span data-ttu-id="c8027-252">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-252">Version</span></span>               | <span data-ttu-id="c8027-253">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="c8027-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="c8027-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c8027-255">6, 7, 8</span></span>               | <span data-ttu-id="c8027-256">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-256">x64</span></span> |
| <span data-ttu-id="c8027-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="c8027-257">CentOS</span></span>                         | <span data-ttu-id="c8027-258">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-258">7+</span></span>                    | <span data-ttu-id="c8027-259">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-259">x64</span></span> |
| <span data-ttu-id="c8027-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-260">Oracle Linux</span></span>                   | <span data-ttu-id="c8027-261">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-261">7+</span></span>                    | <span data-ttu-id="c8027-262">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-262">x64</span></span> |
| <span data-ttu-id="c8027-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="c8027-263">Fedora</span></span>                         | <span data-ttu-id="c8027-264">29+</span><span class="sxs-lookup"><span data-stu-id="c8027-264">29+</span></span>                   | <span data-ttu-id="c8027-265">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-265">x64</span></span> |
| <span data-ttu-id="c8027-266">Debian</span><span class="sxs-lookup"><span data-stu-id="c8027-266">Debian</span></span>                         | <span data-ttu-id="c8027-267">9+</span><span class="sxs-lookup"><span data-stu-id="c8027-267">9+</span></span>                    | <span data-ttu-id="c8027-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c8027-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8027-269">Ubuntu</span></span>                         | <span data-ttu-id="c8027-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="c8027-270">16.04+</span></span>                | <span data-ttu-id="c8027-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="c8027-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c8027-272">Linux Mint</span></span>                     | <span data-ttu-id="c8027-273">18+</span><span class="sxs-lookup"><span data-stu-id="c8027-273">18+</span></span>                   | <span data-ttu-id="c8027-274">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-274">x64</span></span> |
| <span data-ttu-id="c8027-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c8027-275">openSUSE</span></span>                       | <span data-ttu-id="c8027-276">15+</span><span class="sxs-lookup"><span data-stu-id="c8027-276">15+</span></span>                   | <span data-ttu-id="c8027-277">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-277">x64</span></span> |
| <span data-ttu-id="c8027-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c8027-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="c8027-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c8027-279">12 SP2+</span></span>               | <span data-ttu-id="c8027-280">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-280">x64</span></span> |
| <span data-ttu-id="c8027-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-281">Alpine Linux</span></span>                   | <span data-ttu-id="c8027-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="c8027-282">3.8+</span></span>                  | <span data-ttu-id="c8027-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="c8027-283">x64, ARM64</span></span> |

<span data-ttu-id="c8027-284">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="c8027-285">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="c8027-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="c8027-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="c8027-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="c8027-287">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="c8027-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="c8027-288">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c8027-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="c8027-289">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="c8027-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c8027-290">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="c8027-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-291">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-292">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-292">OS</span></span>                             |  <span data-ttu-id="c8027-293">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-293">Version</span></span>                |  <span data-ttu-id="c8027-294">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c8027-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c8027-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="c8027-296">6, 7</span></span>                   | <span data-ttu-id="c8027-297">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-297">x64</span></span> |
| <span data-ttu-id="c8027-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="c8027-298">CentOS</span></span>                         |  <span data-ttu-id="c8027-299">7</span><span class="sxs-lookup"><span data-stu-id="c8027-299">7</span></span>                      | <span data-ttu-id="c8027-300">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-300">x64</span></span> |
| <span data-ttu-id="c8027-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-301">Oracle Linux</span></span>                   |  <span data-ttu-id="c8027-302">7</span><span class="sxs-lookup"><span data-stu-id="c8027-302">7</span></span>                      | <span data-ttu-id="c8027-303">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-303">x64</span></span> |
| <span data-ttu-id="c8027-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="c8027-304">Fedora</span></span>                         |  <span data-ttu-id="c8027-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="c8027-305">29, 30</span></span>                 | <span data-ttu-id="c8027-306">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-306">x64</span></span> |
| <span data-ttu-id="c8027-307">Debian</span><span class="sxs-lookup"><span data-stu-id="c8027-307">Debian</span></span>                         |  <span data-ttu-id="c8027-308">9</span><span class="sxs-lookup"><span data-stu-id="c8027-308">9</span></span>                      | <span data-ttu-id="c8027-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-309">x64, ARM32</span></span> |
| <span data-ttu-id="c8027-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8027-310">Ubuntu</span></span>                         |  <span data-ttu-id="c8027-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="c8027-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="c8027-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-312">x64, ARM32</span></span> |
| <span data-ttu-id="c8027-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c8027-313">Linux Mint</span></span>                     |  <span data-ttu-id="c8027-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="c8027-314">17, 18</span></span>                 | <span data-ttu-id="c8027-315">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-315">x64</span></span> |
| <span data-ttu-id="c8027-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c8027-316">openSUSE</span></span>                       |  <span data-ttu-id="c8027-317">15+</span><span class="sxs-lookup"><span data-stu-id="c8027-317">15+</span></span>                    | <span data-ttu-id="c8027-318">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-318">x64</span></span> |
| <span data-ttu-id="c8027-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c8027-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c8027-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c8027-320">12 SP2+</span></span>                | <span data-ttu-id="c8027-321">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-321">x64</span></span> |
| <span data-ttu-id="c8027-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-322">Alpine Linux</span></span>                   |  <span data-ttu-id="c8027-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="c8027-323">3.8+</span></span>                   | <span data-ttu-id="c8027-324">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-324">x64</span></span> |

<span data-ttu-id="c8027-325">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="c8027-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c8027-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="c8027-327">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="c8027-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="c8027-328">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="c8027-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="c8027-329">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="c8027-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-330">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-331">SO</span><span class="sxs-lookup"><span data-stu-id="c8027-331">OS</span></span>                             |  <span data-ttu-id="c8027-332">Versión</span><span class="sxs-lookup"><span data-stu-id="c8027-332">Version</span></span>                |  <span data-ttu-id="c8027-333">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="c8027-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="c8027-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="c8027-335">6, 7, 8</span></span>                | <span data-ttu-id="c8027-336">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-336">x64</span></span> |
| <span data-ttu-id="c8027-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="c8027-337">CentOS</span></span>                         |  <span data-ttu-id="c8027-338">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-338">7+</span></span>                     | <span data-ttu-id="c8027-339">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-339">x64</span></span> |
| <span data-ttu-id="c8027-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-340">Oracle Linux</span></span>                   |  <span data-ttu-id="c8027-341">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="c8027-341">7+</span></span>                     | <span data-ttu-id="c8027-342">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-342">x64</span></span> |
| <span data-ttu-id="c8027-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="c8027-343">Fedora</span></span>                         |  <span data-ttu-id="c8027-344">30+</span><span class="sxs-lookup"><span data-stu-id="c8027-344">30+</span></span>                    | <span data-ttu-id="c8027-345">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-345">x64</span></span> |
| <span data-ttu-id="c8027-346">Debian</span><span class="sxs-lookup"><span data-stu-id="c8027-346">Debian</span></span>                         |  <span data-ttu-id="c8027-347">9</span><span class="sxs-lookup"><span data-stu-id="c8027-347">9</span></span>                      | <span data-ttu-id="c8027-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-348">x64, ARM32</span></span> |
| <span data-ttu-id="c8027-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8027-349">Ubuntu</span></span>                         |  <span data-ttu-id="c8027-350">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="c8027-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="c8027-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="c8027-351">x64, ARM32</span></span> |
| <span data-ttu-id="c8027-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="c8027-352">Linux Mint</span></span>                     |  <span data-ttu-id="c8027-353">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="c8027-353">17+</span></span>                    | <span data-ttu-id="c8027-354">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-354">x64</span></span> |
| <span data-ttu-id="c8027-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c8027-355">openSUSE</span></span>                       |  <span data-ttu-id="c8027-356">15+</span><span class="sxs-lookup"><span data-stu-id="c8027-356">15+</span></span>                    | <span data-ttu-id="c8027-357">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-357">x64</span></span> |
| <span data-ttu-id="c8027-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="c8027-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="c8027-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="c8027-359">12 SP2+</span></span>                | <span data-ttu-id="c8027-360">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-360">x64</span></span> |
| <span data-ttu-id="c8027-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-361">Alpine Linux</span></span>                   |  <span data-ttu-id="c8027-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="c8027-362">3.8+</span></span>                   | <span data-ttu-id="c8027-363">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-363">x64</span></span> |

<span data-ttu-id="c8027-364">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="c8027-365">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="c8027-365">Linux distribution dependencies</span></span>

<span data-ttu-id="c8027-366">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="c8027-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8027-367">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="c8027-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="c8027-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="c8027-368">Ubuntu</span></span>

<span data-ttu-id="c8027-369">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8027-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="c8027-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="c8027-370">liblttng-ust0</span></span>
- <span data-ttu-id="c8027-371">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="c8027-372">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="c8027-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="c8027-373">libssl1.0.0</span></span>
- <span data-ttu-id="c8027-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="c8027-374">libkrb5-3</span></span>
- <span data-ttu-id="c8027-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="c8027-375">zlib1g</span></span>
- <span data-ttu-id="c8027-376">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="c8027-377">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="c8027-378">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="c8027-379">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="c8027-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="c8027-380">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8027-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="c8027-381">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c8027-382">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c8027-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c8027-383">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="c8027-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c8027-384">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c8027-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="c8027-385">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="c8027-385">CentOS and Fedora</span></span>

<span data-ttu-id="c8027-386">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="c8027-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="c8027-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="c8027-387">lttng-ust</span></span>
- <span data-ttu-id="c8027-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="c8027-388">libcurl</span></span>
- <span data-ttu-id="c8027-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="c8027-389">openssl-libs</span></span>
- <span data-ttu-id="c8027-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="c8027-390">krb5-libs</span></span>
- <span data-ttu-id="c8027-391">libicu</span><span class="sxs-lookup"><span data-stu-id="c8027-391">libicu</span></span>
- <span data-ttu-id="c8027-392">zlib</span><span class="sxs-lookup"><span data-stu-id="c8027-392">zlib</span></span>

<span data-ttu-id="c8027-393">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="c8027-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="c8027-394">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="c8027-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="c8027-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="c8027-395">libunwind</span></span>
- <span data-ttu-id="c8027-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="c8027-396">libuuid</span></span>

<span data-ttu-id="c8027-397">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c8027-398">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8027-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="c8027-399">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="c8027-400">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c8027-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="c8027-401">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="c8027-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="c8027-402">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="c8027-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="c8027-403">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="c8027-403">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="c8027-404">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="c8027-404">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="c8027-405">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="c8027-405">.NET Core Version</span></span> | <span data-ttu-id="c8027-406">macOS</span><span class="sxs-lookup"><span data-stu-id="c8027-406">macOS</span></span>                 | <span data-ttu-id="c8027-407">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="c8027-407">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="c8027-408">3.1</span><span class="sxs-lookup"><span data-stu-id="c8027-408">3.1</span></span>               | <span data-ttu-id="c8027-409">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-409">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c8027-410">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-410">x64</span></span> | [<span data-ttu-id="c8027-411">Más información</span><span class="sxs-lookup"><span data-stu-id="c8027-411">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="c8027-412">3.0</span><span class="sxs-lookup"><span data-stu-id="c8027-412">3.0</span></span>               | <span data-ttu-id="c8027-413">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-413">High Sierra (10.13+)</span></span>  | <span data-ttu-id="c8027-414">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-414">x64</span></span> | [<span data-ttu-id="c8027-415">Más información</span><span class="sxs-lookup"><span data-stu-id="c8027-415">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="c8027-416">2.2</span><span class="sxs-lookup"><span data-stu-id="c8027-416">2.2</span></span>               | <span data-ttu-id="c8027-417">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-417">Sierra (10.12+)</span></span>       | <span data-ttu-id="c8027-418">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-418">x64</span></span> | [<span data-ttu-id="c8027-419">Más información</span><span class="sxs-lookup"><span data-stu-id="c8027-419">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="c8027-420">2.1</span><span class="sxs-lookup"><span data-stu-id="c8027-420">2.1</span></span>               | <span data-ttu-id="c8027-421">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="c8027-421">Sierra (10.12+)</span></span>       | <span data-ttu-id="c8027-422">x64</span><span class="sxs-lookup"><span data-stu-id="c8027-422">x64</span></span> | [<span data-ttu-id="c8027-423">Más información</span><span class="sxs-lookup"><span data-stu-id="c8027-423">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="c8027-424">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="c8027-424">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="c8027-425">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="c8027-425">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="c8027-426">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="c8027-426">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="c8027-427">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="c8027-427">Prior released versions aren't notarized.</span></span> <span data-ttu-id="c8027-428">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="c8027-428">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="c8027-430">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-430">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="c8027-431">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="c8027-431">libgdiplus</span></span>

<span data-ttu-id="c8027-432">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="c8027-432">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="c8027-433">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="c8027-433">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="c8027-434">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="c8027-434">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="c8027-435">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="c8027-435">Next steps</span></span>

- <span data-ttu-id="c8027-436">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="c8027-436">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="c8027-437">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="c8027-437">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
