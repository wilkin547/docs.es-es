---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 06/01/2020
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 81f6ab436428d71f71d9fd0f560bd2b0512a519b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/09/2020
ms.locfileid: "84590765"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="5fa50-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5fa50-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="5fa50-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5fa50-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="5fa50-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="5fa50-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="5fa50-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="5fa50-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="5fa50-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-109">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-109">OS</span></span>                            | <span data-ttu-id="5fa50-110">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-110">Version</span></span>                        | <span data-ttu-id="5fa50-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="5fa50-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="5fa50-112">Windows Client</span></span>                | <span data-ttu-id="5fa50-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="5fa50-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-114">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="5fa50-115">Windows 10 Client</span></span>             | <span data-ttu-id="5fa50-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-116">Version 1607+</span></span>                  | <span data-ttu-id="5fa50-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-117">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-118">Windows Server</span></span>                | <span data-ttu-id="5fa50-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-119">2012 R2+</span></span>                       | <span data-ttu-id="5fa50-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-120">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-121">Nano Server</span></span>                   | <span data-ttu-id="5fa50-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-122">Version 1803+</span></span>                  | <span data-ttu-id="5fa50-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-123">x64, ARM32</span></span>      |

<span data-ttu-id="5fa50-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="5fa50-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5fa50-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="5fa50-126">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="5fa50-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="5fa50-127">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="5fa50-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-128">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-129">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-129">OS</span></span>                            | <span data-ttu-id="5fa50-130">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-130">Version</span></span>                        | <span data-ttu-id="5fa50-131">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="5fa50-132">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="5fa50-132">Windows Client</span></span>                | <span data-ttu-id="5fa50-133">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="5fa50-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-134">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-135">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="5fa50-135">Windows 10 Client</span></span>             | <span data-ttu-id="5fa50-136">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-136">Version 1607+</span></span>                  | <span data-ttu-id="5fa50-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-137">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-138">Windows Server</span></span>                | <span data-ttu-id="5fa50-139">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-139">2012 R2+</span></span>                       | <span data-ttu-id="5fa50-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-140">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-141">Nano Server</span></span>                   | <span data-ttu-id="5fa50-142">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-142">Version 1803+</span></span>                  | <span data-ttu-id="5fa50-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-143">x64, ARM32</span></span>      |

<span data-ttu-id="5fa50-144">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="5fa50-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5fa50-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="5fa50-146">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="5fa50-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="5fa50-147">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="5fa50-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-148">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-149">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-149">OS</span></span>                            | <span data-ttu-id="5fa50-150">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-150">Version</span></span>                        | <span data-ttu-id="5fa50-151">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="5fa50-152">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="5fa50-152">Windows Client</span></span>                | <span data-ttu-id="5fa50-153">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="5fa50-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-154">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-155">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="5fa50-155">Windows 10 Client</span></span>             | <span data-ttu-id="5fa50-156">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-156">Version 1607+</span></span>                  | <span data-ttu-id="5fa50-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-157">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-158">Windows Server</span></span>                | <span data-ttu-id="5fa50-159">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="5fa50-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-160">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-161">Nano Server</span></span>                   | <span data-ttu-id="5fa50-162">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-162">Version 1803+</span></span>                   | <span data-ttu-id="5fa50-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-163">x64, ARM32</span></span>      |

<span data-ttu-id="5fa50-164">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="5fa50-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5fa50-166">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="5fa50-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-167">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-168">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-168">OS</span></span>                            | <span data-ttu-id="5fa50-169">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-169">Version</span></span>                        | <span data-ttu-id="5fa50-170">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="5fa50-171">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="5fa50-171">Windows Client</span></span>                | <span data-ttu-id="5fa50-172">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="5fa50-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-173">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-174">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="5fa50-174">Windows 10 Client</span></span>             | <span data-ttu-id="5fa50-175">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-175">Version 1607+</span></span>                  | <span data-ttu-id="5fa50-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-176">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-177">Windows Server</span></span>                | <span data-ttu-id="5fa50-178">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="5fa50-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="5fa50-179">x64, x86</span></span>        |
| <span data-ttu-id="5fa50-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="5fa50-180">Nano Server</span></span>                   | <span data-ttu-id="5fa50-181">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-181">Version 1803+</span></span>                  | <span data-ttu-id="5fa50-182">x64,</span><span class="sxs-lookup"><span data-stu-id="5fa50-182">x64,</span></span>            |

