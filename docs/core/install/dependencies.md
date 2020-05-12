---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 04/30/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 280aa1431686ff99257580bb024a84b1e57f85c0
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895486"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="1f062-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1f062-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="1f062-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f062-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="1f062-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="1f062-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="1f062-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1f062-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1f062-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="1f062-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-109">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-109">OS</span></span>                            | <span data-ttu-id="1f062-110">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-110">Version</span></span>                        | <span data-ttu-id="1f062-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1f062-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="1f062-112">Windows Client</span></span>                | <span data-ttu-id="1f062-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="1f062-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1f062-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-114">x64, x86</span></span>        |
| <span data-ttu-id="1f062-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f062-115">Windows 10 Client</span></span>             | <span data-ttu-id="1f062-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-116">Version 1607+</span></span>                  | <span data-ttu-id="1f062-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-117">x64, x86</span></span>        |
| <span data-ttu-id="1f062-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1f062-118">Windows Server</span></span>                | <span data-ttu-id="1f062-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-119">2012 R2+</span></span>                       | <span data-ttu-id="1f062-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-120">x64, x86</span></span>        |
| <span data-ttu-id="1f062-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1f062-121">Nano Server</span></span>                   | <span data-ttu-id="1f062-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-122">Version 1803+</span></span>                  | <span data-ttu-id="1f062-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-123">x64, ARM32</span></span>      |

<span data-ttu-id="1f062-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1f062-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1f062-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1f062-126">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1f062-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1f062-127">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="1f062-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-128">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-129">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-129">OS</span></span>                            | <span data-ttu-id="1f062-130">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-130">Version</span></span>                        | <span data-ttu-id="1f062-131">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1f062-132">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="1f062-132">Windows Client</span></span>                | <span data-ttu-id="1f062-133">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="1f062-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1f062-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-134">x64, x86</span></span>        |
| <span data-ttu-id="1f062-135">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f062-135">Windows 10 Client</span></span>             | <span data-ttu-id="1f062-136">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-136">Version 1607+</span></span>                  | <span data-ttu-id="1f062-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-137">x64, x86</span></span>        |
| <span data-ttu-id="1f062-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1f062-138">Windows Server</span></span>                | <span data-ttu-id="1f062-139">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-139">2012 R2+</span></span>                       | <span data-ttu-id="1f062-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-140">x64, x86</span></span>        |
| <span data-ttu-id="1f062-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1f062-141">Nano Server</span></span>                   | <span data-ttu-id="1f062-142">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-142">Version 1803+</span></span>                  | <span data-ttu-id="1f062-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-143">x64, ARM32</span></span>      |

<span data-ttu-id="1f062-144">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1f062-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1f062-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1f062-146">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1f062-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1f062-147">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="1f062-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-148">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-149">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-149">OS</span></span>                            | <span data-ttu-id="1f062-150">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-150">Version</span></span>                        | <span data-ttu-id="1f062-151">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1f062-152">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="1f062-152">Windows Client</span></span>                | <span data-ttu-id="1f062-153">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="1f062-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1f062-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-154">x64, x86</span></span>        |
| <span data-ttu-id="1f062-155">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f062-155">Windows 10 Client</span></span>             | <span data-ttu-id="1f062-156">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-156">Version 1607+</span></span>                  | <span data-ttu-id="1f062-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-157">x64, x86</span></span>        |
| <span data-ttu-id="1f062-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1f062-158">Windows Server</span></span>                | <span data-ttu-id="1f062-159">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1f062-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-160">x64, x86</span></span>        |
| <span data-ttu-id="1f062-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1f062-161">Nano Server</span></span>                   | <span data-ttu-id="1f062-162">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-162">Version 1803+</span></span>                   | <span data-ttu-id="1f062-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-163">x64, ARM32</span></span>      |

