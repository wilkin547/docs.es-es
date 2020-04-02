---
title: 'SDK de .NET Core y dependencias del entorno de ejecución: .NET Core'
description: Detalla los requisitos previos de la arquitectura de la CPU y del sistema operativo para instalar el SDK y el entorno de ejecución de .NET Core en Windows, Linux y macOS.
author: leecow
ms.author: leecow
ms.date: 12/04/2019
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 023b8fdf029dd6b17fe2186296d87dd7507c60b5
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/19/2020
ms.locfileid: "79546567"
---
# <a name="net-core-dependencies-and-requirements"></a><span data-ttu-id="cecfd-103">Dependencias y requisitos de .NET Core</span><span class="sxs-lookup"><span data-stu-id="cecfd-103">.NET Core dependencies and requirements</span></span>

<span data-ttu-id="cecfd-104">En este artículo se detallan las arquitecturas de la CPU y de los sistemas operativos que son compatibles con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cecfd-104">This article details which operating systems and CPU architecture are supported by .NET Core.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="cecfd-105">Sistemas operativos admitidos</span><span class="sxs-lookup"><span data-stu-id="cecfd-105">Supported operating systems</span></span>

::: zone pivot="os-windows"

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-core-31"></a>[<span data-ttu-id="cecfd-106">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-106">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="cecfd-107">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="cecfd-107">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-108">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-108">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-109">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-109">OS</span></span>                            | <span data-ttu-id="cecfd-110">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-110">Version</span></span>                        | <span data-ttu-id="cecfd-111">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-111">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="cecfd-112">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="cecfd-112">Windows Client</span></span>                | <span data-ttu-id="cecfd-113">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-113">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="cecfd-114">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-114">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-115">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="cecfd-115">Windows 10 Client</span></span>             | <span data-ttu-id="cecfd-116">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-116">Version 1607+</span></span>                  | <span data-ttu-id="cecfd-117">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-117">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-118">Windows Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-118">Windows Server</span></span>                | <span data-ttu-id="cecfd-119">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-119">2012 R2+</span></span>                       | <span data-ttu-id="cecfd-120">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-120">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-121">Nano Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-121">Nano Server</span></span>                   | <span data-ttu-id="cecfd-122">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-122">Version 1803+</span></span>                  | <span data-ttu-id="cecfd-123">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-123">x64, ARM32</span></span>      |

<span data-ttu-id="cecfd-124">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-124">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="cecfd-125">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cecfd-125">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="cecfd-126">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="cecfd-126">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="cecfd-127">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="cecfd-127">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-128">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-128">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-129">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-129">OS</span></span>                            | <span data-ttu-id="cecfd-130">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-130">Version</span></span>                        | <span data-ttu-id="cecfd-131">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-131">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="cecfd-132">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="cecfd-132">Windows Client</span></span>                | <span data-ttu-id="cecfd-133">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-133">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="cecfd-134">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-134">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-135">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="cecfd-135">Windows 10 Client</span></span>             | <span data-ttu-id="cecfd-136">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-136">Version 1607+</span></span>                  | <span data-ttu-id="cecfd-137">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-137">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-138">Windows Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-138">Windows Server</span></span>                | <span data-ttu-id="cecfd-139">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-139">2012 R2+</span></span>                       | <span data-ttu-id="cecfd-140">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-140">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-141">Nano Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-141">Nano Server</span></span>                   | <span data-ttu-id="cecfd-142">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-142">Version 1803+</span></span>                  | <span data-ttu-id="cecfd-143">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-143">x64, ARM32</span></span>      |

<span data-ttu-id="cecfd-144">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-144">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="cecfd-145">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cecfd-145">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cecfd-146">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="cecfd-146">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="cecfd-147">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="cecfd-147">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-148">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-148">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-149">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-149">OS</span></span>                            | <span data-ttu-id="cecfd-150">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-150">Version</span></span>                        | <span data-ttu-id="cecfd-151">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-151">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="cecfd-152">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="cecfd-152">Windows Client</span></span>                | <span data-ttu-id="cecfd-153">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-153">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="cecfd-154">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-154">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-155">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="cecfd-155">Windows 10 Client</span></span>             | <span data-ttu-id="cecfd-156">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-156">Version 1607+</span></span>                  | <span data-ttu-id="cecfd-157">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-157">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-158">Windows Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-158">Windows Server</span></span>                | <span data-ttu-id="cecfd-159">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-159">2008 R2 SP1+</span></span>                   | <span data-ttu-id="cecfd-160">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-160">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-161">Nano Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-161">Nano Server</span></span>                   | <span data-ttu-id="cecfd-162">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-162">Version 1803+</span></span>                   | <span data-ttu-id="cecfd-163">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-163">x64, ARM32</span></span>      |