<span data-ttu-id="5fa50-183">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="5fa50-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5fa50-184">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="5fa50-185">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="5fa50-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="5fa50-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="5fa50-186">Windows 7 SP1</span></span>
- <span data-ttu-id="5fa50-187">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="5fa50-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="5fa50-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-188">Windows 8.1</span></span>
- <span data-ttu-id="5fa50-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5fa50-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="5fa50-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5fa50-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="5fa50-191">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fa50-191">Install the following:</span></span>

- <span data-ttu-id="5fa50-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="5fa50-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="5fa50-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="5fa50-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="5fa50-194">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fa50-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="5fa50-195">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="5fa50-196">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="5fa50-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="5fa50-197">\- o -</span><span class="sxs-lookup"><span data-stu-id="5fa50-197">\- or -</span></span>
>
> <span data-ttu-id="5fa50-198">El programa no se puede iniciar porque falta el archivo *api-ms-win-cor-timezone-l1-1-0.dll* en el equipo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-198">The program can't start because *api-ms-win-cor-timezone-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="5fa50-199">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="5fa50-199">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="5fa50-200">\- o -</span><span class="sxs-lookup"><span data-stu-id="5fa50-200">\- or -</span></span>
>
> <span data-ttu-id="5fa50-201">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="5fa50-201">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="5fa50-202">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-202">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="5fa50-203">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-203">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="5fa50-204">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="5fa50-204">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="5fa50-205">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="5fa50-205">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-206">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-206">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-207">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-207">OS</span></span>                             | <span data-ttu-id="5fa50-208">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-208">Version</span></span>               | <span data-ttu-id="5fa50-209">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-209">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="5fa50-210">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-210">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="5fa50-211">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="5fa50-211">6, 7, 8</span></span>               | <span data-ttu-id="5fa50-212">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-212">x64</span></span> |
| <span data-ttu-id="5fa50-213">CentOS</span><span class="sxs-lookup"><span data-stu-id="5fa50-213">CentOS</span></span>                         | <span data-ttu-id="5fa50-214">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-214">7+</span></span>                    | <span data-ttu-id="5fa50-215">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-215">x64</span></span> |
| <span data-ttu-id="5fa50-216">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-216">Oracle Linux</span></span>                   | <span data-ttu-id="5fa50-217">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-217">7+</span></span>                    | <span data-ttu-id="5fa50-218">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-218">x64</span></span> |
| <span data-ttu-id="5fa50-219">Fedora</span><span class="sxs-lookup"><span data-stu-id="5fa50-219">Fedora</span></span>                         | <span data-ttu-id="5fa50-220">30+</span><span class="sxs-lookup"><span data-stu-id="5fa50-220">30+</span></span>                   | <span data-ttu-id="5fa50-221">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-221">x64</span></span> |
| <span data-ttu-id="5fa50-222">Debian</span><span class="sxs-lookup"><span data-stu-id="5fa50-222">Debian</span></span>                         | <span data-ttu-id="5fa50-223">9+</span><span class="sxs-lookup"><span data-stu-id="5fa50-223">9+</span></span>                    | <span data-ttu-id="5fa50-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="5fa50-225">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5fa50-225">Ubuntu</span></span>                         | <span data-ttu-id="5fa50-226">16.04+</span><span class="sxs-lookup"><span data-stu-id="5fa50-226">16.04+</span></span>                | <span data-ttu-id="5fa50-227">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-227">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="5fa50-228">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="5fa50-228">Linux Mint</span></span>                     | <span data-ttu-id="5fa50-229">18+</span><span class="sxs-lookup"><span data-stu-id="5fa50-229">18+</span></span>                   | <span data-ttu-id="5fa50-230">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-230">x64</span></span> |
| <span data-ttu-id="5fa50-231">openSUSE</span><span class="sxs-lookup"><span data-stu-id="5fa50-231">openSUSE</span></span>                       | <span data-ttu-id="5fa50-232">15+</span><span class="sxs-lookup"><span data-stu-id="5fa50-232">15+</span></span>                   | <span data-ttu-id="5fa50-233">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-233">x64</span></span> |
| <span data-ttu-id="5fa50-234">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="5fa50-234">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="5fa50-235">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="5fa50-235">12 SP2+</span></span>               | <span data-ttu-id="5fa50-236">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-236">x64</span></span> |
| <span data-ttu-id="5fa50-237">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-237">Alpine Linux</span></span>                   | <span data-ttu-id="5fa50-238">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-238">3.10+</span></span>                 | <span data-ttu-id="5fa50-239">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-239">x64, ARM64</span></span> |