<span data-ttu-id="1f062-164">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1f062-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1f062-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1f062-166">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="1f062-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-167">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-168">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-168">OS</span></span>                            | <span data-ttu-id="1f062-169">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-169">Version</span></span>                        | <span data-ttu-id="1f062-170">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="1f062-171">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="1f062-171">Windows Client</span></span>                | <span data-ttu-id="1f062-172">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="1f062-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="1f062-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-173">x64, x86</span></span>        |
| <span data-ttu-id="1f062-174">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="1f062-174">Windows 10 Client</span></span>             | <span data-ttu-id="1f062-175">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-175">Version 1607+</span></span>                  | <span data-ttu-id="1f062-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-176">x64, x86</span></span>        |
| <span data-ttu-id="1f062-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="1f062-177">Windows Server</span></span>                | <span data-ttu-id="1f062-178">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="1f062-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="1f062-179">x64, x86</span></span>        |
| <span data-ttu-id="1f062-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="1f062-180">Nano Server</span></span>                   | <span data-ttu-id="1f062-181">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-181">Version 1803+</span></span>                  | <span data-ttu-id="1f062-182">x64,</span><span class="sxs-lookup"><span data-stu-id="1f062-182">x64,</span></span>            |

<span data-ttu-id="1f062-183">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="1f062-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1f062-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="1f062-185">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="1f062-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="1f062-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="1f062-186">Windows 7 SP1</span></span>
- <span data-ttu-id="1f062-187">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="1f062-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="1f062-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="1f062-188">Windows 8.1</span></span>
- <span data-ttu-id="1f062-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="1f062-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="1f062-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="1f062-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="1f062-191">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f062-191">Install the following:</span></span>

- <span data-ttu-id="1f062-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="1f062-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="1f062-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="1f062-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="1f062-194">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f062-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="1f062-195">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1f062-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1f062-196">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="1f062-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1f062-197">\- o -</span><span class="sxs-lookup"><span data-stu-id="1f062-197">\- or -</span></span>
>
> <span data-ttu-id="1f062-198">El programa no se puede iniciar porque falta el archivo *api-ms-win-cor-timezone-l1-1-0.dll* en el equipo.</span><span class="sxs-lookup"><span data-stu-id="1f062-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="1f062-199">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="1f062-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="1f062-200">\- o -</span><span class="sxs-lookup"><span data-stu-id="1f062-200">\- or -</span></span>
>
> <span data-ttu-id="1f062-201">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="1f062-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="1f062-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="1f062-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="1f062-203">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f062-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1f062-204">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="1f062-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1f062-205">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="1f062-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-206">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-207">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-207">OS</span></span>                             | <span data-ttu-id="1f062-208">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-208">Version</span></span>               | <span data-ttu-id="1f062-209">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1f062-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1f062-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1f062-211">6, 7, 8</span></span>               | <span data-ttu-id="1f062-212">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-212">x64</span></span> |
| <span data-ttu-id="1f062-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="1f062-213">CentOS</span></span>                         | <span data-ttu-id="1f062-214">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-214">7+</span></span>                    | <span data-ttu-id="1f062-215">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-215">x64</span></span> |
| <span data-ttu-id="1f062-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-216">Oracle Linux</span></span>                   | <span data-ttu-id="1f062-217">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-217">7+</span></span>                    | <span data-ttu-id="1f062-218">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-218">x64</span></span> |
| <span data-ttu-id="1f062-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="1f062-219">Fedora</span></span>                         | <span data-ttu-id="1f062-220">30+</span><span class="sxs-lookup"><span data-stu-id="1f062-220">30+</span></span>                   | <span data-ttu-id="1f062-221">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-221">x64</span></span> |
| <span data-ttu-id="1f062-222">Debian</span><span class="sxs-lookup"><span data-stu-id="1f062-222">Debian</span></span>                         | <span data-ttu-id="1f062-223">9+</span><span class="sxs-lookup"><span data-stu-id="1f062-223">9+</span></span>                    | <span data-ttu-id="1f062-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1f062-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1f062-225">Ubuntu</span></span>                         | <span data-ttu-id="1f062-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="1f062-226">16.04+</span></span>                | <span data-ttu-id="1f062-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1f062-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1f062-228">Linux Mint</span></span>                     | <span data-ttu-id="1f062-229">18+</span><span class="sxs-lookup"><span data-stu-id="1f062-229">18+</span></span>                   | <span data-ttu-id="1f062-230">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-230">x64</span></span> |
| <span data-ttu-id="1f062-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1f062-231">openSUSE</span></span>                       | <span data-ttu-id="1f062-232">15+</span><span class="sxs-lookup"><span data-stu-id="1f062-232">15+</span></span>                   | <span data-ttu-id="1f062-233">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-233">x64</span></span> |
| <span data-ttu-id="1f062-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1f062-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1f062-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1f062-235">12 SP2+</span></span>               | <span data-ttu-id="1f062-236">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-236">x64</span></span> |
| <span data-ttu-id="1f062-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-237">Alpine Linux</span></span>                   | <span data-ttu-id="1f062-238">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-238">3.10+</span></span>                 | <span data-ttu-id="1f062-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-239">x64, ARM64</span></span> |

