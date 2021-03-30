---
title: Instalación de .NET en Windows
description: Obtenga información sobre las versiones de Windows en las que puede instalar .NET.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9b0c5c2ea26546a142029b730dfd38923231bae4
ms.sourcegitcommit: c7f0beaa2bd66ebca86362ca17d673f7e8256ca6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2021
ms.locfileid: "104873749"
---
# <a name="install-net-on-windows"></a><span data-ttu-id="21680-103">Instalación de .NET en Windows</span><span class="sxs-lookup"><span data-stu-id="21680-103">Install .NET on Windows</span></span>

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

<span data-ttu-id="21680-107">En este artículo obtendrá información sobre cómo instalar .NET en Windows.</span><span class="sxs-lookup"><span data-stu-id="21680-107">In this article, you'll learn how to install .NET on Windows.</span></span> <span data-ttu-id="21680-108">.NET está formado por el entorno de ejecución y el SDK.</span><span class="sxs-lookup"><span data-stu-id="21680-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="21680-109">El entorno de ejecución se usa para ejecutar una aplicación de .NET, y puede o no incluirse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21680-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="21680-110">El SDK se usa para crear aplicaciones y bibliotecas de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="21680-111">El entorno de ejecución de .NET siempre se instala con el SDK.</span><span class="sxs-lookup"><span data-stu-id="21680-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="21680-112">La versión más reciente de .NET es la 5.0.</span><span class="sxs-lookup"><span data-stu-id="21680-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="21680-113">Descarga de .NET</span><span class="sxs-lookup"><span data-stu-id="21680-113">Download .NET</span></span>](https://dotnet.microsoft.com/download/dotnet)

## <a name="supported-releases"></a><span data-ttu-id="21680-114">Versiones compatibles</span><span class="sxs-lookup"><span data-stu-id="21680-114">Supported releases</span></span>

<span data-ttu-id="21680-115">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de Windows en las que se admiten.</span><span class="sxs-lookup"><span data-stu-id="21680-115">The following table is a list of currently supported .NET releases and the versions of Windows they're supported on.</span></span> <span data-ttu-id="21680-116">Estas versiones siguen siendo compatibles hasta que la versión de [.NET llega al fin del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) o la versión de [Windows llega al final del ciclo de vida](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="21680-116">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Windows reaches end-of-life](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span></span>