<span data-ttu-id="5fa50-240">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-240">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="5fa50-241">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="5fa50-241">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fa50-242">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="5fa50-242">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="5fa50-243">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="5fa50-243">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="5fa50-244">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="5fa50-244">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="5fa50-245">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5fa50-245">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="5fa50-246">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="5fa50-246">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="5fa50-247">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-247">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="5fa50-248">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="5fa50-248">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="5fa50-249">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="5fa50-249">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-250">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-251">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-251">OS</span></span>                             | <span data-ttu-id="5fa50-252">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-252">Version</span></span>               | <span data-ttu-id="5fa50-253">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-253">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="5fa50-254">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-254">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="5fa50-255">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="5fa50-255">6, 7, 8</span></span>               | <span data-ttu-id="5fa50-256">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-256">x64</span></span> |
| <span data-ttu-id="5fa50-257">CentOS</span><span class="sxs-lookup"><span data-stu-id="5fa50-257">CentOS</span></span>                         | <span data-ttu-id="5fa50-258">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-258">7+</span></span>                    | <span data-ttu-id="5fa50-259">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-259">x64</span></span> |
| <span data-ttu-id="5fa50-260">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-260">Oracle Linux</span></span>                   | <span data-ttu-id="5fa50-261">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-261">7+</span></span>                    | <span data-ttu-id="5fa50-262">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-262">x64</span></span> |
| <span data-ttu-id="5fa50-263">Fedora</span><span class="sxs-lookup"><span data-stu-id="5fa50-263">Fedora</span></span>                         | <span data-ttu-id="5fa50-264">29+</span><span class="sxs-lookup"><span data-stu-id="5fa50-264">29+</span></span>                   | <span data-ttu-id="5fa50-265">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-265">x64</span></span> |
| <span data-ttu-id="5fa50-266">Debian</span><span class="sxs-lookup"><span data-stu-id="5fa50-266">Debian</span></span>                         | <span data-ttu-id="5fa50-267">9+</span><span class="sxs-lookup"><span data-stu-id="5fa50-267">9+</span></span>                    | <span data-ttu-id="5fa50-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="5fa50-269">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5fa50-269">Ubuntu</span></span>                         | <span data-ttu-id="5fa50-270">16.04+</span><span class="sxs-lookup"><span data-stu-id="5fa50-270">16.04+</span></span>                | <span data-ttu-id="5fa50-271">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-271">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="5fa50-272">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="5fa50-272">Linux Mint</span></span>                     | <span data-ttu-id="5fa50-273">18+</span><span class="sxs-lookup"><span data-stu-id="5fa50-273">18+</span></span>                   | <span data-ttu-id="5fa50-274">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-274">x64</span></span> |
| <span data-ttu-id="5fa50-275">openSUSE</span><span class="sxs-lookup"><span data-stu-id="5fa50-275">openSUSE</span></span>                       | <span data-ttu-id="5fa50-276">15+</span><span class="sxs-lookup"><span data-stu-id="5fa50-276">15+</span></span>                   | <span data-ttu-id="5fa50-277">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-277">x64</span></span> |
| <span data-ttu-id="5fa50-278">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="5fa50-278">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="5fa50-279">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="5fa50-279">12 SP2+</span></span>               | <span data-ttu-id="5fa50-280">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-280">x64</span></span> |
| <span data-ttu-id="5fa50-281">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-281">Alpine Linux</span></span>                   | <span data-ttu-id="5fa50-282">3.8+</span><span class="sxs-lookup"><span data-stu-id="5fa50-282">3.8+</span></span>                  | <span data-ttu-id="5fa50-283">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="5fa50-283">x64, ARM64</span></span> |