<span data-ttu-id="1f062-240">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="1f062-241">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="1f062-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f062-242">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="1f062-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="1f062-243">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="1f062-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="1f062-244">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="1f062-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="1f062-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="1f062-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="1f062-246">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1f062-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1f062-247">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f062-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="1f062-248">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="1f062-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1f062-249">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="1f062-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-250">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-251">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-251">OS</span></span>                             | <span data-ttu-id="1f062-252">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-252">Version</span></span>               | <span data-ttu-id="1f062-253">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="1f062-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="1f062-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1f062-255">6, 7, 8</span></span>               | <span data-ttu-id="1f062-256">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-256">x64</span></span> |
| <span data-ttu-id="1f062-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="1f062-257">CentOS</span></span>                         | <span data-ttu-id="1f062-258">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-258">7+</span></span>                    | <span data-ttu-id="1f062-259">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-259">x64</span></span> |
| <span data-ttu-id="1f062-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-260">Oracle Linux</span></span>                   | <span data-ttu-id="1f062-261">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-261">7+</span></span>                    | <span data-ttu-id="1f062-262">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-262">x64</span></span> |
| <span data-ttu-id="1f062-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="1f062-263">Fedora</span></span>                         | <span data-ttu-id="1f062-264">29+</span><span class="sxs-lookup"><span data-stu-id="1f062-264">29+</span></span>                   | <span data-ttu-id="1f062-265">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-265">x64</span></span> |
| <span data-ttu-id="1f062-266">Debian</span><span class="sxs-lookup"><span data-stu-id="1f062-266">Debian</span></span>                         | <span data-ttu-id="1f062-267">9+</span><span class="sxs-lookup"><span data-stu-id="1f062-267">9+</span></span>                    | <span data-ttu-id="1f062-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1f062-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1f062-269">Ubuntu</span></span>                         | <span data-ttu-id="1f062-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="1f062-270">16.04+</span></span>                | <span data-ttu-id="1f062-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="1f062-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1f062-272">Linux Mint</span></span>                     | <span data-ttu-id="1f062-273">18+</span><span class="sxs-lookup"><span data-stu-id="1f062-273">18+</span></span>                   | <span data-ttu-id="1f062-274">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-274">x64</span></span> |
| <span data-ttu-id="1f062-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1f062-275">openSUSE</span></span>                       | <span data-ttu-id="1f062-276">15+</span><span class="sxs-lookup"><span data-stu-id="1f062-276">15+</span></span>                   | <span data-ttu-id="1f062-277">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-277">x64</span></span> |
| <span data-ttu-id="1f062-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1f062-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="1f062-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1f062-279">12 SP2+</span></span>               | <span data-ttu-id="1f062-280">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-280">x64</span></span> |
| <span data-ttu-id="1f062-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-281">Alpine Linux</span></span>                   | <span data-ttu-id="1f062-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="1f062-282">3.8+</span></span>                  | <span data-ttu-id="1f062-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="1f062-283">x64, ARM64</span></span> |