<span data-ttu-id="cecfd-164">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-164">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="cecfd-165">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-165">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cecfd-166">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="cecfd-166">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-167">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-167">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-168">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-168">OS</span></span>                            | <span data-ttu-id="cecfd-169">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-169">Version</span></span>                        | <span data-ttu-id="cecfd-170">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-170">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="cecfd-171">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="cecfd-171">Windows Client</span></span>                | <span data-ttu-id="cecfd-172">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-172">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="cecfd-173">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-173">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-174">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="cecfd-174">Windows 10 Client</span></span>             | <span data-ttu-id="cecfd-175">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-175">Version 1607+</span></span>                  | <span data-ttu-id="cecfd-176">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-176">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-177">Windows Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-177">Windows Server</span></span>                | <span data-ttu-id="cecfd-178">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-178">2008 R2 SP1+</span></span>                   | <span data-ttu-id="cecfd-179">x64, x86</span><span class="sxs-lookup"><span data-stu-id="cecfd-179">x64, x86</span></span>        |
| <span data-ttu-id="cecfd-180">Nano Server</span><span class="sxs-lookup"><span data-stu-id="cecfd-180">Nano Server</span></span>                   | <span data-ttu-id="cecfd-181">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-181">Version 1803+</span></span>                  | <span data-ttu-id="cecfd-182">x64,</span><span class="sxs-lookup"><span data-stu-id="cecfd-182">x64,</span></span>            |

<span data-ttu-id="cecfd-183">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-183">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2"></a><span data-ttu-id="cecfd-184">Windows 7, Vista, 8.1, Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cecfd-184">Windows 7 / Vista / 8.1 / Server 2008 R2</span></span>

<span data-ttu-id="cecfd-185">Se necesitan dependencias adicionales en caso de instalar el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="cecfd-185">Additional dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

- <span data-ttu-id="cecfd-186">Windows 7 SP1</span><span class="sxs-lookup"><span data-stu-id="cecfd-186">Windows 7 SP1</span></span>
- <span data-ttu-id="cecfd-187">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="cecfd-187">Windows Vista SP 2</span></span>
- <span data-ttu-id="cecfd-188">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-188">Windows 8.1</span></span>
- <span data-ttu-id="cecfd-189">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="cecfd-189">Windows Server 2008 R2</span></span>
- <span data-ttu-id="cecfd-190">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="cecfd-190">Windows Server 2012 R2</span></span>

<span data-ttu-id="cecfd-191">Instale el software siguiente:</span><span class="sxs-lookup"><span data-stu-id="cecfd-191">Install the following:</span></span>

- <span data-ttu-id="cecfd-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span><span class="sxs-lookup"><span data-stu-id="cecfd-192">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685).</span></span>
- [<span data-ttu-id="cecfd-193">KB2533623</span><span class="sxs-lookup"><span data-stu-id="cecfd-193">KB2533623</span></span>](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)

<span data-ttu-id="cecfd-194">Los requisitos anteriores también son necesarios si se encuentra con uno de los errores siguientes:</span><span class="sxs-lookup"><span data-stu-id="cecfd-194">The requirements above are also required if you come across one of the following errors:</span></span>

> <span data-ttu-id="cecfd-195">El programa no se puede iniciar porque el archivo *api-ms-win-crt-runtime-l1-1-0.dll* falta en el equipo.</span><span class="sxs-lookup"><span data-stu-id="cecfd-195">The program can't start because *api-ms-win-crt-runtime-l1-1-0.dll* is missing from your computer.</span></span> <span data-ttu-id="cecfd-196">Intente volver a instalar el programa para corregir este problema.</span><span class="sxs-lookup"><span data-stu-id="cecfd-196">Try reinstalling the program to fix this problem.</span></span>
>
> <span data-ttu-id="cecfd-197">\- o -</span><span class="sxs-lookup"><span data-stu-id="cecfd-197">\- or -</span></span>
>
> <span data-ttu-id="cecfd-198">La biblioteca *hostfxr.dll* se ha encontrado, pero no se ha podido cargar desde *C:\\\<path_to_app>\\hostfxr.dll*.</span><span class="sxs-lookup"><span data-stu-id="cecfd-198">The library *hostfxr.dll* was found, but loading it from *C:\\\<path_to_app>\\hostfxr.dll* failed.</span></span>

::: zone-end

::: zone pivot="os-linux"