<span data-ttu-id="21680-117">Las fechas de fin de servicio de Windows 10 están segmentadas por edición.</span><span class="sxs-lookup"><span data-stu-id="21680-117">Windows 10 versions end-of-service dates are segmented by edition.</span></span> <span data-ttu-id="21680-118">En la tabla que hay a continuación solo se tienen en cuenta las ediciones **Home**, **Pro**, **Pro Education** y **Pro for Workstations**.</span><span class="sxs-lookup"><span data-stu-id="21680-118">Only **Home**, **Pro**, **Pro Education**, and **Pro for Workstations** editions are considered in the following table.</span></span> <span data-ttu-id="21680-119">Para ver detalles específicos, consulte la [hoja informativa sobre el ciclo de vida de Windows](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet).</span><span class="sxs-lookup"><span data-stu-id="21680-119">Check the [Windows lifecycle fact sheet](https://support.microsoft.com/help/13853/windows-lifecycle-fact-sheet) for specific details.</span></span>

> [!TIP]
> <span data-ttu-id="21680-120">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-120">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-121">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="21680-121">Operating System</span></span>            | <span data-ttu-id="21680-122">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21680-122">.NET Core 2.1</span></span> | <span data-ttu-id="21680-123">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="21680-123">.NET Core 3.1</span></span> | <span data-ttu-id="21680-124">.NET 5</span><span class="sxs-lookup"><span data-stu-id="21680-124">.NET 5</span></span> |
|-----------------------------|---------------|---------------|--------|
| <span data-ttu-id="21680-125">Windows 10 / Windows Server, versión 20H2</span><span class="sxs-lookup"><span data-stu-id="21680-125">Windows 10 / Windows Server, Version 20H2</span></span>    | <span data-ttu-id="21680-126">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-126">✔️</span></span>           | <span data-ttu-id="21680-127">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-127">✔️</span></span>            | <span data-ttu-id="21680-128">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-128">✔️</span></span>    |
| <span data-ttu-id="21680-129">Windows 10 / Windows Server, versión 2004</span><span class="sxs-lookup"><span data-stu-id="21680-129">Windows 10 / Windows Server, Version 2004</span></span>    | <span data-ttu-id="21680-130">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-130">✔️</span></span>           | <span data-ttu-id="21680-131">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-131">✔️</span></span>            | <span data-ttu-id="21680-132">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-132">✔️</span></span>    |
| <span data-ttu-id="21680-133">Windows 10 / Windows Server, versión 1909</span><span class="sxs-lookup"><span data-stu-id="21680-133">Windows 10 / Windows Server, Version 1909</span></span>    | <span data-ttu-id="21680-134">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-134">✔️</span></span>           | <span data-ttu-id="21680-135">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-135">✔️</span></span>            | <span data-ttu-id="21680-136">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-136">✔️</span></span>    |
| <span data-ttu-id="21680-137">Windows 10 / Windows Server, versión 1903</span><span class="sxs-lookup"><span data-stu-id="21680-137">Windows 10 / Windows Server, Version 1903</span></span>    | <span data-ttu-id="21680-138">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-138">✔️</span></span>           | <span data-ttu-id="21680-139">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-139">✔️</span></span>            | <span data-ttu-id="21680-140">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-140">✔️</span></span>    |
| <span data-ttu-id="21680-141">Windows 10, versión 1809</span><span class="sxs-lookup"><span data-stu-id="21680-141">Windows 10, Version 1809</span></span>    | <span data-ttu-id="21680-142">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-142">✔️</span></span>           | <span data-ttu-id="21680-143">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-143">✔️</span></span>            | <span data-ttu-id="21680-144">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-144">✔️</span></span>    |
| <span data-ttu-id="21680-145"> Windows 10, versión 1803</span><span class="sxs-lookup"><span data-stu-id="21680-145">Windows 10, Version 1803</span></span>    | <span data-ttu-id="21680-146">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-146">✔️</span></span>           | <span data-ttu-id="21680-147">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-147">✔️</span></span>            | <span data-ttu-id="21680-148">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-148">✔️</span></span>    |
| <span data-ttu-id="21680-149">Windows 10, versión 1709</span><span class="sxs-lookup"><span data-stu-id="21680-149">Windows 10, Version 1709</span></span>    | <span data-ttu-id="21680-150">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-150">✔️</span></span>           | <span data-ttu-id="21680-151">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-151">✔️</span></span>            | <span data-ttu-id="21680-152">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-152">✔️</span></span>    |
| <span data-ttu-id="21680-153">Windows 10, versión 1607</span><span class="sxs-lookup"><span data-stu-id="21680-153">Windows 10, Version 1607</span></span>    | <span data-ttu-id="21680-154">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-154">✔️</span></span>           | <span data-ttu-id="21680-155">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-155">✔️</span></span>            | <span data-ttu-id="21680-156">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-156">✔️</span></span>    |
| <span data-ttu-id="21680-157">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-157">Windows 8.1</span></span>                 | <span data-ttu-id="21680-158">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-158">✔️</span></span>           | <span data-ttu-id="21680-159">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-159">✔️</span></span>            | <span data-ttu-id="21680-160">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-160">✔️</span></span>    |
| <span data-ttu-id="21680-161">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="21680-161">Windows 7 SP1 [ESU][esu]</span></span>    | <span data-ttu-id="21680-162">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-162">✔️</span></span>           | <span data-ttu-id="21680-163">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-163">✔️</span></span>            | <span data-ttu-id="21680-164">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-164">✔️</span></span>    |
| <span data-ttu-id="21680-165">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="21680-165">Windows Server 2019</span></span><br><span data-ttu-id="21680-166">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="21680-166">Windows Server 2016</span></span><br><span data-ttu-id="21680-167">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="21680-167">Windows Server 2012 R2</span></span><br>      | <span data-ttu-id="21680-168">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-168">✔️</span></span>           | <span data-ttu-id="21680-169">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-169">✔️</span></span>            | <span data-ttu-id="21680-170">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-170">✔️</span></span>    |
| <span data-ttu-id="21680-171">Windows Server Core 2012 R2</span><span class="sxs-lookup"><span data-stu-id="21680-171">Windows Server Core 2012 R2</span></span> | <span data-ttu-id="21680-172">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-172">✔️</span></span>           | <span data-ttu-id="21680-173">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-173">✔️</span></span>            | <span data-ttu-id="21680-174">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-174">✔️</span></span>    |
| <span data-ttu-id="21680-175">Nano Server, versión 1809+</span><span class="sxs-lookup"><span data-stu-id="21680-175">Nano Server, Version 1809+</span></span>  | <span data-ttu-id="21680-176">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-176">✔️</span></span>           | <span data-ttu-id="21680-177">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-177">✔️</span></span>            | <span data-ttu-id="21680-178">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-178">✔️</span></span>    |
| <span data-ttu-id="21680-179">Nano Server, versión 1803</span><span class="sxs-lookup"><span data-stu-id="21680-179">Nano Server, Version 1803</span></span>   | <span data-ttu-id="21680-180">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-180">✔️</span></span>           | <span data-ttu-id="21680-181">✔️</span><span class="sxs-lookup"><span data-stu-id="21680-181">✔️</span></span>            | ❌    |

## <a name="unsupported-releases"></a><span data-ttu-id="21680-182">Versiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="21680-182">Unsupported releases</span></span>

<span data-ttu-id="21680-183">Las versiones siguientes de .NET ya ❌ no se admiten:</span><span class="sxs-lookup"><span data-stu-id="21680-183">The following versions of .NET are ❌ no longer supported:</span></span>

- <span data-ttu-id="21680-184">3.0</span><span class="sxs-lookup"><span data-stu-id="21680-184">3.0</span></span>
- <span data-ttu-id="21680-185">2.2</span><span class="sxs-lookup"><span data-stu-id="21680-185">2.2</span></span>
- <span data-ttu-id="21680-186">2.0</span><span class="sxs-lookup"><span data-stu-id="21680-186">2.0</span></span>

## <a name="runtime-information"></a><span data-ttu-id="21680-187">Información en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="21680-187">Runtime information</span></span>

<span data-ttu-id="21680-188">El entorno de ejecución se usa para ejecutar aplicaciones creadas con .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-188">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="21680-189">Cuando un autor publica una aplicación, puede incluir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21680-189">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="21680-190">Si no lo hace, el usuario elige si quiere instalar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21680-190">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="21680-191">Hay tres entornos de ejecución distintos que se pueden instalar en Windows:</span><span class="sxs-lookup"><span data-stu-id="21680-191">There are three different runtimes you can install on Windows:</span></span>

- <span data-ttu-id="21680-192">*Entorno de ejecución de ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="21680-192">*ASP.NET Core runtime*</span></span>\
  <span data-ttu-id="21680-193">Ejecuta aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="21680-193">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="21680-194">Incluye el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-194">Includes the .NET runtime.</span></span>

- <span data-ttu-id="21680-195">*Entorno de ejecución de escritorio*</span><span class="sxs-lookup"><span data-stu-id="21680-195">*Desktop runtime*</span></span>\
  <span data-ttu-id="21680-196">Ejecuta aplicaciones de escritorio WPF y Windows Forms de .NET para Windows.</span><span class="sxs-lookup"><span data-stu-id="21680-196">Runs .NET WPF and Windows Forms desktop apps for Windows.</span></span> <span data-ttu-id="21680-197">Incluye el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-197">Includes the .NET runtime.</span></span>

- <span data-ttu-id="21680-198">*Entorno de ejecución de .NET*</span><span class="sxs-lookup"><span data-stu-id="21680-198">*.NET runtime*</span></span>\
  <span data-ttu-id="21680-199">Este entorno de ejecución es el más sencillo y no incluye ningún otro.</span><span class="sxs-lookup"><span data-stu-id="21680-199">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="21680-200">Se recomienda encarecidamente instalar el *entorno de ejecución de ASP.NET Core* y el *entorno de ejecución de escritorio* para conseguir la mejor compatibilidad con las aplicaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-200">It's highly recommended that you install both *ASP.NET Core runtime* and *Desktop runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="21680-201">Descarga del entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="21680-201">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet)

## <a name="sdk-information"></a><span data-ttu-id="21680-202">Información del SDK</span><span class="sxs-lookup"><span data-stu-id="21680-202">SDK information</span></span>

<span data-ttu-id="21680-203">El SDK se usa para compilar y publicar aplicaciones y bibliotecas de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-203">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="21680-204">La instalación del SDK incluye los tres [entornos de ejecución](#runtime-information): el de ASP.NET Core, el de escritorio y el de .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-204">Installing the SDK includes all three [runtimes](#runtime-information): ASP.NET Core, Desktop, and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="21680-205">Dependencias</span><span class="sxs-lookup"><span data-stu-id="21680-205">Dependencies</span></span>

<!-- markdownlint-disable MD025 -->
<!-- markdownlint-disable MD024 -->

# <a name="net-50"></a>[<span data-ttu-id="21680-206">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21680-206">.NET 5.0</span></span>](#tab/net50)

<span data-ttu-id="21680-207">Las versiones siguientes de Windows son compatibles con .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="21680-207">The following Windows versions are supported with .NET 5.0:</span></span>

> [!NOTE]
> <span data-ttu-id="21680-208">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-208">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-209">SO</span><span class="sxs-lookup"><span data-stu-id="21680-209">OS</span></span>                  | <span data-ttu-id="21680-210">Versión</span><span class="sxs-lookup"><span data-stu-id="21680-210">Version</span></span>       | <span data-ttu-id="21680-211">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="21680-211">Architectures</span></span>   |
|---------------------|---------------|-----------------|
| <span data-ttu-id="21680-212">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="21680-212">Windows 10 Client</span></span>   | <span data-ttu-id="21680-213">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-213">Version 1607+</span></span> | <span data-ttu-id="21680-214">x64, x86, ARM64</span><span class="sxs-lookup"><span data-stu-id="21680-214">x64, x86, ARM64</span></span> |
| <span data-ttu-id="21680-215">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="21680-215">Windows Client</span></span>      | <span data-ttu-id="21680-216">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-216">7 SP1+, 8.1</span></span>   | <span data-ttu-id="21680-217">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-217">x64, x86</span></span>        |
| <span data-ttu-id="21680-218">Windows Server</span><span class="sxs-lookup"><span data-stu-id="21680-218">Windows Server</span></span>      | <span data-ttu-id="21680-219">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-219">2012 R2+</span></span>      | <span data-ttu-id="21680-220">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-220">x64, x86</span></span>        |
| <span data-ttu-id="21680-221">Windows Server Core</span><span class="sxs-lookup"><span data-stu-id="21680-221">Windows Server Core</span></span> | <span data-ttu-id="21680-222">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-222">2012 R2+</span></span>      | <span data-ttu-id="21680-223">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-223">x64, x86</span></span>        |
| <span data-ttu-id="21680-224">Nano Server</span><span class="sxs-lookup"><span data-stu-id="21680-224">Nano Server</span></span>         | <span data-ttu-id="21680-225">Versión 1809 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-225">Version 1809+</span></span> | <span data-ttu-id="21680-226">x64</span><span class="sxs-lookup"><span data-stu-id="21680-226">x64</span></span>             |

<span data-ttu-id="21680-227">Para obtener más información sobre los sistemas operativos compatibles con .NET 5.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET 5.0](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="21680-227">For more information about .NET 5.0 supported operating systems, distributions, and lifecycle policy, see [.NET 5.0 Supported OS Versions](https://github.com/dotnet/core/blob/main/release-notes/5.0/5.0-supported-os.md).</span></span>

# <a name="net-core-31"></a>[<span data-ttu-id="21680-228">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="21680-228">.NET Core 3.1</span></span>](#tab/netcore31)

<span data-ttu-id="21680-229">Las versiones siguientes de Windows son compatibles con .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="21680-229">The following Windows versions are supported with .NET Core 3.1:</span></span>

> [!NOTE]
> <span data-ttu-id="21680-230">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-230">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-231">SO</span><span class="sxs-lookup"><span data-stu-id="21680-231">OS</span></span>                            | <span data-ttu-id="21680-232">Versión</span><span class="sxs-lookup"><span data-stu-id="21680-232">Version</span></span>                        | <span data-ttu-id="21680-233">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="21680-233">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="21680-234">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="21680-234">Windows Client</span></span>                | <span data-ttu-id="21680-235">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-235">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="21680-236">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-236">x64, x86</span></span>        |
| <span data-ttu-id="21680-237">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="21680-237">Windows 10 Client</span></span>             | <span data-ttu-id="21680-238">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-238">Version 1607+</span></span>                  | <span data-ttu-id="21680-239">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-239">x64, x86</span></span>        |
| <span data-ttu-id="21680-240">Windows Server</span><span class="sxs-lookup"><span data-stu-id="21680-240">Windows Server</span></span>                | <span data-ttu-id="21680-241">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-241">2012 R2+</span></span>                       | <span data-ttu-id="21680-242">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-242">x64, x86</span></span>        |
| <span data-ttu-id="21680-243">Nano Server</span><span class="sxs-lookup"><span data-stu-id="21680-243">Nano Server</span></span>                   | <span data-ttu-id="21680-244">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-244">Version 1803+</span></span>                  | <span data-ttu-id="21680-245">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="21680-245">x64, ARM32</span></span>      |

<span data-ttu-id="21680-246">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.1](https://github.com/dotnet/core/blob/main/release-notes/3.1/3.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="21680-246">For more information about .NET Core 3.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.1 Supported OS Versions](https://github.com/dotnet/core/blob/main/release-notes/3.1/3.1-supported-os.md).</span></span>

# <a name="net-core-30"></a>[<span data-ttu-id="21680-247">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="21680-247">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="21680-248">*.NET Core 3.0 no se admite ❌ actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="21680-248">*.NET Core 3.0 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="21680-249">Las versiones siguientes de Windows son compatibles con .NET Core 3.0:</span><span class="sxs-lookup"><span data-stu-id="21680-249">The following Windows versions are supported with .NET Core 3.0:</span></span>

> [!NOTE]
> <span data-ttu-id="21680-250">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-250">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-251">SO</span><span class="sxs-lookup"><span data-stu-id="21680-251">OS</span></span>                            | <span data-ttu-id="21680-252">Versión</span><span class="sxs-lookup"><span data-stu-id="21680-252">Version</span></span>                        | <span data-ttu-id="21680-253">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="21680-253">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="21680-254">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="21680-254">Windows Client</span></span>                | <span data-ttu-id="21680-255">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-255">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="21680-256">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-256">x64, x86</span></span>        |
| <span data-ttu-id="21680-257">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="21680-257">Windows 10 Client</span></span>             | <span data-ttu-id="21680-258">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-258">Version 1607+</span></span>                  | <span data-ttu-id="21680-259">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-259">x64, x86</span></span>        |
| <span data-ttu-id="21680-260">Windows Server</span><span class="sxs-lookup"><span data-stu-id="21680-260">Windows Server</span></span>                | <span data-ttu-id="21680-261">2012 R2 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-261">2012 R2+</span></span>                       | <span data-ttu-id="21680-262">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-262">x64, x86</span></span>        |
| <span data-ttu-id="21680-263">Nano Server</span><span class="sxs-lookup"><span data-stu-id="21680-263">Nano Server</span></span>                   | <span data-ttu-id="21680-264">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-264">Version 1803+</span></span>                  | <span data-ttu-id="21680-265">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="21680-265">x64, ARM32</span></span>      |

<span data-ttu-id="21680-266">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 3.0, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 3.0](https://github.com/dotnet/core/blob/main/release-notes/3.0/3.0-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="21680-266">For more information about .NET Core 3.0 supported operating systems, distributions, and lifecycle policy, see [.NET Core 3.0 Supported OS Versions](https://github.com/dotnet/core/blob/main/release-notes/3.0/3.0-supported-os.md).</span></span>

# <a name="net-core-22"></a>[<span data-ttu-id="21680-267">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="21680-267">.NET Core 2.2</span></span>](#tab/netcore22)

<span data-ttu-id="21680-268">*.NET Core 2.2 no se admite ❌ actualmente. Para más información, consulte la [directiva de soporte técnico de .NET Core](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span><span class="sxs-lookup"><span data-stu-id="21680-268">*.NET Core 2.2 is currently ❌ out of support. For more information, see the [.NET Core Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).*</span></span>

<span data-ttu-id="21680-269">Las versiones siguientes de Windows son compatibles con .NET Core 2.2:</span><span class="sxs-lookup"><span data-stu-id="21680-269">The following Windows versions are supported with .NET Core 2.2:</span></span>

> [!NOTE]
> <span data-ttu-id="21680-270">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-270">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-271">SO</span><span class="sxs-lookup"><span data-stu-id="21680-271">OS</span></span>                            | <span data-ttu-id="21680-272">Versión</span><span class="sxs-lookup"><span data-stu-id="21680-272">Version</span></span>                        | <span data-ttu-id="21680-273">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="21680-273">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="21680-274">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="21680-274">Windows Client</span></span>                | <span data-ttu-id="21680-275">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-275">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="21680-276">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-276">x64, x86</span></span>        |
| <span data-ttu-id="21680-277">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="21680-277">Windows 10 Client</span></span>             | <span data-ttu-id="21680-278">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-278">Version 1607+</span></span>                  | <span data-ttu-id="21680-279">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-279">x64, x86</span></span>        |
| <span data-ttu-id="21680-280">Windows Server</span><span class="sxs-lookup"><span data-stu-id="21680-280">Windows Server</span></span>                | <span data-ttu-id="21680-281">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-281">2008 R2 SP1+</span></span>                   | <span data-ttu-id="21680-282">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-282">x64, x86</span></span>        |
| <span data-ttu-id="21680-283">Nano Server</span><span class="sxs-lookup"><span data-stu-id="21680-283">Nano Server</span></span>                   | <span data-ttu-id="21680-284">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-284">Version 1803+</span></span>                   | <span data-ttu-id="21680-285">x64, ARM32</span><span class="sxs-lookup"><span data-stu-id="21680-285">x64, ARM32</span></span>      |

<span data-ttu-id="21680-286">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.2, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.2](https://github.com/dotnet/core/blob/main/release-notes/2.2/2.2-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="21680-286">For more information about .NET Core 2.2 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.2 Supported OS Versions](https://github.com/dotnet/core/blob/main/release-notes/2.2/2.2-supported-os.md).</span></span>

# <a name="net-core-21"></a>[<span data-ttu-id="21680-287">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21680-287">.NET Core 2.1</span></span>](#tab/netcore21)

<span data-ttu-id="21680-288">Las versiones siguientes de Windows son compatibles con .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="21680-288">The following Windows versions are supported with .NET Core 2.1:</span></span>

> [!NOTE]
> <span data-ttu-id="21680-289">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="21680-289">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="21680-290">SO</span><span class="sxs-lookup"><span data-stu-id="21680-290">OS</span></span>                            | <span data-ttu-id="21680-291">Versión</span><span class="sxs-lookup"><span data-stu-id="21680-291">Version</span></span>                        | <span data-ttu-id="21680-292">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="21680-292">Architectures</span></span>   |
| ----------------------------- | ------------------------------ | --------------- |
| <span data-ttu-id="21680-293">Cliente Windows</span><span class="sxs-lookup"><span data-stu-id="21680-293">Windows Client</span></span>                | <span data-ttu-id="21680-294">7 SP1 y posteriores, y 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-294">7 SP1+, 8.1</span></span>                    | <span data-ttu-id="21680-295">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-295">x64, x86</span></span>        |
| <span data-ttu-id="21680-296">Cliente de Windows 10</span><span class="sxs-lookup"><span data-stu-id="21680-296">Windows 10 Client</span></span>             | <span data-ttu-id="21680-297">Versión 1607 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-297">Version 1607+</span></span>                  | <span data-ttu-id="21680-298">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-298">x64, x86</span></span>        |
| <span data-ttu-id="21680-299">Windows Server</span><span class="sxs-lookup"><span data-stu-id="21680-299">Windows Server</span></span>                | <span data-ttu-id="21680-300">2008 R2 SP1 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-300">2008 R2 SP1+</span></span>                   | <span data-ttu-id="21680-301">x64, x86</span><span class="sxs-lookup"><span data-stu-id="21680-301">x64, x86</span></span>        |
| <span data-ttu-id="21680-302">Nano Server</span><span class="sxs-lookup"><span data-stu-id="21680-302">Nano Server</span></span>                   | <span data-ttu-id="21680-303">Versión 1803 y posteriores</span><span class="sxs-lookup"><span data-stu-id="21680-303">Version 1803+</span></span>                  | <span data-ttu-id="21680-304">x64,</span><span class="sxs-lookup"><span data-stu-id="21680-304">x64,</span></span>            |

<span data-ttu-id="21680-305">Para obtener más información sobre los sistemas operativos compatibles con .NET Core 2.1, las distribuciones y la directiva del ciclo de vida, vea [Versiones de SO compatibles con .NET Core 2.1](https://github.com/dotnet/core/blob/main/release-notes/2.1/2.1-supported-os.md).</span><span class="sxs-lookup"><span data-stu-id="21680-305">For more information about .NET Core 2.1 supported operating systems, distributions, and lifecycle policy, see [.NET Core 2.1 Supported OS Versions](https://github.com/dotnet/core/blob/main/release-notes/2.1/2.1-supported-os.md).</span></span>

### <a name="offline-install-for-windows-7"></a><span data-ttu-id="21680-306">Instalación sin conexión para Windows 7</span><span class="sxs-lookup"><span data-stu-id="21680-306">Offline install for Windows 7</span></span>

<span data-ttu-id="21680-307">Al realizar una instalación sin conexión para .NET Core 2.1 en Windows 7, primero deberá asegurarse de que se ha instalado en la máquina de destino la versión más reciente de [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm).</span><span class="sxs-lookup"><span data-stu-id="21680-307">When doing an offline install for .NET Core 2.1 on Windows 7, you'll first need to make sure that the latest [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) has been installed on the target machine.</span></span>

<span data-ttu-id="21680-308">La herramienta _certmgr.exe_ puede automatizar la instalación de un certificado y se obtiene de Visual Studio o Windows SDK.</span><span class="sxs-lookup"><span data-stu-id="21680-308">The _certmgr.exe_ tool can automate installing a certificate and is obtained from Visual Studio or the Windows SDK.</span></span> <span data-ttu-id="21680-309">El siguiente comando se usa para instalar el certificado antes de ejecutar el instalador de .NET Core 2.1:</span><span class="sxs-lookup"><span data-stu-id="21680-309">The following command is used to install the certificate before running the .NET Core 2.1 installer:</span></span>

```console
certmgr.exe /add MicRooCerAut2011_2011_03_22.crt /s /r localMachine root
```

<span data-ttu-id="21680-310">Asegúrese de revisar las dependencias necesarias para [Windows 7 a continuación](#additional-deps).</span><span class="sxs-lookup"><span data-stu-id="21680-310">Be sure to review the dependencies required for [Windows 7 below](#additional-deps).</span></span>

---

<!-- markdownlint-disable MD001 -->

### <a name="windows-7--vista--81--server-2008-r2--server-2012-r2"></a><a name="additional-deps"></a> <span data-ttu-id="21680-311">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="21680-311">Windows 7 / Vista / 8.1 / Server 2008 R2 / Server 2012 R2</span></span>

<span data-ttu-id="21680-312">Se necesitan más dependencias en caso de que se instale el SDK o el entorno de ejecución de .NET en las versiones siguientes de Windows:</span><span class="sxs-lookup"><span data-stu-id="21680-312">More dependencies are required if you're installing the .NET SDK or runtime on the following Windows versions:</span></span>

| <span data-ttu-id="21680-313">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="21680-313">Operating System</span></span>         | <span data-ttu-id="21680-314">Prerrequisitos</span><span class="sxs-lookup"><span data-stu-id="21680-314">Prerequisites</span></span>                                                                    |
|--------------------------|----------------------------------------------------------------------------------|
| <span data-ttu-id="21680-315">Windows 7 SP1 [ESU][esu]</span><span class="sxs-lookup"><span data-stu-id="21680-315">Windows 7 SP1 [ESU][esu]</span></span> | <span data-ttu-id="21680-316">- Microsoft Visual C++ 2015-2019 Redistributable [64 bits][vcc64] / [32 bits][vcc32]</span><span class="sxs-lookup"><span data-stu-id="21680-316">- Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> <br> <span data-ttu-id="21680-317">- KB3063858 [64 bits][kb64] / [32 bits][kb32]</span><span class="sxs-lookup"><span data-stu-id="21680-317">- KB3063858 [64-bit][kb64] / [32-bit][kb32]</span></span> <br> <span data-ttu-id="21680-318">- [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) (solo instalador sin conexión de .NET Core 2.1)</span><span class="sxs-lookup"><span data-stu-id="21680-318">- [Microsoft Root Certificate Authority 2011](https://www.microsoft.com/pkiops/Docs/Repository.htm) (.NET Core 2.1 offline installer only)</span></span> |
| <span data-ttu-id="21680-319">Windows Vista SP2</span><span class="sxs-lookup"><span data-stu-id="21680-319">Windows Vista SP 2</span></span>       | <span data-ttu-id="21680-320">Microsoft Visual C++ 2015-2019 Redistributable [64 bits][vcc64] / [32 bits][vcc32]</span><span class="sxs-lookup"><span data-stu-id="21680-320">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="21680-321">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="21680-321">Windows 8.1</span></span>              | <span data-ttu-id="21680-322">Microsoft Visual C++ 2015-2019 Redistributable [64 bits][vcc64] / [32 bits][vcc32]</span><span class="sxs-lookup"><span data-stu-id="21680-322">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="21680-323">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="21680-323">Windows Server 2008 R2</span></span>   | <span data-ttu-id="21680-324">Microsoft Visual C++ 2015-2019 Redistributable [64 bits][vcc64] / [32 bits][vcc32]</span><span class="sxs-lookup"><span data-stu-id="21680-324">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |
| <span data-ttu-id="21680-325">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="21680-325">Windows Server 2012 R2</span></span>   | <span data-ttu-id="21680-326">Microsoft Visual C++ 2015-2019 Redistributable [64 bits][vcc64] / [32 bits][vcc32]</span><span class="sxs-lookup"><span data-stu-id="21680-326">Microsoft Visual C++ 2015-2019 Redistributable [64-bit][vcc64] / [32-bit][vcc32]</span></span> |

<span data-ttu-id="21680-327">Los requisitos anteriores también son necesarios si se encuentra con un error relacionado con uno de los archivos DLL siguientes:</span><span class="sxs-lookup"><span data-stu-id="21680-327">The previous requirements are also required if you receive an error related to either of the following dlls:</span></span>

- <span data-ttu-id="21680-328">*api-ms-win-crt-runtime-l1-1-0.dll*</span><span class="sxs-lookup"><span data-stu-id="21680-328">*api-ms-win-crt-runtime-l1-1-0.dll*</span></span>
- <span data-ttu-id="21680-329">*api-ms-win-cor-timezone-l1-1-0.dll*</span><span class="sxs-lookup"><span data-stu-id="21680-329">*api-ms-win-cor-timezone-l1-1-0.dll*</span></span>
- <span data-ttu-id="21680-330">*hostfxr.dll*</span><span class="sxs-lookup"><span data-stu-id="21680-330">*hostfxr.dll*</span></span>

## <a name="install-with-powershell-automation"></a><span data-ttu-id="21680-331">Instalación mediante la automatización de PowerShell</span><span class="sxs-lookup"><span data-stu-id="21680-331">Install with PowerShell automation</span></span>

<span data-ttu-id="21680-332">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización de CI y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21680-332">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for CI automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="21680-333">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="21680-333">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="21680-334">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="21680-334">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="21680-335">Puede elegir una versión concreta especificando el modificador `Channel`.</span><span class="sxs-lookup"><span data-stu-id="21680-335">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="21680-336">Incluya el modificador `Runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21680-336">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="21680-337">De lo contrario, el script instala el SDK.</span><span class="sxs-lookup"><span data-stu-id="21680-337">Otherwise, the script installs the SDK.</span></span>

```powershell
dotnet-install.ps1 -Channel 5.0 -Runtime aspnetcore
```

<span data-ttu-id="21680-338">Instale el SDK omitiendo el modificador `-Runtime`.</span><span class="sxs-lookup"><span data-stu-id="21680-338">Install the SDK by omitting the `-Runtime` switch.</span></span> <span data-ttu-id="21680-339">El modificador `-Channel` de este ejemplo está establecido en `Current`, con lo que se instala la versión admitida más reciente.</span><span class="sxs-lookup"><span data-stu-id="21680-339">The `-Channel` switch is set in this example to `Current`, which installs the latest supported version.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

## <a name="install-with-visual-studio"></a><span data-ttu-id="21680-340">Instalación con Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21680-340">Install with Visual Studio</span></span>

<span data-ttu-id="21680-341">Si usa Visual Studio para desarrollar aplicaciones de .NET, en la tabla siguiente se describe la versión mínima necesaria de Visual Studio, en función de la versión del SDK de .NET de destino.</span><span class="sxs-lookup"><span data-stu-id="21680-341">If you're using Visual Studio to develop .NET apps, the following table describes the minimum required version of Visual Studio based on the target .NET SDK version.</span></span>

| <span data-ttu-id="21680-342">Versión de SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="21680-342">.NET SDK version</span></span>      | <span data-ttu-id="21680-343">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="21680-343">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="21680-344">5.0</span><span class="sxs-lookup"><span data-stu-id="21680-344">5.0</span></span>                   | <span data-ttu-id="21680-345">Visual Studio 2019, versión 16.8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="21680-345">Visual Studio 2019 version 16.8 or higher.</span></span> |
| <span data-ttu-id="21680-346">3.1</span><span class="sxs-lookup"><span data-stu-id="21680-346">3.1</span></span>                   | <span data-ttu-id="21680-347">Visual Studio 2019, versión 16.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="21680-347">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="21680-348">3.0</span><span class="sxs-lookup"><span data-stu-id="21680-348">3.0</span></span>                   | <span data-ttu-id="21680-349">Visual Studio 2019, versión 16.3 o posterior.</span><span class="sxs-lookup"><span data-stu-id="21680-349">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="21680-350">2.2</span><span class="sxs-lookup"><span data-stu-id="21680-350">2.2</span></span>                   | <span data-ttu-id="21680-351">Visual Studio 2017, versión 15.9 o posterior.</span><span class="sxs-lookup"><span data-stu-id="21680-351">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="21680-352">2.1</span><span class="sxs-lookup"><span data-stu-id="21680-352">2.1</span></span>                   | <span data-ttu-id="21680-353">Visual Studio 2017, versión 15.7 o posterior.</span><span class="sxs-lookup"><span data-stu-id="21680-353">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="21680-354">Si ya tiene Visual Studio instalado, puede comprobar la versión siguiendo los pasos que se detallan a continuación.</span><span class="sxs-lookup"><span data-stu-id="21680-354">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="21680-355">Abra Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="21680-355">Open Visual Studio.</span></span>
01. <span data-ttu-id="21680-356">Seleccione **Ayuda** > **Acerca de Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="21680-356">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="21680-357">Lea el número de versión en el cuadro de diálogo **Acerca de**.</span><span class="sxs-lookup"><span data-stu-id="21680-357">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="21680-358">Visual Studio puede instalar el SDK y el entorno de ejecución de .NET más recientes.</span><span class="sxs-lookup"><span data-stu-id="21680-358">Visual Studio can install the latest .NET SDK and runtime.</span></span>

> [!div class="button"]
> <span data-ttu-id="21680-359">[Descargue Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="21680-359">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="21680-360">Selección de una carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="21680-360">Select a workload</span></span>

<span data-ttu-id="21680-361">Al instalar o modificar Visual Studio, seleccione una de las cargas de trabajo siguientes o más, en función del tipo de aplicación que quiera compilar:</span><span class="sxs-lookup"><span data-stu-id="21680-361">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="21680-362">La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.</span><span class="sxs-lookup"><span data-stu-id="21680-362">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="21680-363">La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="21680-363">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="21680-364">La carga de trabajo **Desarrollo de Azure** en la sección **Web y nube**.</span><span class="sxs-lookup"><span data-stu-id="21680-364">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="21680-365">La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Móviles y de escritorio**.</span><span class="sxs-lookup"><span data-stu-id="21680-365">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="21680-366">[![Visual Studio 2019 para Windows con la carga de trabajo de .NET Core](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="21680-366">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="21680-367">Instalación junto con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="21680-367">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="21680-368">Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="21680-368">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="21680-369">Visual Studio Code está disponible para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="21680-369">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="21680-370">Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.</span><span class="sxs-lookup"><span data-stu-id="21680-370">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="21680-371">[Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="21680-371">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="21680-372">[Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet).</span><span class="sxs-lookup"><span data-stu-id="21680-372">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet).</span></span>
01. <span data-ttu-id="21680-373">[Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="21680-373">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="windows-installer"></a><span data-ttu-id="21680-374">Windows Installer</span><span class="sxs-lookup"><span data-stu-id="21680-374">Windows Installer</span></span>

<span data-ttu-id="21680-375">La [página de descarga](https://dotnet.microsoft.com/download/dotnet) de .NET proporciona ejecutables de Windows Installer.</span><span class="sxs-lookup"><span data-stu-id="21680-375">The [download page](https://dotnet.microsoft.com/download/dotnet) for .NET provides Windows Installer executables.</span></span>

<span data-ttu-id="21680-376">Al usar los instaladores de Windows para instalar .NET, puede personalizar la ruta de instalación estableciendo los parámetros `DOTNETHOME_X64` y `DOTNETHOME_X86`:</span><span class="sxs-lookup"><span data-stu-id="21680-376">When you use the Windows installers to install .NET, you can customize the installation path by setting the `DOTNETHOME_X64` and `DOTNETHOME_X86` parameters:</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe DOTNETHOME_X64="F:\dotnet\x64" DOTNETHOME_X86="F:\dotnet\x86"
```

<span data-ttu-id="21680-377">Si quiere instalar .NET de forma silenciosa, como en un entorno de producción o para admitir la integración continua, use las expresiones switch siguientes:</span><span class="sxs-lookup"><span data-stu-id="21680-377">If you want to install .NET silently, such as in a production environment or to support continuous integration, use the following switches:</span></span>

- `/install`\
<span data-ttu-id="21680-378">Instala .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-378">Installs .NET.</span></span>

- `/quiet`\
<span data-ttu-id="21680-379">Impide que se muestren interfaces de usuario y solicitudes.</span><span class="sxs-lookup"><span data-stu-id="21680-379">Prevents any UI and prompts from displaying.</span></span>

- `norestart`\
<span data-ttu-id="21680-380">Suprime los intentos de reinicio.</span><span class="sxs-lookup"><span data-stu-id="21680-380">Suppresses any attempts to restart.</span></span>

```console
dotnet-sdk-3.1.301-win-x64.exe /install /quiet /norestart
```

<span data-ttu-id="21680-381">Para obtener más información, vea [Opciones de la línea de comandos del instalador estándar](/windows/win32/msi/standard-installer-command-line-options).</span><span class="sxs-lookup"><span data-stu-id="21680-381">For more information, see [Standard Installer Command-Line Options](/windows/win32/msi/standard-installer-command-line-options).</span></span>

> [!TIP]
> <span data-ttu-id="21680-382">El instalador devuelve un código de salida 0 en caso de no detectar ningún error y un código de salida 3010 para indicar que se requiere un reinicio.</span><span class="sxs-lookup"><span data-stu-id="21680-382">The installer returns an exit code of 0 for success and an exit code of 3010 to indicate that a restart is required.</span></span> <span data-ttu-id="21680-383">Cualquier otro valor suele ser un código de error.</span><span class="sxs-lookup"><span data-stu-id="21680-383">Any other value is generally an error code.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="21680-384">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="21680-384">Download and manually install</span></span>

<span data-ttu-id="21680-385">Como alternativa a los instaladores de Windows para .NET, puede descargar e instalar manualmente el SDK o el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="21680-385">As an alternative to the Windows installers for .NET, you can download and manually install the SDK or runtime.</span></span> <span data-ttu-id="21680-386">La instalación manual se suele realizar durante las pruebas de integración continua.</span><span class="sxs-lookup"><span data-stu-id="21680-386">Manual install is usually done as part of continuous integration testing.</span></span> <span data-ttu-id="21680-387">Para un desarrollador o usuario, generalmente es mejor usar un [instalador](https://dotnet.microsoft.com/download/dotnet).</span><span class="sxs-lookup"><span data-stu-id="21680-387">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet).</span></span>

<span data-ttu-id="21680-388">Tanto el SDK como el entorno de ejecución de .NET se pueden instalar manualmente una vez que se han descargado.</span><span class="sxs-lookup"><span data-stu-id="21680-388">Both .NET SDK and .NET Runtime can be manually installed after they've been downloaded.</span></span> <span data-ttu-id="21680-389">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="21680-389">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="21680-390">En primer lugar, descargue una versión binaria del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="21680-390">First, download a binary release for either the SDK or the runtime from one of the following sites:</span></span>

- [<span data-ttu-id="21680-391">Descargas de .NET 5.0</span><span class="sxs-lookup"><span data-stu-id="21680-391">.NET 5.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/5.0)
- [<span data-ttu-id="21680-392">Descargas de .NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="21680-392">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/3.1)
- [<span data-ttu-id="21680-393">Descargas de .NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="21680-393">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet/2.1)
- [<span data-ttu-id="21680-394">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="21680-394">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet)

<span data-ttu-id="21680-395">Cree un directorio en el que se extraerá .NET; por ejemplo, `%USERPROFILE%\dotnet`.</span><span class="sxs-lookup"><span data-stu-id="21680-395">Create a directory to extract .NET to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="21680-396">Después, extraiga el archivo ZIP descargado en ese directorio.</span><span class="sxs-lookup"><span data-stu-id="21680-396">Then, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="21680-397">De forma predeterminada, los comandos y las aplicaciones de la CLI de .NET no usarán la versión de .NET instalada de esta manera y debe elegir explícitamente usarla.</span><span class="sxs-lookup"><span data-stu-id="21680-397">By default, .NET CLI commands and apps won't use .NET installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="21680-398">Para ello, cambie las variables de entorno con las que se inicia una aplicación:</span><span class="sxs-lookup"><span data-stu-id="21680-398">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
set DOTNET_MULTILEVEL_LOOKUP=0
```

<span data-ttu-id="21680-399">Este enfoque permite instalar varias versiones en ubicaciones independientes y elegir explícitamente qué ubicación de instalación debe usar una aplicación mediante la ejecución de la aplicación con variables de entorno que apuntan a esa ubicación.</span><span class="sxs-lookup"><span data-stu-id="21680-399">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="21680-400">Cuando `DOTNET_MULTILEVEL_LOOKUP` se establece en `0`, .NET ignora cualquier versión de .NET instalada de forma global.</span><span class="sxs-lookup"><span data-stu-id="21680-400">When `DOTNET_MULTILEVEL_LOOKUP` is set to `0`, .NET ignores any globally installed .NET version.</span></span> <span data-ttu-id="21680-401">Elimine esa configuración de entorno para que .NET tenga en cuenta la ubicación de instalación global predeterminada al seleccionar el mejor marco para ejecutar la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21680-401">Remove that environment setting to let .NET consider the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="21680-402">La ubicación predeterminada suele ser `C:\Program Files\dotnet`, en la que los instaladores instalan .NET.</span><span class="sxs-lookup"><span data-stu-id="21680-402">The default is typically `C:\Program Files\dotnet`, which is where the installers install .NET.</span></span>

## <a name="docker"></a><span data-ttu-id="21680-403">Docker</span><span class="sxs-lookup"><span data-stu-id="21680-403">Docker</span></span>

<span data-ttu-id="21680-404">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="21680-404">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="21680-405">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="21680-405">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="21680-406">.NET se puede ejecutar en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="21680-406">.NET can run in a Docker container.</span></span> <span data-ttu-id="21680-407">Las imágenes oficiales de Docker en .NET se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET](https://hub.docker.com/_/microsoft-dotnet).</span><span class="sxs-lookup"><span data-stu-id="21680-407">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet).</span></span> <span data-ttu-id="21680-408">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="21680-408">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="21680-409">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="21680-409">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="21680-410">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="21680-410">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="21680-411">Para obtener más información sobre el uso de .NET en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/main/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="21680-411">For more information about using .NET in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/main/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="21680-412">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="21680-412">Next steps</span></span>

- <span data-ttu-id="21680-413">[Procedimiento para comprobar que .NET ya está instalado](how-to-detect-installed-versions.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="21680-413">[How to check if .NET is already installed](how-to-detect-installed-versions.md?pivots=os-windows).</span></span>
- <span data-ttu-id="21680-414">[Tutorial: Tutorial Hola mundo](../tutorials/with-visual-studio.md).</span><span class="sxs-lookup"><span data-stu-id="21680-414">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="21680-415">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="21680-415">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="21680-416">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="21680-416">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[esu]: /troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq
[vcc64]: https://aka.ms/vs/16/release/vc_redist.x64.exe
[vcc32]: https://aka.ms/vs/16/release/vc_redist.x86.exe
[kb64]: https://www.microsoft.com/download/details.aspx?id=47442
[kb32]: https://www.microsoft.com/download/details.aspx?id=47409