<span data-ttu-id="1f062-284">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="1f062-285">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="1f062-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="1f062-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="1f062-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="1f062-287">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="1f062-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="1f062-288">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f062-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="1f062-289">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="1f062-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1f062-290">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="1f062-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-291">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-292">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-292">OS</span></span>                             |  <span data-ttu-id="1f062-293">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-293">Version</span></span>                |  <span data-ttu-id="1f062-294">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1f062-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1f062-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="1f062-296">6, 7</span></span>                   | <span data-ttu-id="1f062-297">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-297">x64</span></span> |
| <span data-ttu-id="1f062-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="1f062-298">CentOS</span></span>                         |  <span data-ttu-id="1f062-299">7</span><span class="sxs-lookup"><span data-stu-id="1f062-299">7</span></span>                      | <span data-ttu-id="1f062-300">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-300">x64</span></span> |
| <span data-ttu-id="1f062-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-301">Oracle Linux</span></span>                   |  <span data-ttu-id="1f062-302">7</span><span class="sxs-lookup"><span data-stu-id="1f062-302">7</span></span>                      | <span data-ttu-id="1f062-303">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-303">x64</span></span> |
| <span data-ttu-id="1f062-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="1f062-304">Fedora</span></span>                         |  <span data-ttu-id="1f062-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="1f062-305">29, 30</span></span>                 | <span data-ttu-id="1f062-306">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-306">x64</span></span> |
| <span data-ttu-id="1f062-307">Debian</span><span class="sxs-lookup"><span data-stu-id="1f062-307">Debian</span></span>                         |  <span data-ttu-id="1f062-308">9</span><span class="sxs-lookup"><span data-stu-id="1f062-308">9</span></span>                      | <span data-ttu-id="1f062-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-309">x64, ARM32</span></span> |
| <span data-ttu-id="1f062-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1f062-310">Ubuntu</span></span>                         |  <span data-ttu-id="1f062-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="1f062-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="1f062-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-312">x64, ARM32</span></span> |
| <span data-ttu-id="1f062-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1f062-313">Linux Mint</span></span>                     |  <span data-ttu-id="1f062-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="1f062-314">17, 18</span></span>                 | <span data-ttu-id="1f062-315">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-315">x64</span></span> |
| <span data-ttu-id="1f062-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1f062-316">openSUSE</span></span>                       |  <span data-ttu-id="1f062-317">15+</span><span class="sxs-lookup"><span data-stu-id="1f062-317">15+</span></span>                    | <span data-ttu-id="1f062-318">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-318">x64</span></span> |
| <span data-ttu-id="1f062-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1f062-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1f062-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1f062-320">12 SP2+</span></span>                | <span data-ttu-id="1f062-321">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-321">x64</span></span> |
| <span data-ttu-id="1f062-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-322">Alpine Linux</span></span>                   |  <span data-ttu-id="1f062-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="1f062-323">3.8+</span></span>                   | <span data-ttu-id="1f062-324">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-324">x64</span></span> |