<span data-ttu-id="5fa50-284">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-284">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="5fa50-285">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="5fa50-285">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="5fa50-286">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="5fa50-286">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="5fa50-287">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="5fa50-287">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="5fa50-288">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-288">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="5fa50-289">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="5fa50-289">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="5fa50-290">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="5fa50-290">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-291">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-291">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-292">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-292">OS</span></span>                             |  <span data-ttu-id="5fa50-293">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-293">Version</span></span>                |  <span data-ttu-id="5fa50-294">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-294">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="5fa50-295">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-295">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="5fa50-296">6, 7</span><span class="sxs-lookup"><span data-stu-id="5fa50-296">6, 7</span></span>                   | <span data-ttu-id="5fa50-297">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-297">x64</span></span> |
| <span data-ttu-id="5fa50-298">CentOS</span><span class="sxs-lookup"><span data-stu-id="5fa50-298">CentOS</span></span>                         |  <span data-ttu-id="5fa50-299">7</span><span class="sxs-lookup"><span data-stu-id="5fa50-299">7</span></span>                      | <span data-ttu-id="5fa50-300">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-300">x64</span></span> |
| <span data-ttu-id="5fa50-301">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-301">Oracle Linux</span></span>                   |  <span data-ttu-id="5fa50-302">7</span><span class="sxs-lookup"><span data-stu-id="5fa50-302">7</span></span>                      | <span data-ttu-id="5fa50-303">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-303">x64</span></span> |
| <span data-ttu-id="5fa50-304">Fedora</span><span class="sxs-lookup"><span data-stu-id="5fa50-304">Fedora</span></span>                         |  <span data-ttu-id="5fa50-305">29, 30</span><span class="sxs-lookup"><span data-stu-id="5fa50-305">29, 30</span></span>                 | <span data-ttu-id="5fa50-306">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-306">x64</span></span> |
| <span data-ttu-id="5fa50-307">Debian</span><span class="sxs-lookup"><span data-stu-id="5fa50-307">Debian</span></span>                         |  <span data-ttu-id="5fa50-308">9</span><span class="sxs-lookup"><span data-stu-id="5fa50-308">9</span></span>                      | <span data-ttu-id="5fa50-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-309">x64, ARM32</span></span> |
| <span data-ttu-id="5fa50-310">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5fa50-310">Ubuntu</span></span>                         |  <span data-ttu-id="5fa50-311">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="5fa50-311">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="5fa50-312">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-312">x64, ARM32</span></span> |
| <span data-ttu-id="5fa50-313">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="5fa50-313">Linux Mint</span></span>                     |  <span data-ttu-id="5fa50-314">17, 18</span><span class="sxs-lookup"><span data-stu-id="5fa50-314">17, 18</span></span>                 | <span data-ttu-id="5fa50-315">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-315">x64</span></span> |
| <span data-ttu-id="5fa50-316">openSUSE</span><span class="sxs-lookup"><span data-stu-id="5fa50-316">openSUSE</span></span>                       |  <span data-ttu-id="5fa50-317">15+</span><span class="sxs-lookup"><span data-stu-id="5fa50-317">15+</span></span>                    | <span data-ttu-id="5fa50-318">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-318">x64</span></span> |
| <span data-ttu-id="5fa50-319">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="5fa50-319">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="5fa50-320">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="5fa50-320">12 SP2+</span></span>                | <span data-ttu-id="5fa50-321">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-321">x64</span></span> |
| <span data-ttu-id="5fa50-322">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-322">Alpine Linux</span></span>                   |  <span data-ttu-id="5fa50-323">3.8+</span><span class="sxs-lookup"><span data-stu-id="5fa50-323">3.8+</span></span>                   | <span data-ttu-id="5fa50-324">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-324">x64</span></span> |