# <a name="net-core-31"></a>[<span data-ttu-id="cecfd-199">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-199">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="cecfd-200">.NET Core 3.1 considera Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cecfd-200">.NET Core 3.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="cecfd-201">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="cecfd-201">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="cecfd-202">.NET Core 3.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="cecfd-202">.NET Core 3.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-203">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-203">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-204">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-204">OS</span></span>                             | <span data-ttu-id="cecfd-205">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-205">Version</span></span>               | <span data-ttu-id="cecfd-206">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-206">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="cecfd-207">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-207">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="cecfd-208">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="cecfd-208">6, 7, 8</span></span>               | <span data-ttu-id="cecfd-209">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-209">x64</span></span> |
| <span data-ttu-id="cecfd-210">CentOS</span><span class="sxs-lookup"><span data-stu-id="cecfd-210">CentOS</span></span>                         | <span data-ttu-id="cecfd-211">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-211">7+</span></span>                    | <span data-ttu-id="cecfd-212">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-212">x64</span></span> |
| <span data-ttu-id="cecfd-213">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-213">Oracle Linux</span></span>                   | <span data-ttu-id="cecfd-214">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-214">7+</span></span>                    | <span data-ttu-id="cecfd-215">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-215">x64</span></span> |
| <span data-ttu-id="cecfd-216">Fedora</span><span class="sxs-lookup"><span data-stu-id="cecfd-216">Fedora</span></span>                         | <span data-ttu-id="cecfd-217">30+</span><span class="sxs-lookup"><span data-stu-id="cecfd-217">30+</span></span>                   | <span data-ttu-id="cecfd-218">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-218">x64</span></span> |
| <span data-ttu-id="cecfd-219">Debian</span><span class="sxs-lookup"><span data-stu-id="cecfd-219">Debian</span></span>                         | <span data-ttu-id="cecfd-220">9+</span><span class="sxs-lookup"><span data-stu-id="cecfd-220">9+</span></span>                    | <span data-ttu-id="cecfd-221">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-221">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="cecfd-222">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="cecfd-222">Ubuntu</span></span>                         | <span data-ttu-id="cecfd-223">16.04+</span><span class="sxs-lookup"><span data-stu-id="cecfd-223">16.04+</span></span>                | <span data-ttu-id="cecfd-224">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-224">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="cecfd-225">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="cecfd-225">Linux Mint</span></span>                     | <span data-ttu-id="cecfd-226">18+</span><span class="sxs-lookup"><span data-stu-id="cecfd-226">18+</span></span>                   | <span data-ttu-id="cecfd-227">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-227">x64</span></span> |
| <span data-ttu-id="cecfd-228">openSUSE</span><span class="sxs-lookup"><span data-stu-id="cecfd-228">openSUSE</span></span>                       | <span data-ttu-id="cecfd-229">15+</span><span class="sxs-lookup"><span data-stu-id="cecfd-229">15+</span></span>                   | <span data-ttu-id="cecfd-230">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-230">x64</span></span> |
| <span data-ttu-id="cecfd-231">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="cecfd-231">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="cecfd-232">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="cecfd-232">12 SP2+</span></span>               | <span data-ttu-id="cecfd-233">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-233">x64</span></span> |
| <span data-ttu-id="cecfd-234">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-234">Alpine Linux</span></span>                   | <span data-ttu-id="cecfd-235">3.10 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-235">3.10+</span></span>                 | <span data-ttu-id="cecfd-236">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-236">x64, ARM64</span></span> |

<span data-ttu-id="cecfd-237">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-237">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md).</span></span>