<span data-ttu-id="1f062-325">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="1f062-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="1f062-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="1f062-327">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="1f062-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="1f062-328">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="1f062-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="1f062-329">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="1f062-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-330">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-331">SO</span><span class="sxs-lookup"><span data-stu-id="1f062-331">OS</span></span>                             |  <span data-ttu-id="1f062-332">Versión</span><span class="sxs-lookup"><span data-stu-id="1f062-332">Version</span></span>                |  <span data-ttu-id="1f062-333">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="1f062-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="1f062-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="1f062-335">6, 7, 8</span></span>                | <span data-ttu-id="1f062-336">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-336">x64</span></span> |
| <span data-ttu-id="1f062-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="1f062-337">CentOS</span></span>                         |  <span data-ttu-id="1f062-338">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-338">7+</span></span>                     | <span data-ttu-id="1f062-339">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-339">x64</span></span> |
| <span data-ttu-id="1f062-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-340">Oracle Linux</span></span>                   |  <span data-ttu-id="1f062-341">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="1f062-341">7+</span></span>                     | <span data-ttu-id="1f062-342">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-342">x64</span></span> |
| <span data-ttu-id="1f062-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="1f062-343">Fedora</span></span>                         |  <span data-ttu-id="1f062-344">30+</span><span class="sxs-lookup"><span data-stu-id="1f062-344">30+</span></span>                    | <span data-ttu-id="1f062-345">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-345">x64</span></span> |
| <span data-ttu-id="1f062-346">Debian</span><span class="sxs-lookup"><span data-stu-id="1f062-346">Debian</span></span>                         |  <span data-ttu-id="1f062-347">9</span><span class="sxs-lookup"><span data-stu-id="1f062-347">9</span></span>                      | <span data-ttu-id="1f062-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-348">x64, ARM32</span></span> |
| <span data-ttu-id="1f062-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1f062-349">Ubuntu</span></span>                         |  <span data-ttu-id="1f062-350">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="1f062-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="1f062-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="1f062-351">x64, ARM32</span></span> |
| <span data-ttu-id="1f062-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="1f062-352">Linux Mint</span></span>                     |  <span data-ttu-id="1f062-353">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="1f062-353">17+</span></span>                    | <span data-ttu-id="1f062-354">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-354">x64</span></span> |
| <span data-ttu-id="1f062-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="1f062-355">openSUSE</span></span>                       |  <span data-ttu-id="1f062-356">15+</span><span class="sxs-lookup"><span data-stu-id="1f062-356">15+</span></span>                    | <span data-ttu-id="1f062-357">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-357">x64</span></span> |
| <span data-ttu-id="1f062-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="1f062-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="1f062-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="1f062-359">12 SP2+</span></span>                | <span data-ttu-id="1f062-360">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-360">x64</span></span> |
| <span data-ttu-id="1f062-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-361">Alpine Linux</span></span>                   |  <span data-ttu-id="1f062-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="1f062-362">3.8+</span></span>                   | <span data-ttu-id="1f062-363">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-363">x64</span></span> |

<span data-ttu-id="1f062-364">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="1f062-365">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="1f062-365">Linux distribution dependencies</span></span>

<span data-ttu-id="1f062-366">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="1f062-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f062-367">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="1f062-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="1f062-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="1f062-368">Ubuntu</span></span>

<span data-ttu-id="1f062-369">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f062-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1f062-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="1f062-370">liblttng-ust0</span></span>
- <span data-ttu-id="1f062-371">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="1f062-372">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="1f062-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="1f062-373">libssl1.0.0</span></span>
- <span data-ttu-id="1f062-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="1f062-374">libkrb5-3</span></span>
- <span data-ttu-id="1f062-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="1f062-375">zlib1g</span></span>
- <span data-ttu-id="1f062-376">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="1f062-377">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="1f062-378">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="1f062-379">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="1f062-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="1f062-380">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f062-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1f062-381">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1f062-382">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="1f062-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1f062-383">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="1f062-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1f062-384">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="1f062-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="1f062-385">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="1f062-385">CentOS and Fedora</span></span>

<span data-ttu-id="1f062-386">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="1f062-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="1f062-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1f062-387">lttng-ust</span></span>
- <span data-ttu-id="1f062-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="1f062-388">libcurl</span></span>
- <span data-ttu-id="1f062-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="1f062-389">openssl-libs</span></span>
- <span data-ttu-id="1f062-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1f062-390">krb5-libs</span></span>
- <span data-ttu-id="1f062-391">libicu</span><span class="sxs-lookup"><span data-stu-id="1f062-391">libicu</span></span>
- <span data-ttu-id="1f062-392">zlib</span><span class="sxs-lookup"><span data-stu-id="1f062-392">zlib</span></span>

<span data-ttu-id="1f062-393">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="1f062-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="1f062-394">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f062-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="1f062-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="1f062-395">libunwind</span></span>
- <span data-ttu-id="1f062-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="1f062-396">libuuid</span></span>