<span data-ttu-id="5fa50-325">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-325">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="5fa50-326">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-326">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="5fa50-327">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5fa50-327">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="5fa50-328">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="5fa50-328">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="5fa50-329">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="5fa50-329">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-330">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-330">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-331">SO</span><span class="sxs-lookup"><span data-stu-id="5fa50-331">OS</span></span>                             |  <span data-ttu-id="5fa50-332">Versión</span><span class="sxs-lookup"><span data-stu-id="5fa50-332">Version</span></span>                |  <span data-ttu-id="5fa50-333">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-333">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="5fa50-334">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-334">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="5fa50-335">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="5fa50-335">6, 7, 8</span></span>                | <span data-ttu-id="5fa50-336">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-336">x64</span></span> |
| <span data-ttu-id="5fa50-337">CentOS</span><span class="sxs-lookup"><span data-stu-id="5fa50-337">CentOS</span></span>                         |  <span data-ttu-id="5fa50-338">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-338">7+</span></span>                     | <span data-ttu-id="5fa50-339">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-339">x64</span></span> |
| <span data-ttu-id="5fa50-340">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-340">Oracle Linux</span></span>                   |  <span data-ttu-id="5fa50-341">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="5fa50-341">7+</span></span>                     | <span data-ttu-id="5fa50-342">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-342">x64</span></span> |
| <span data-ttu-id="5fa50-343">Fedora</span><span class="sxs-lookup"><span data-stu-id="5fa50-343">Fedora</span></span>                         |  <span data-ttu-id="5fa50-344">30+</span><span class="sxs-lookup"><span data-stu-id="5fa50-344">30+</span></span>                    | <span data-ttu-id="5fa50-345">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-345">x64</span></span> |
| <span data-ttu-id="5fa50-346">Debian</span><span class="sxs-lookup"><span data-stu-id="5fa50-346">Debian</span></span>                         |  <span data-ttu-id="5fa50-347">9</span><span class="sxs-lookup"><span data-stu-id="5fa50-347">9</span></span>                      | <span data-ttu-id="5fa50-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-348">x64, ARM32</span></span> |
| <span data-ttu-id="5fa50-349">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5fa50-349">Ubuntu</span></span>                         |  <span data-ttu-id="5fa50-350">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="5fa50-350">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="5fa50-351">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="5fa50-351">x64, ARM32</span></span> |
| <span data-ttu-id="5fa50-352">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="5fa50-352">Linux Mint</span></span>                     |  <span data-ttu-id="5fa50-353">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="5fa50-353">17+</span></span>                    | <span data-ttu-id="5fa50-354">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-354">x64</span></span> |
| <span data-ttu-id="5fa50-355">openSUSE</span><span class="sxs-lookup"><span data-stu-id="5fa50-355">openSUSE</span></span>                       |  <span data-ttu-id="5fa50-356">15+</span><span class="sxs-lookup"><span data-stu-id="5fa50-356">15+</span></span>                    | <span data-ttu-id="5fa50-357">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-357">x64</span></span> |
| <span data-ttu-id="5fa50-358">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="5fa50-358">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="5fa50-359">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="5fa50-359">12 SP2+</span></span>                | <span data-ttu-id="5fa50-360">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-360">x64</span></span> |
| <span data-ttu-id="5fa50-361">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-361">Alpine Linux</span></span>                   |  <span data-ttu-id="5fa50-362">3.8+</span><span class="sxs-lookup"><span data-stu-id="5fa50-362">3.8+</span></span>                   | <span data-ttu-id="5fa50-363">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-363">x64</span></span> |