<span data-ttu-id="cecfd-238">Para obtener más información sobre cómo instalar .NET Core 3.1 en ARM64 (kernel 4.14 y posteriores), vea [Instalación de .NET Core 3.0 en Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span><span class="sxs-lookup"><span data-stu-id="cecfd-238">For more information about how to install .NET Core 3.1 on ARM64 (kernel 4.14+), see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cecfd-239">La compatibilidad con ARM64 requiere la versión 4.14 del kernel de Linux o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="cecfd-239">ARM64 support requires Linux kernel 4.14 or higher.</span></span> <span data-ttu-id="cecfd-240">No todas las distribuciones de Linux cumplen este requisito.</span><span class="sxs-lookup"><span data-stu-id="cecfd-240">Some linux distributions satisfy this requirement while others don't.</span></span> <span data-ttu-id="cecfd-241">Por ejemplo, Ubuntu 18.04 es compatible, pero Ubuntu 16.04, no.</span><span class="sxs-lookup"><span data-stu-id="cecfd-241">For example, Ubuntu 18.04 is supported but Ubuntu 16.04 doesn't.</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="cecfd-242">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="cecfd-242">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="cecfd-243">*.NET Core 3.0 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="cecfd-243">*.NET Core 3.0 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="cecfd-244">.NET Core 3.0 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cecfd-244">.NET Core 3.0 treats Linux as a single operating system.</span></span> <span data-ttu-id="cecfd-245">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="cecfd-245">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="cecfd-246">.NET Core 3.0 se admite en las versiones o distribuciones siguientes de Linux:</span><span class="sxs-lookup"><span data-stu-id="cecfd-246">.NET Core 3.0 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-247">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-247">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-248">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-248">OS</span></span>                             | <span data-ttu-id="cecfd-249">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-249">Version</span></span>               | <span data-ttu-id="cecfd-250">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-250">Architectures</span></span>    |
| ------------------------------ | --------------------- | ---------------- |
| <span data-ttu-id="cecfd-251">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-251">Red Hat Enterprise Linux</span></span>       | <span data-ttu-id="cecfd-252">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="cecfd-252">6, 7, 8</span></span>               | <span data-ttu-id="cecfd-253">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-253">x64</span></span> |
| <span data-ttu-id="cecfd-254">CentOS</span><span class="sxs-lookup"><span data-stu-id="cecfd-254">CentOS</span></span>                         | <span data-ttu-id="cecfd-255">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-255">7+</span></span>                    | <span data-ttu-id="cecfd-256">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-256">x64</span></span> |
| <span data-ttu-id="cecfd-257">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-257">Oracle Linux</span></span>                   | <span data-ttu-id="cecfd-258">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-258">7+</span></span>                    | <span data-ttu-id="cecfd-259">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-259">x64</span></span> |
| <span data-ttu-id="cecfd-260">Fedora</span><span class="sxs-lookup"><span data-stu-id="cecfd-260">Fedora</span></span>                         | <span data-ttu-id="cecfd-261">29+</span><span class="sxs-lookup"><span data-stu-id="cecfd-261">29+</span></span>                   | <span data-ttu-id="cecfd-262">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-262">x64</span></span> |
| <span data-ttu-id="cecfd-263">Debian</span><span class="sxs-lookup"><span data-stu-id="cecfd-263">Debian</span></span>                         | <span data-ttu-id="cecfd-264">9+</span><span class="sxs-lookup"><span data-stu-id="cecfd-264">9+</span></span>                    | <span data-ttu-id="cecfd-265">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-265">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="cecfd-266">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="cecfd-266">Ubuntu</span></span>                         | <span data-ttu-id="cecfd-267">16.04+</span><span class="sxs-lookup"><span data-stu-id="cecfd-267">16.04+</span></span>                | <span data-ttu-id="cecfd-268">x64, ARM32, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-268">x64, ARM32, ARM64</span></span> |
| <span data-ttu-id="cecfd-269">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="cecfd-269">Linux Mint</span></span>                     | <span data-ttu-id="cecfd-270">18+</span><span class="sxs-lookup"><span data-stu-id="cecfd-270">18+</span></span>                   | <span data-ttu-id="cecfd-271">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-271">x64</span></span> |
| <span data-ttu-id="cecfd-272">openSUSE</span><span class="sxs-lookup"><span data-stu-id="cecfd-272">openSUSE</span></span>                       | <span data-ttu-id="cecfd-273">15+</span><span class="sxs-lookup"><span data-stu-id="cecfd-273">15+</span></span>                   | <span data-ttu-id="cecfd-274">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-274">x64</span></span> |
| <span data-ttu-id="cecfd-275">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="cecfd-275">SUSE Enterprise Linux (SLES)</span></span>   | <span data-ttu-id="cecfd-276">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="cecfd-276">12 SP2+</span></span>               | <span data-ttu-id="cecfd-277">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-277">x64</span></span> |
| <span data-ttu-id="cecfd-278">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-278">Alpine Linux</span></span>                   | <span data-ttu-id="cecfd-279">3.8+</span><span class="sxs-lookup"><span data-stu-id="cecfd-279">3.8+</span></span>                  | <span data-ttu-id="cecfd-280">x64, ARM64</span><span class="sxs-lookup"><span data-stu-id="cecfd-280">x64, ARM64</span></span> |

<span data-ttu-id="cecfd-281">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-281">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md).</span></span>

<span data-ttu-id="cecfd-282">Para obtener más información sobre cómo instalar .NET Core 3.0 en ARM64, vea [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213) (Instalación de .NET Core 3.0 en Linux ARM64).</span><span class="sxs-lookup"><span data-stu-id="cecfd-282">For more information about how to install .NET Core 3.0 on ARM64, see [Installing .NET Core 3.0 on Linux ARM64](https://gist.github.com/richlander/467813274cea8abc624553ee72b28213).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="cecfd-283">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="cecfd-283">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="cecfd-284">*.NET Core 2.2 no se admite actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="cecfd-284">*.NET Core 2.2 is currently out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="cecfd-285">.NET Core 2.2 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cecfd-285">.NET Core 2.2 treats Linux as a single operating system.</span></span> <span data-ttu-id="cecfd-286">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="cecfd-286">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="cecfd-287">.NET Core 2.2 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="cecfd-287">.NET Core 2.2 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-288">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-288">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-289">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-289">OS</span></span>                             |  <span data-ttu-id="cecfd-290">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-290">Version</span></span>                |  <span data-ttu-id="cecfd-291">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-291">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="cecfd-292">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-292">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="cecfd-293">6, 7</span><span class="sxs-lookup"><span data-stu-id="cecfd-293">6, 7</span></span>                   | <span data-ttu-id="cecfd-294">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-294">x64</span></span> |
| <span data-ttu-id="cecfd-295">CentOS</span><span class="sxs-lookup"><span data-stu-id="cecfd-295">CentOS</span></span>                         |  <span data-ttu-id="cecfd-296">7</span><span class="sxs-lookup"><span data-stu-id="cecfd-296">7</span></span>                      | <span data-ttu-id="cecfd-297">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-297">x64</span></span> |
| <span data-ttu-id="cecfd-298">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-298">Oracle Linux</span></span>                   |  <span data-ttu-id="cecfd-299">7</span><span class="sxs-lookup"><span data-stu-id="cecfd-299">7</span></span>                      | <span data-ttu-id="cecfd-300">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-300">x64</span></span> |
| <span data-ttu-id="cecfd-301">Fedora</span><span class="sxs-lookup"><span data-stu-id="cecfd-301">Fedora</span></span>                         |  <span data-ttu-id="cecfd-302">29, 30</span><span class="sxs-lookup"><span data-stu-id="cecfd-302">29, 30</span></span>                 | <span data-ttu-id="cecfd-303">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-303">x64</span></span> |
| <span data-ttu-id="cecfd-304">Debian</span><span class="sxs-lookup"><span data-stu-id="cecfd-304">Debian</span></span>                         |  <span data-ttu-id="cecfd-305">9</span><span class="sxs-lookup"><span data-stu-id="cecfd-305">9</span></span>                      | <span data-ttu-id="cecfd-306">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-306">x64, ARM32</span></span> |
| <span data-ttu-id="cecfd-307">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="cecfd-307">Ubuntu</span></span>                         |  <span data-ttu-id="cecfd-308">16.04, 18.04, 18.10</span><span class="sxs-lookup"><span data-stu-id="cecfd-308">16.04, 18.04, 18.10</span></span>    | <span data-ttu-id="cecfd-309">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-309">x64, ARM32</span></span> |
| <span data-ttu-id="cecfd-310">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="cecfd-310">Linux Mint</span></span>                     |  <span data-ttu-id="cecfd-311">17, 18</span><span class="sxs-lookup"><span data-stu-id="cecfd-311">17, 18</span></span>                 | <span data-ttu-id="cecfd-312">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-312">x64</span></span> |
| <span data-ttu-id="cecfd-313">openSUSE</span><span class="sxs-lookup"><span data-stu-id="cecfd-313">openSUSE</span></span>                       |  <span data-ttu-id="cecfd-314">15+</span><span class="sxs-lookup"><span data-stu-id="cecfd-314">15+</span></span>                    | <span data-ttu-id="cecfd-315">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-315">x64</span></span> |
| <span data-ttu-id="cecfd-316">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="cecfd-316">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="cecfd-317">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="cecfd-317">12 SP2+</span></span>                | <span data-ttu-id="cecfd-318">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-318">x64</span></span> |
| <span data-ttu-id="cecfd-319">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-319">Alpine Linux</span></span>                   |  <span data-ttu-id="cecfd-320">3.8+</span><span class="sxs-lookup"><span data-stu-id="cecfd-320">3.8+</span></span>                   | <span data-ttu-id="cecfd-321">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-321">x64</span></span> |

<span data-ttu-id="cecfd-322">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-322">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="cecfd-323">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-323">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="cecfd-324">.NET Core 2.1 considera a Linux como un único sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="cecfd-324">.NET Core 2.1 treats Linux as a single operating system.</span></span> <span data-ttu-id="cecfd-325">Solo hay una única compilación de Linux (por arquitectura de chip) para las distribuciones de Linux compatibles.</span><span class="sxs-lookup"><span data-stu-id="cecfd-325">There's a single Linux build (per chip architecture) for supported Linux distributions.</span></span>

<span data-ttu-id="cecfd-326">.NET Core 2.1 se admite en las siguientes versiones o distribuciones de Linux:</span><span class="sxs-lookup"><span data-stu-id="cecfd-326">.NET Core 2.1 is supported on the following Linux distributions/versions:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-327">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-327">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-328">SO</span><span class="sxs-lookup"><span data-stu-id="cecfd-328">OS</span></span>                             |  <span data-ttu-id="cecfd-329">Versión</span><span class="sxs-lookup"><span data-stu-id="cecfd-329">Version</span></span>                |  <span data-ttu-id="cecfd-330">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-330">Architectures</span></span>   |
| ------------------------------ | ----------------------- | ---------------- |
| <span data-ttu-id="cecfd-331">Red Hat Enterprise Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-331">Red Hat Enterprise Linux</span></span>       |  <span data-ttu-id="cecfd-332">6, 7, 8</span><span class="sxs-lookup"><span data-stu-id="cecfd-332">6, 7, 8</span></span>                | <span data-ttu-id="cecfd-333">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-333">x64</span></span> |
| <span data-ttu-id="cecfd-334">CentOS</span><span class="sxs-lookup"><span data-stu-id="cecfd-334">CentOS</span></span>                         |  <span data-ttu-id="cecfd-335">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-335">7+</span></span>                     | <span data-ttu-id="cecfd-336">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-336">x64</span></span> |
| <span data-ttu-id="cecfd-337">Oracle Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-337">Oracle Linux</span></span>                   |  <span data-ttu-id="cecfd-338">7 (o posterior)</span><span class="sxs-lookup"><span data-stu-id="cecfd-338">7+</span></span>                     | <span data-ttu-id="cecfd-339">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-339">x64</span></span> |
| <span data-ttu-id="cecfd-340">Fedora</span><span class="sxs-lookup"><span data-stu-id="cecfd-340">Fedora</span></span>                         |  <span data-ttu-id="cecfd-341">30+</span><span class="sxs-lookup"><span data-stu-id="cecfd-341">30+</span></span>                    | <span data-ttu-id="cecfd-342">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-342">x64</span></span> |
| <span data-ttu-id="cecfd-343">Debian</span><span class="sxs-lookup"><span data-stu-id="cecfd-343">Debian</span></span>                         |  <span data-ttu-id="cecfd-344">9</span><span class="sxs-lookup"><span data-stu-id="cecfd-344">9</span></span>                      | <span data-ttu-id="cecfd-345">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-345">x64, ARM32</span></span> |
| <span data-ttu-id="cecfd-346">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="cecfd-346">Ubuntu</span></span>                         |  <span data-ttu-id="cecfd-347">16.04, 18.04, 19.04 y 19.10</span><span class="sxs-lookup"><span data-stu-id="cecfd-347">16.04, 18.04, 19.04, 19.10</span></span>    | <span data-ttu-id="cecfd-348">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="cecfd-348">x64, ARM32</span></span> |
| <span data-ttu-id="cecfd-349">Linux Mint</span><span class="sxs-lookup"><span data-stu-id="cecfd-349">Linux Mint</span></span>                     |  <span data-ttu-id="cecfd-350">17 y posteriores</span><span class="sxs-lookup"><span data-stu-id="cecfd-350">17+</span></span>                    | <span data-ttu-id="cecfd-351">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-351">x64</span></span> |
| <span data-ttu-id="cecfd-352">openSUSE</span><span class="sxs-lookup"><span data-stu-id="cecfd-352">openSUSE</span></span>                       |  <span data-ttu-id="cecfd-353">15+</span><span class="sxs-lookup"><span data-stu-id="cecfd-353">15+</span></span>                    | <span data-ttu-id="cecfd-354">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-354">x64</span></span> |
| <span data-ttu-id="cecfd-355">SUSE Enterprise Linux (SLES)</span><span class="sxs-lookup"><span data-stu-id="cecfd-355">SUSE Enterprise Linux (SLES)</span></span>   |  <span data-ttu-id="cecfd-356">12 SP2+</span><span class="sxs-lookup"><span data-stu-id="cecfd-356">12 SP2+</span></span>                | <span data-ttu-id="cecfd-357">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-357">x64</span></span> |
| <span data-ttu-id="cecfd-358">Alpine Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-358">Alpine Linux</span></span>                   |  <span data-ttu-id="cecfd-359">3.8+</span><span class="sxs-lookup"><span data-stu-id="cecfd-359">3.8+</span></span>                   | <span data-ttu-id="cecfd-360">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-360">x64</span></span> |

<span data-ttu-id="cecfd-361">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-361">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md).</span></span>

---

## <a name="linux-distribution-dependencies"></a><span data-ttu-id="cecfd-362">Dependencias de distribución de Linux</span><span class="sxs-lookup"><span data-stu-id="cecfd-362">Linux distribution dependencies</span></span>

<span data-ttu-id="cecfd-363">En función de la distribución de Linux, es posible que tenga que instalar dependencias adicionales.</span><span class="sxs-lookup"><span data-stu-id="cecfd-363">Based on your linux distribution, you may need to install additional dependencies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cecfd-364">Los nombres y las versiones exactos pueden variar ligeramente en la distribución de Linux que prefiera.</span><span class="sxs-lookup"><span data-stu-id="cecfd-364">The exact versions and names may vary slightly on your Linux distribution of choice.</span></span>

### <a name="ubuntu"></a><span data-ttu-id="cecfd-365">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="cecfd-365">Ubuntu</span></span>

<span data-ttu-id="cecfd-366">Las distribuciones de Ubuntu necesitan tener instaladas las bibliotecas siguientes:</span><span class="sxs-lookup"><span data-stu-id="cecfd-366">Ubuntu distributions require the following libraries to be installed:</span></span>

- <span data-ttu-id="cecfd-367">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="cecfd-367">liblttng-ust0</span></span>
- <span data-ttu-id="cecfd-368">libcurl3 (para 14.x y 16.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-368">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="cecfd-369">libcurl4 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-369">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="cecfd-370">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="cecfd-370">libssl1.0.0</span></span>
- <span data-ttu-id="cecfd-371">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="cecfd-371">libkrb5-3</span></span>
- <span data-ttu-id="cecfd-372">zlib1g</span><span class="sxs-lookup"><span data-stu-id="cecfd-372">zlib1g</span></span>
- <span data-ttu-id="cecfd-373">libicu52 (para 14.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-373">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="cecfd-374">libicu55 (para 16.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-374">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="cecfd-375">libicu57 (para 17.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-375">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="cecfd-376">libicu60 (para 18.x)</span><span class="sxs-lookup"><span data-stu-id="cecfd-376">libicu60 (for 18.x)</span></span>

<span data-ttu-id="cecfd-377">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesita la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="cecfd-377">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="cecfd-378">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-378">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="cecfd-379">La mayoría de versiones de Ubuntu incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="cecfd-379">Most versions of Ubuntu include an earlier version of libgdiplus.</span></span> <span data-ttu-id="cecfd-380">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="cecfd-380">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="cecfd-381">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="cecfd-381">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

### <a name="centos-and-fedora"></a><span data-ttu-id="cecfd-382">CentOS y Fedora</span><span class="sxs-lookup"><span data-stu-id="cecfd-382">CentOS and Fedora</span></span>

<span data-ttu-id="cecfd-383">Las distribuciones de CentOS necesitan tener instaladas las siguientes bibliotecas:</span><span class="sxs-lookup"><span data-stu-id="cecfd-383">CentOS distributions require the following libraries installed:</span></span>

- <span data-ttu-id="cecfd-384">lttng-ust</span><span class="sxs-lookup"><span data-stu-id="cecfd-384">lttng-ust</span></span>
- <span data-ttu-id="cecfd-385">libcurl</span><span class="sxs-lookup"><span data-stu-id="cecfd-385">libcurl</span></span>
- <span data-ttu-id="cecfd-386">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="cecfd-386">openssl-libs</span></span>
- <span data-ttu-id="cecfd-387">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="cecfd-387">krb5-libs</span></span>
- <span data-ttu-id="cecfd-388">libicu</span><span class="sxs-lookup"><span data-stu-id="cecfd-388">libicu</span></span>
- <span data-ttu-id="cecfd-389">zlib</span><span class="sxs-lookup"><span data-stu-id="cecfd-389">zlib</span></span>

<span data-ttu-id="cecfd-390">Usuarios de Fedora: Si la versión de OpenSSL es la 1.1 o una posterior, es necesario instalar **compat-openssl10**.</span><span class="sxs-lookup"><span data-stu-id="cecfd-390">Fedora users: If your OpenSSL's version >= 1.1, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="cecfd-391">En el caso de .NET Core 2.0, también se necesitan las dependencias siguientes:</span><span class="sxs-lookup"><span data-stu-id="cecfd-391">For .NET Core 2.0, the following dependencies are also required:</span></span>

- <span data-ttu-id="cecfd-392">libunwind</span><span class="sxs-lookup"><span data-stu-id="cecfd-392">libunwind</span></span>
- <span data-ttu-id="cecfd-393">libuuid</span><span class="sxs-lookup"><span data-stu-id="cecfd-393">libuuid</span></span>

<span data-ttu-id="cecfd-394">Para obtener más información sobre las dependencias, vea [Aplicaciones de Linux independientes](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-394">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="cecfd-395">En el caso de las aplicaciones de .NET Core que utilizan el ensamblado *System.Drawing.Common*, también se necesitará la dependencia siguiente:</span><span class="sxs-lookup"><span data-stu-id="cecfd-395">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- <span data-ttu-id="cecfd-396">libgdiplus (versión 6.0.1 o posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-396">libgdiplus (version 6.0.1 or later)</span></span>

> [!WARNING]
> <span data-ttu-id="cecfd-397">La mayoría de versiones de CentOS incluyen una versión anterior de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="cecfd-397">Most versions of CentOS and Fedora include an earlier version of libgdiplus.</span></span> <span data-ttu-id="cecfd-398">Puede instalar una versión reciente de libgdiplus al agregar el repositorio Mono al sistema.</span><span class="sxs-lookup"><span data-stu-id="cecfd-398">You can install a recent version of libgdiplus by adding the Mono repository to your system.</span></span> <span data-ttu-id="cecfd-399">Para obtener más información, vea <https://www.mono-project.com/download/stable/>.</span><span class="sxs-lookup"><span data-stu-id="cecfd-399">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

::: zone-end

::: zone pivot="os-macos"

<span data-ttu-id="cecfd-400">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="cecfd-400">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="cecfd-401">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="cecfd-401">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="cecfd-402">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="cecfd-402">.NET Core Version</span></span> | <span data-ttu-id="cecfd-403">macOS</span><span class="sxs-lookup"><span data-stu-id="cecfd-403">macOS</span></span>                 | <span data-ttu-id="cecfd-404">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="cecfd-404">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="cecfd-405">3.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-405">3.1</span></span>               | <span data-ttu-id="cecfd-406">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-406">High Sierra (10.13+)</span></span>  | <span data-ttu-id="cecfd-407">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-407">x64</span></span> | [<span data-ttu-id="cecfd-408">Más información</span><span class="sxs-lookup"><span data-stu-id="cecfd-408">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="cecfd-409">3.0</span><span class="sxs-lookup"><span data-stu-id="cecfd-409">3.0</span></span>               | <span data-ttu-id="cecfd-410">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-410">High Sierra (10.13+)</span></span>  | <span data-ttu-id="cecfd-411">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-411">x64</span></span> | [<span data-ttu-id="cecfd-412">Más información</span><span class="sxs-lookup"><span data-stu-id="cecfd-412">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="cecfd-413">2.2</span><span class="sxs-lookup"><span data-stu-id="cecfd-413">2.2</span></span>               | <span data-ttu-id="cecfd-414">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-414">Sierra (10.12+)</span></span>       | <span data-ttu-id="cecfd-415">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-415">x64</span></span> | [<span data-ttu-id="cecfd-416">Más información</span><span class="sxs-lookup"><span data-stu-id="cecfd-416">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="cecfd-417">2.1</span><span class="sxs-lookup"><span data-stu-id="cecfd-417">2.1</span></span>               | <span data-ttu-id="cecfd-418">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="cecfd-418">Sierra (10.12+)</span></span>       | <span data-ttu-id="cecfd-419">x64</span><span class="sxs-lookup"><span data-stu-id="cecfd-419">x64</span></span> | [<span data-ttu-id="cecfd-420">Más información</span><span class="sxs-lookup"><span data-stu-id="cecfd-420">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="cecfd-421">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="cecfd-421">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="cecfd-422">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="cecfd-422">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="cecfd-423">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="cecfd-423">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="cecfd-424">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="cecfd-424">Prior released versions aren't notarized.</span></span> <span data-ttu-id="cecfd-425">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="cecfd-425">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="cecfd-427">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-427">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="cecfd-428">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="cecfd-428">libgdiplus</span></span>

<span data-ttu-id="cecfd-429">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="cecfd-429">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="cecfd-430">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="cecfd-430">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="cecfd-431">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="cecfd-431">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

::: zone-end

## <a name="next-steps"></a><span data-ttu-id="cecfd-432">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="cecfd-432">Next steps</span></span>

- <span data-ttu-id="cecfd-433">Para desarrollar y ejecutar aplicaciones, instale el [SDK de .NET Core](sdk.md), que incluye el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cecfd-433">To develop and run apps, install the [.NET Core SDK](sdk.md) (includes the runtime).</span></span>
- <span data-ttu-id="cecfd-434">Para ejecutar las aplicaciones que han creado otros usuarios, instale el [entorno de ejecución de .NET Core](runtime.md).</span><span class="sxs-lookup"><span data-stu-id="cecfd-434">To run apps others have created, install the [.NET Core runtime](runtime.md).</span></span>