<span data-ttu-id="1f062-397">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="1f062-398">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f062-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="1f062-399">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="1f062-400">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="1f062-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="1f062-401">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="1f062-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="1f062-402">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="1f062-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="1f062-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="1f062-403">Alpine</span></span>

<span data-ttu-id="1f062-404">Las distribuciones de Alpine necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1f062-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="1f062-405">icu-libs (esto no es necesario si la globalización está deshabilitada)</span><span class="sxs-lookup"><span data-stu-id="1f062-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="1f062-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="1f062-406">krb5-libs</span></span>
- <span data-ttu-id="1f062-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="1f062-407">libcurl</span></span>
- <span data-ttu-id="1f062-408">libintl</span><span class="sxs-lookup"><span data-stu-id="1f062-408">libintl</span></span>
- <span data-ttu-id="1f062-409">libssl1.1 (para Alpine 3.9 o una versión posterior) o libssl1.0 (para versiones anteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="1f062-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="1f062-410">libstdc++</span></span>
- <span data-ttu-id="1f062-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="1f062-411">lttng-ust</span></span>
- <span data-ttu-id="1f062-412">numactl (opcional, útil solo para dispositivos con NUMA habilitado)</span><span class="sxs-lookup"><span data-stu-id="1f062-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="1f062-413">zlib</span><span class="sxs-lookup"><span data-stu-id="1f062-413">zlib</span></span>

<span data-ttu-id="1f062-414">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f062-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="1f062-415">libgdiplus (solo está disponible en el repositorio Edge/Testing)</span><span class="sxs-lookup"><span data-stu-id="1f062-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="1f062-416">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="1f062-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="1f062-417">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="1f062-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="1f062-418">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="1f062-418">.NET Core Version</span></span> | <span data-ttu-id="1f062-419">macOS</span><span class="sxs-lookup"><span data-stu-id="1f062-419">macOS</span></span>                 | <span data-ttu-id="1f062-420">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="1f062-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="1f062-421">3.1</span><span class="sxs-lookup"><span data-stu-id="1f062-421">3.1</span></span>               | <span data-ttu-id="1f062-422">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1f062-423">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-423">x64</span></span> | [<span data-ttu-id="1f062-424">Más información</span><span class="sxs-lookup"><span data-stu-id="1f062-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="1f062-425">3.0</span><span class="sxs-lookup"><span data-stu-id="1f062-425">3.0</span></span>               | <span data-ttu-id="1f062-426">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="1f062-427">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-427">x64</span></span> | [<span data-ttu-id="1f062-428">Más información</span><span class="sxs-lookup"><span data-stu-id="1f062-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="1f062-429">2.2</span><span class="sxs-lookup"><span data-stu-id="1f062-429">2.2</span></span>               | <span data-ttu-id="1f062-430">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="1f062-431">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-431">x64</span></span> | [<span data-ttu-id="1f062-432">Más información</span><span class="sxs-lookup"><span data-stu-id="1f062-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="1f062-433">2.1</span><span class="sxs-lookup"><span data-stu-id="1f062-433">2.1</span></span>               | <span data-ttu-id="1f062-434">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="1f062-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="1f062-435">x64</span><span class="sxs-lookup"><span data-stu-id="1f062-435">x64</span></span> | [<span data-ttu-id="1f062-436">Más información</span><span class="sxs-lookup"><span data-stu-id="1f062-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="1f062-437">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="1f062-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="1f062-438">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="1f062-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="1f062-439">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="1f062-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="1f062-440">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="1f062-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="1f062-441">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="1f062-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="1f062-443">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="1f062-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="1f062-444">libgdiplus</span></span>

<span data-ttu-id="1f062-445">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="1f062-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="1f062-446">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="1f062-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="1f062-447">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="1f062-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="1f062-448">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="1f062-448">Next steps</span></span>

- <span data-ttu-id="1f062-449">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1f062-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="1f062-450">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="1f062-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
