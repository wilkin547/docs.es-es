---
title: Instalación de .NET en macOS
description: Obtenga información sobre qué versiones de macOS puede instalar en .NET.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 983c5d2c04b87759b898f449bc092161b03c8ace
ms.sourcegitcommit: c38bf879a2611ff46aacdd529b9f2725f93e18a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/13/2020
ms.locfileid: "94594461"
---
# <a name="install-net-on-macos"></a><span data-ttu-id="a46f1-103">Instalación de .NET en macOS</span><span class="sxs-lookup"><span data-stu-id="a46f1-103">Install .NET on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

<span data-ttu-id="a46f1-107">En este artículo obtendrá información sobre cómo instalar .NET en macOS.</span><span class="sxs-lookup"><span data-stu-id="a46f1-107">In this article, you'll learn how to install .NET on macOS.</span></span> <span data-ttu-id="a46f1-108">.NET está formado por el entorno de ejecución y el SDK.</span><span class="sxs-lookup"><span data-stu-id="a46f1-108">.NET is made up of the runtime and the SDK.</span></span> <span data-ttu-id="a46f1-109">El entorno de ejecución se usa para ejecutar una aplicación de .NET, y puede o no incluirse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a46f1-109">The runtime is used to run a .NET app and may or may not be included with the app.</span></span> <span data-ttu-id="a46f1-110">El SDK se usa para crear aplicaciones y bibliotecas de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-110">The SDK is used to create .NET apps and libraries.</span></span> <span data-ttu-id="a46f1-111">El entorno de ejecución de .NET siempre se instala con el SDK.</span><span class="sxs-lookup"><span data-stu-id="a46f1-111">The .NET runtime is always installed with the SDK.</span></span>

<span data-ttu-id="a46f1-112">La versión más reciente de .NET es la 5.0.</span><span class="sxs-lookup"><span data-stu-id="a46f1-112">The latest version of .NET is 5.0.</span></span>