<span data-ttu-id="5fa50-364">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-364">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="5fa50-365">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="5fa50-365">Linux distribution dependencies</span></span>

<span data-ttu-id="5fa50-366">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="5fa50-366">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5fa50-367">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="5fa50-367">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="5fa50-368">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="5fa50-368">Ubuntu</span></span>

<span data-ttu-id="5fa50-369">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fa50-369">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="5fa50-370">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="5fa50-370">liblttng-ust0</span></span>
- <span data-ttu-id="5fa50-371">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-371">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="5fa50-372">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-372">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="5fa50-373">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="5fa50-373">libssl1.0.0</span></span>
- <span data-ttu-id="5fa50-374">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="5fa50-374">libkrb5-3</span></span>
- <span data-ttu-id="5fa50-375">zlib1g</span><span class="sxs-lookup"><span data-stu-id="5fa50-375">zlib1g</span></span>
- <span data-ttu-id="5fa50-376">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-376">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="5fa50-377">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-377">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="5fa50-378">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-378">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="5fa50-379">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="5fa50-379">libicu60 (for 18.x)</span></span>

<span data-ttu-id="5fa50-380">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fa50-380">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5fa50-381">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-381">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="5fa50-382">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="5fa50-382">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="5fa50-383">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="5fa50-383">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="5fa50-384">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5fa50-384">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="5fa50-385">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="5fa50-385">CentOS and Fedora</span></span>

<span data-ttu-id="5fa50-386">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="5fa50-386">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="5fa50-387">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="5fa50-387">lttng-ust</span></span>
- <span data-ttu-id="5fa50-388">libcurl</span><span class="sxs-lookup"><span data-stu-id="5fa50-388">libcurl</span></span>
- <span data-ttu-id="5fa50-389">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="5fa50-389">openssl-libs</span></span>
- <span data-ttu-id="5fa50-390">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="5fa50-390">krb5-libs</span></span>
- <span data-ttu-id="5fa50-391">libicu</span><span class="sxs-lookup"><span data-stu-id="5fa50-391">libicu</span></span>
- <span data-ttu-id="5fa50-392">zlib</span><span class="sxs-lookup"><span data-stu-id="5fa50-392">zlib</span></span>

<span data-ttu-id="5fa50-393">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="5fa50-393">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="5fa50-394">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fa50-394">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="5fa50-395">libunwind</span><span class="sxs-lookup"><span data-stu-id="5fa50-395">libunwind</span></span>
- <span data-ttu-id="5fa50-396">libuuid</span><span class="sxs-lookup"><span data-stu-id="5fa50-396">libuuid</span></span>

<span data-ttu-id="5fa50-397">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-397">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="5fa50-398">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fa50-398">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="5fa50-399">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-399">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="5fa50-400">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="5fa50-400">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="5fa50-401">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="5fa50-401">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="5fa50-402">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="5fa50-402">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="alpine"></a><span data-ttu-id="5fa50-403">Alpine</span><span class="sxs-lookup"><span data-stu-id="5fa50-403">Alpine</span></span>