> [!div class="button"]
> [<span data-ttu-id="a46f1-113">Descargar .NET Core</span><span class="sxs-lookup"><span data-stu-id="a46f1-113">Download .NET Core</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="a46f1-114">Versiones compatibles</span><span class="sxs-lookup"><span data-stu-id="a46f1-114">Supported releases</span></span>

<span data-ttu-id="a46f1-115">En la tabla siguiente se muestra una lista de versiones de .NET actualmente compatibles y las versiones de macOS que se admiten.</span><span class="sxs-lookup"><span data-stu-id="a46f1-115">The following table is a list of currently supported .NET releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="a46f1-116">Estas versiones se siguen admitiendo hasta que la versión de [.NET alcance la finalización del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="a46f1-116">These versions remain supported either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="a46f1-117">Con la marca ✔️ se indica que la versión de .NET Core se sigue admitiendo.</span><span class="sxs-lookup"><span data-stu-id="a46f1-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="a46f1-118">Con la marca ❌ se indica que la versión de .NET Core no se admite.</span><span class="sxs-lookup"><span data-stu-id="a46f1-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="a46f1-119">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="a46f1-119">Operating System</span></span>          | <span data-ttu-id="a46f1-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-120">.NET Core 2.1</span></span> | <span data-ttu-id="a46f1-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-121">.NET Core 3.1</span></span> | <span data-ttu-id="a46f1-122">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a46f1-122">.NET 5.0</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a46f1-123">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="a46f1-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="a46f1-124">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="a46f1-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="a46f1-125">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="a46f1-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="a46f1-126">✔️ 5.0 ([notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="a46f1-126">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="a46f1-127">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="a46f1-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="a46f1-128">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="a46f1-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="a46f1-129">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="a46f1-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="a46f1-130">✔️ 5.0 ([notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="a46f1-130">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="a46f1-131">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="a46f1-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="a46f1-132">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="a46f1-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="a46f1-133">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="a46f1-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="a46f1-134">✔️ 5.0 ([notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="a46f1-134">✔️ 5.0 ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="a46f1-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="a46f1-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="a46f1-136">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="a46f1-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="a46f1-137">❌ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="a46f1-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="a46f1-138">❌ 5.0 ([notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="a46f1-138">❌ 5.0 ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="a46f1-139">Versiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="a46f1-139">Unsupported releases</span></span>

<span data-ttu-id="a46f1-140">Las versiones siguientes de .NET ya ❌ no se admiten.</span><span class="sxs-lookup"><span data-stu-id="a46f1-140">The following versions of .NET are ❌ no longer supported.</span></span> <span data-ttu-id="a46f1-141">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="a46f1-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a46f1-142">3.0 ([Notas de la versión][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="a46f1-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="a46f1-143">2.2 ([Notas de la versión][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="a46f1-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="a46f1-144">2.0 ([Notas de la versión][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="a46f1-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="a46f1-145">Información en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="a46f1-145">Runtime information</span></span>

<span data-ttu-id="a46f1-146">El entorno de ejecución se usa para ejecutar aplicaciones creadas con .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-146">The runtime is used to run apps created with .NET.</span></span> <span data-ttu-id="a46f1-147">Cuando un autor publica una aplicación, puede incluir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f1-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="a46f1-148">Si no lo hace, el usuario elige si quiere instalar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f1-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="a46f1-149">Hay tres tiempos de ejecución distintos que se pueden instalar en macOS:</span><span class="sxs-lookup"><span data-stu-id="a46f1-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="a46f1-150">*Entorno de ejecución de ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="a46f1-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="a46f1-151">Ejecuta aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a46f1-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="a46f1-152">Incluye el entorno de ejecución de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-152">Includes the .NET runtime.</span></span>

<span data-ttu-id="a46f1-153">*Entorno de ejecución de .NET*</span><span class="sxs-lookup"><span data-stu-id="a46f1-153">*.NET runtime*</span></span>\
<span data-ttu-id="a46f1-154">Este entorno de ejecución es el más sencillo y no incluye ningún otro.</span><span class="sxs-lookup"><span data-stu-id="a46f1-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="a46f1-155">Se recomienda encarecidamente instalar el *entorno de ejecución de ASP.NET Core* para conseguir la mejor compatibilidad con las aplicaciones de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET apps.</span></span>

> [!div class="button"]
> [<span data-ttu-id="a46f1-156">Descarga del entorno de ejecución de .NET</span><span class="sxs-lookup"><span data-stu-id="a46f1-156">Download .NET Runtime</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="a46f1-157">Información del SDK</span><span class="sxs-lookup"><span data-stu-id="a46f1-157">SDK information</span></span>

<span data-ttu-id="a46f1-158">El SDK se usa para compilar y publicar aplicaciones y bibliotecas de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-158">The SDK is used to build and publish .NET apps and libraries.</span></span> <span data-ttu-id="a46f1-159">La instalación del SDK incluye ambos [entornos de ejecución](#runtime-information): ASP.NET Core y .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET.</span></span>

## <a name="dependencies"></a><span data-ttu-id="a46f1-160">Dependencias</span><span class="sxs-lookup"><span data-stu-id="a46f1-160">Dependencies</span></span>

<span data-ttu-id="a46f1-161">.NET es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="a46f1-161">.NET is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="a46f1-162">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="a46f1-162">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="a46f1-163">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a46f1-163">.NET Core Version</span></span> | <span data-ttu-id="a46f1-164">macOS</span><span class="sxs-lookup"><span data-stu-id="a46f1-164">macOS</span></span>                 | <span data-ttu-id="a46f1-165">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="a46f1-165">Architectures</span></span> | <span data-ttu-id="a46f1-166">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-166">More information</span></span>    |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="a46f1-167">5.0</span><span class="sxs-lookup"><span data-stu-id="a46f1-167">5.0</span></span>               | <span data-ttu-id="a46f1-168">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a46f1-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a46f1-169">x64</span><span class="sxs-lookup"><span data-stu-id="a46f1-169">x64</span></span> | [<span data-ttu-id="a46f1-170">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md) |
| <span data-ttu-id="a46f1-171">3.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-171">3.1</span></span>               | <span data-ttu-id="a46f1-172">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a46f1-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a46f1-173">x64</span><span class="sxs-lookup"><span data-stu-id="a46f1-173">x64</span></span> | [<span data-ttu-id="a46f1-174">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="a46f1-175">3.0</span><span class="sxs-lookup"><span data-stu-id="a46f1-175">3.0</span></span>               | <span data-ttu-id="a46f1-176">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a46f1-176">High Sierra (10.13+)</span></span>  | <span data-ttu-id="a46f1-177">x64</span><span class="sxs-lookup"><span data-stu-id="a46f1-177">x64</span></span> | [<span data-ttu-id="a46f1-178">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="a46f1-179">2.2</span><span class="sxs-lookup"><span data-stu-id="a46f1-179">2.2</span></span>               | <span data-ttu-id="a46f1-180">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a46f1-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="a46f1-181">x64</span><span class="sxs-lookup"><span data-stu-id="a46f1-181">x64</span></span> | [<span data-ttu-id="a46f1-182">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="a46f1-183">2.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-183">2.1</span></span>               | <span data-ttu-id="a46f1-184">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="a46f1-184">Sierra (10.12+)</span></span>       | <span data-ttu-id="a46f1-185">x64</span><span class="sxs-lookup"><span data-stu-id="a46f1-185">x64</span></span> | [<span data-ttu-id="a46f1-186">Más información</span><span class="sxs-lookup"><span data-stu-id="a46f1-186">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="a46f1-187">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="a46f1-187">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="a46f1-188">Este requisito se aplica al entorno de ejecución de .NET, al SDK de .NET y al software creado con .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-188">This requirement applies to the .NET runtime, .NET SDK, and software created with .NET.</span></span>

<span data-ttu-id="a46f1-189">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores del entorno de ejecución y el SDK de .NET 5.0 y .NET Core 3.1, 3.0 y 2.1.</span><span class="sxs-lookup"><span data-stu-id="a46f1-189">The runtime and SDK installers for .NET 5.0 and .NET Core 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="a46f1-190">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="a46f1-190">Prior released versions aren't notarized.</span></span> <span data-ttu-id="a46f1-191">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="a46f1-191">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="a46f1-193">Para obtener más información sobre cómo afecta la certificación forzada a .NET (y a las aplicaciones de .NET), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-193">For more information about how enforced-notarization affects .NET (and your .NET apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="a46f1-194">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="a46f1-194">libgdiplus</span></span>

<span data-ttu-id="a46f1-195">Para las aplicaciones de .NET en las que se usa el ensamblado *System.Drawing.Common* es necesario instalar libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="a46f1-195">.NET applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="a46f1-196">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="a46f1-196">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="a46f1-197">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="a46f1-197">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="a46f1-198">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="a46f1-198">Install with an installer</span></span>

<span data-ttu-id="a46f1-199">macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET 5.0:</span><span class="sxs-lookup"><span data-stu-id="a46f1-199">macOS has standalone installers that can be used to install the .NET 5.0 SDK:</span></span>

- [<span data-ttu-id="a46f1-200">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="a46f1-200">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/5.0)

## <a name="download-and-manually-install"></a><span data-ttu-id="a46f1-201">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="a46f1-201">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="a46f1-202">Como alternativa a los instaladores de macOS para .NET, puede descargar e instalar manualmente el SDK y el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f1-202">As an alternative to the macOS installers for .NET, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="a46f1-203">La instalación manual se suele llevar a cabo durante las pruebas de integración continua.</span><span class="sxs-lookup"><span data-stu-id="a46f1-203">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="a46f1-204">Para un desarrollador o usuario, generalmente es mejor usar un [instalador](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="a46f1-204">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="a46f1-205">Si instala el SDK de .NET, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="a46f1-205">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="a46f1-206">En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="a46f1-206">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="a46f1-207">✔️ [Descargas de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="a46f1-207">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="a46f1-208">✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="a46f1-208">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="a46f1-209">✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="a46f1-209">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="a46f1-210">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="a46f1-210">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="a46f1-211">A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET. Luego, asegúrese de que .NET esté en PATH.</span><span class="sxs-lookup"><span data-stu-id="a46f1-211">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="a46f1-212">Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-212">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="a46f1-213">Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.</span><span class="sxs-lookup"><span data-stu-id="a46f1-213">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="a46f1-214">El nombre del archivo puede ser distinto en función de lo que haya descargado.</span><span class="sxs-lookup"><span data-stu-id="a46f1-214">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="a46f1-215">**Use el comando siguiente para extraer el entorno de ejecución**:</span><span class="sxs-lookup"><span data-stu-id="a46f1-215">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="a46f1-216">**Use el comando siguiente para extraer el SDK**:</span><span class="sxs-lookup"><span data-stu-id="a46f1-216">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="a46f1-217">Los comandos `export` anteriores solo hacen que los de la CLI de .NET estén disponibles para la sesión del terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="a46f1-217">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="a46f1-218">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="a46f1-218">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="a46f1-219">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="a46f1-219">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="a46f1-220">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="a46f1-220">For example:</span></span>
>
> - <span data-ttu-id="a46f1-221">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="a46f1-221">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="a46f1-222">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="a46f1-222">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="a46f1-223">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="a46f1-223">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="a46f1-224">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="a46f1-224">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="a46f1-225">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="a46f1-225">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="a46f1-226">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="a46f1-226">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="a46f1-227">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="a46f1-227">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="a46f1-228">Instalación con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="a46f1-228">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="a46f1-229">Visual Studio para Mac instala el SDK de .NET cuando se selecciona la carga de trabajo **.NET**.</span><span class="sxs-lookup"><span data-stu-id="a46f1-229">Visual Studio for Mac installs the .NET SDK when the **.NET** workload is selected.</span></span> <span data-ttu-id="a46f1-230">Para empezar con el desarrollo en .NET en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="a46f1-230">To get started with .NET development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span>

| <span data-ttu-id="a46f1-231">Versión de SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="a46f1-231">.NET SDK version</span></span>      | <span data-ttu-id="a46f1-232">Versión de Visual Studio</span><span class="sxs-lookup"><span data-stu-id="a46f1-232">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="a46f1-233">5.0</span><span class="sxs-lookup"><span data-stu-id="a46f1-233">5.0</span></span>                   | <span data-ttu-id="a46f1-234">Visual Studio 2019 para Mac, versión 8.8 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a46f1-234">Visual Studio 2019 for Mac version 8.8 or higher.</span></span> |
| <span data-ttu-id="a46f1-235">3.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-235">3.1</span></span>                   | <span data-ttu-id="a46f1-236">Visual Studio 2019 para Mac, versión 8.4 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a46f1-236">Visual Studio 2019 for Mac version 8.4 or higher.</span></span> |
| <span data-ttu-id="a46f1-237">2.1</span><span class="sxs-lookup"><span data-stu-id="a46f1-237">2.1</span></span>                   | <span data-ttu-id="a46f1-238">Visual Studio 2019 para Mac, versión 8.0 o posterior.</span><span class="sxs-lookup"><span data-stu-id="a46f1-238">Visual Studio 2019 for Mac version 8.0 or higher.</span></span> |

<span data-ttu-id="a46f1-239">[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="a46f1-239">[![macOS Visual Studio 2019 for Mac with .NET workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="a46f1-240">Instalación junto con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="a46f1-240">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="a46f1-241">Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="a46f1-241">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="a46f1-242">Visual Studio Code está disponible para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="a46f1-242">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="a46f1-243">Aunque Visual Studio Code no incluye un instalador automatizado de .NET como Visual Studio, resulta sencillo agregar compatibilidad con .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-243">While Visual Studio Code doesn't come with an automated .NET installer like Visual Studio does, adding .NET support is simple.</span></span>

01. <span data-ttu-id="a46f1-244">[Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="a46f1-244">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="a46f1-245">[Descargue e instale el SDK de .NET](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="a46f1-245">[Download and install the .NET SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="a46f1-246">[Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="a46f1-246">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="a46f1-247">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="a46f1-247">Install with bash automation</span></span>

<span data-ttu-id="a46f1-248">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f1-248">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="a46f1-249">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-249">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="a46f1-250">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET 3.1.</span><span class="sxs-lookup"><span data-stu-id="a46f1-250">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET 3.1.</span></span> <span data-ttu-id="a46f1-251">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="a46f1-251">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="a46f1-252">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a46f1-252">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="a46f1-253">De lo contrario, el script instala el [SDK](./windows.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-253">Otherwise, the script installs the [SDK](./windows.md).</span></span>

```bash
./dotnet-install.sh --channel 5.0 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="a46f1-254">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="a46f1-254">The previous command installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="a46f1-255">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET.</span><span class="sxs-lookup"><span data-stu-id="a46f1-255">The ASP.NET Core runtime also includes the standard .NET runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="a46f1-256">Docker</span><span class="sxs-lookup"><span data-stu-id="a46f1-256">Docker</span></span>

<span data-ttu-id="a46f1-257">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="a46f1-257">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="a46f1-258">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a46f1-258">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="a46f1-259">.NET se puede ejecutar en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="a46f1-259">.NET can run in a Docker container.</span></span> <span data-ttu-id="a46f1-260">Las imágenes oficiales de Docker en .NET se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet/).</span><span class="sxs-lookup"><span data-stu-id="a46f1-260">Official .NET Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet/).</span></span> <span data-ttu-id="a46f1-261">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="a46f1-261">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="a46f1-262">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="a46f1-262">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="a46f1-263">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-aspnet) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="a46f1-263">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-aspnet) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="a46f1-264">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-264">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="a46f1-265">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="a46f1-265">Next steps</span></span>

- <span data-ttu-id="a46f1-266">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="a46f1-266">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="a46f1-267">[Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-267">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="a46f1-268">[Tutorial: Introducción a macOS](../tutorials/with-visual-studio-mac.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-268">[Tutorial: Get started on macOS](../tutorials/with-visual-studio-mac.md).</span></span>
- <span data-ttu-id="a46f1-269">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-269">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="a46f1-270">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="a46f1-270">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