<span data-ttu-id="5fa50-404">Las distribuciones de Alpine necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="5fa50-404">Alpine distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="5fa50-405">icu-libs (esto no es necesario si la globalización está deshabilitada)</span><span class="sxs-lookup"><span data-stu-id="5fa50-405">icu-libs (this is not needed if globalization is disabled)</span></span>
- <span data-ttu-id="5fa50-406">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="5fa50-406">krb5-libs</span></span>
- <span data-ttu-id="5fa50-407">libcurl</span><span class="sxs-lookup"><span data-stu-id="5fa50-407">libcurl</span></span>
- <span data-ttu-id="5fa50-408">libintl</span><span class="sxs-lookup"><span data-stu-id="5fa50-408">libintl</span></span>
- <span data-ttu-id="5fa50-409">libssl1.1 (para Alpine 3.9 o una versión posterior) o libssl1.0 (para versiones anteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-409">libssl1.1 (for Alpine 3.9 or later) or libssl1.0 (for older ones)</span></span>
- <span data-ttu-id="5fa50-410">libstdc++</span><span class="sxs-lookup"><span data-stu-id="5fa50-410">libstdc++</span></span>
- <span data-ttu-id="5fa50-411">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="5fa50-411">lttng-ust</span></span>
- <span data-ttu-id="5fa50-412">numactl (opcional, útil solo para dispositivos con NUMA habilitado)</span><span class="sxs-lookup"><span data-stu-id="5fa50-412">numactl (optional, useful only for devices with NUMA enabled)</span></span>
- <span data-ttu-id="5fa50-413">zlib</span><span class="sxs-lookup"><span data-stu-id="5fa50-413">zlib</span></span>

<span data-ttu-id="5fa50-414">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fa50-414">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="5fa50-415">libgdiplus (solo está disponible en el repositorio Edge/Testing)</span><span class="sxs-lookup"><span data-stu-id="5fa50-415">libgdiplus (it is available only in the edge/testing repository)</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="5fa50-416">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="5fa50-416">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="5fa50-417">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="5fa50-417">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="5fa50-418">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="5fa50-418">.NET Core Version</span></span> | <span data-ttu-id="5fa50-419">macOS</span><span class="sxs-lookup"><span data-stu-id="5fa50-419">macOS</span></span>                 | <span data-ttu-id="5fa50-420">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="5fa50-420">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="5fa50-421">3.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-421">3.1</span></span>               | <span data-ttu-id="5fa50-422">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-422">High Sierra (10.13+)</span></span>  | <span data-ttu-id="5fa50-423">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-423">x64</span></span> | [<span data-ttu-id="5fa50-424">Más información</span><span class="sxs-lookup"><span data-stu-id="5fa50-424">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="5fa50-425">3.0</span><span class="sxs-lookup"><span data-stu-id="5fa50-425">3.0</span></span>               | <span data-ttu-id="5fa50-426">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-426">High Sierra (10.13+)</span></span>  | <span data-ttu-id="5fa50-427">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-427">x64</span></span> | [<span data-ttu-id="5fa50-428">Más información</span><span class="sxs-lookup"><span data-stu-id="5fa50-428">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="5fa50-429">2.2</span><span class="sxs-lookup"><span data-stu-id="5fa50-429">2.2</span></span>               | <span data-ttu-id="5fa50-430">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-430">Sierra (10.12+)</span></span>       | <span data-ttu-id="5fa50-431">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-431">x64</span></span> | [<span data-ttu-id="5fa50-432">Más información</span><span class="sxs-lookup"><span data-stu-id="5fa50-432">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="5fa50-433">2.1</span><span class="sxs-lookup"><span data-stu-id="5fa50-433">2.1</span></span>               | <span data-ttu-id="5fa50-434">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="5fa50-434">Sierra (10.12+)</span></span>       | <span data-ttu-id="5fa50-435">x64</span><span class="sxs-lookup"><span data-stu-id="5fa50-435">x64</span></span> | [<span data-ttu-id="5fa50-436">Más información</span><span class="sxs-lookup"><span data-stu-id="5fa50-436">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="5fa50-437">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="5fa50-437">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="5fa50-438">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="5fa50-438">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="5fa50-439">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="5fa50-439">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="5fa50-440">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="5fa50-440">Prior released versions aren't notarized.</span></span> <span data-ttu-id="5fa50-441">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="5fa50-441">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="5fa50-443">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-443">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="5fa50-444">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="5fa50-444">libgdiplus</span></span>

<span data-ttu-id="5fa50-445">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="5fa50-445">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="5fa50-446">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="5fa50-446">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="5fa50-447">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="5fa50-447">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="5fa50-448">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="5fa50-448">Next steps</span></span>

- <span data-ttu-id="5fa50-449">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5fa50-449">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="5fa50-450">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="5fa50-450">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
