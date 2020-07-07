---
title: Instalación de .NET Core en macOS
description: Descubra qué versiones de macOS puede instalar en .NET Core.
author: adegeo
ms.author: adegeo
ms.date: 06/25/2020
ms.openlocfilehash: bb1a0fa24e2f6e8850cbe59378793ff846f04ba9
ms.sourcegitcommit: c23d9666ec75b91741da43ee3d91c317d68c7327
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85804462"
---
# <a name="install-net-core-on-macos"></a><span data-ttu-id="09920-103">Instalación de .NET Core en macOS</span><span class="sxs-lookup"><span data-stu-id="09920-103">Install .NET Core on macOS</span></span>

> [!div class="op_single_selector"]
>
> - [Instalación en Windows](windows.md)
> - [Instalación en macOS](macos.md)
> - [Instalación en Linux](linux.md)

<span data-ttu-id="09920-107">En este artículo obtendrá información sobre cómo instalar .NET Core en macOS.</span><span class="sxs-lookup"><span data-stu-id="09920-107">In this article, you'll learn how to install .NET Core on macOS.</span></span> <span data-ttu-id="09920-108">.NET Core está formado por el entorno de ejecución y el SDK.</span><span class="sxs-lookup"><span data-stu-id="09920-108">.NET Core is made up of the runtime and the SDK.</span></span> <span data-ttu-id="09920-109">El tiempo de ejecución se usa para ejecutar una aplicación de .NET Core, y puede o no incluirse con la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09920-109">The runtime is used to run a .NET Core app and may or may not be included with the app.</span></span> <span data-ttu-id="09920-110">El SDK se usa para crear aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-110">The SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="09920-111">El entorno de ejecución de .NET Core siempre se instala con el SDK.</span><span class="sxs-lookup"><span data-stu-id="09920-111">The .NET Core runtime is always installed with the SDK.</span></span>

<span data-ttu-id="09920-112">La versión más reciente de .NET Core es la 3.1.</span><span class="sxs-lookup"><span data-stu-id="09920-112">The latest version of .NET Core is 3.1.</span></span>

[<span data-ttu-id="09920-113">Descargar .NET Core</span><span class="sxs-lookup"><span data-stu-id="09920-113">Download .NET Core.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="supported-releases"></a><span data-ttu-id="09920-114">Versiones compatibles</span><span class="sxs-lookup"><span data-stu-id="09920-114">Supported releases</span></span>

<span data-ttu-id="09920-115">En la tabla siguiente se muestra una lista de versiones de .NET Core actualmente compatibles y las versiones de macOS que se admiten.</span><span class="sxs-lookup"><span data-stu-id="09920-115">The following table is a list of currently supported .NET Core releases and the versions of macOS they're supported on.</span></span> <span data-ttu-id="09920-116">Estas versiones se siguen admitiendo hasta que la versión de [.NET Core alcance la finalización del soporte técnico](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="09920-116">These versions remain supported either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

- <span data-ttu-id="09920-117">Con la marca ✔️ se indica que la versión de .NET Core se sigue admitiendo.</span><span class="sxs-lookup"><span data-stu-id="09920-117">A ✔️ indicates that the version of .NET Core is still supported.</span></span>
- <span data-ttu-id="09920-118">Con la marca ❌ se indica que la versión de .NET Core no se admite.</span><span class="sxs-lookup"><span data-stu-id="09920-118">A ❌ indicates that the version of .NET Core isn't supported.</span></span>

| <span data-ttu-id="09920-119">Sistema operativo</span><span class="sxs-lookup"><span data-stu-id="09920-119">Operating System</span></span>          | <span data-ttu-id="09920-120">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="09920-120">.NET Core 2.1</span></span> | <span data-ttu-id="09920-121">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="09920-121">.NET Core 3.1</span></span> | <span data-ttu-id="09920-122">.NET 5 (versión preliminar)</span><span class="sxs-lookup"><span data-stu-id="09920-122">.NET 5 Preview</span></span> |
|---------------------------|---------------|---------------|----------------|
| <span data-ttu-id="09920-123">macOS 10.15 "Catalina"</span><span class="sxs-lookup"><span data-stu-id="09920-123">macOS 10.15 "Catalina"</span></span>    | <span data-ttu-id="09920-124">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="09920-124">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="09920-125">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="09920-125">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="09920-126">✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="09920-126">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="09920-127">macOS 10.14 "Mojave"</span><span class="sxs-lookup"><span data-stu-id="09920-127">macOS 10.14 "Mojave"</span></span>      | <span data-ttu-id="09920-128">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="09920-128">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="09920-129">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="09920-129">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="09920-130">✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="09920-130">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="09920-131">macOS 10.13 "High Sierra"</span><span class="sxs-lookup"><span data-stu-id="09920-131">macOS 10.13 "High Sierra"</span></span> | <span data-ttu-id="09920-132">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="09920-132">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="09920-133">✔️ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="09920-133">✔️ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="09920-134">✔️ 5.0, versión preliminar ([Notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="09920-134">✔️ 5.0 Preview ([Release notes][release-notes-50])</span></span> |
| <span data-ttu-id="09920-135">macOS 10.12 "Sierra"</span><span class="sxs-lookup"><span data-stu-id="09920-135">macOS 10.12 "Sierra"</span></span>      | <span data-ttu-id="09920-136">✔️ 2.1 ([Notas de la versión][release-notes-21])</span><span class="sxs-lookup"><span data-stu-id="09920-136">✔️ 2.1 ([Release notes][release-notes-21])</span></span> | <span data-ttu-id="09920-137">❌ 3.1 ([Notas de la versión][release-notes-31])</span><span class="sxs-lookup"><span data-stu-id="09920-137">❌ 3.1 ([Release notes][release-notes-31])</span></span> | <span data-ttu-id="09920-138">❌ 5.0, versión preliminar ([Notas de la versión][release-notes-50])</span><span class="sxs-lookup"><span data-stu-id="09920-138">❌ 5.0 Preview ([Release notes][release-notes-50])</span></span> |

## <a name="unsupported-releases"></a><span data-ttu-id="09920-139">Versiones no admitidas</span><span class="sxs-lookup"><span data-stu-id="09920-139">Unsupported releases</span></span>

<span data-ttu-id="09920-140">Las siguientes versiones de .NET Core ya no se admiten ❌.</span><span class="sxs-lookup"><span data-stu-id="09920-140">The following versions of .NET Core are ❌ no longer supported.</span></span> <span data-ttu-id="09920-141">aunque sus descargas siguen estando publicadas:</span><span class="sxs-lookup"><span data-stu-id="09920-141">The downloads for these still remain published:</span></span>

- <span data-ttu-id="09920-142">3.0 ([Notas de la versión][release-notes-30])</span><span class="sxs-lookup"><span data-stu-id="09920-142">3.0 ([Release notes][release-notes-30])</span></span>
- <span data-ttu-id="09920-143">2.2 ([Notas de la versión][release-notes-22])</span><span class="sxs-lookup"><span data-stu-id="09920-143">2.2 ([Release notes][release-notes-22])</span></span>
- <span data-ttu-id="09920-144">2.0 ([Notas de la versión][release-notes-20])</span><span class="sxs-lookup"><span data-stu-id="09920-144">2.0 ([Release notes][release-notes-20])</span></span>

## <a name="runtime-information"></a><span data-ttu-id="09920-145">Información en tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="09920-145">Runtime information</span></span>

<span data-ttu-id="09920-146">El entorno de ejecución de .NET Core se usa para ejecutar aplicaciones creadas con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-146">The runtime is used to run apps created with .NET Core.</span></span> <span data-ttu-id="09920-147">Cuando un autor publica una aplicación, puede incluir el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09920-147">When an app author publishes an app, they can include the runtime with their app.</span></span> <span data-ttu-id="09920-148">Si no lo hace, el usuario elige si quiere instalar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09920-148">If they don't include the runtime, it's up to the user to install the runtime.</span></span>

<span data-ttu-id="09920-149">Hay tres tiempos de ejecución distintos que se pueden instalar en macOS:</span><span class="sxs-lookup"><span data-stu-id="09920-149">There are three different runtimes you can install on macOS:</span></span>

<span data-ttu-id="09920-150">*Entorno de ejecución de ASP.NET Core*</span><span class="sxs-lookup"><span data-stu-id="09920-150">*ASP.NET Core runtime*</span></span>\
<span data-ttu-id="09920-151">Ejecuta aplicaciones de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-151">Runs ASP.NET Core apps.</span></span> <span data-ttu-id="09920-152">Incluye el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-152">Includes the .NET Core runtime.</span></span>

<span data-ttu-id="09920-153">*Entorno de ejecución de .NET Core*</span><span class="sxs-lookup"><span data-stu-id="09920-153">*.NET Core runtime*</span></span>\
<span data-ttu-id="09920-154">Este entorno de ejecución es el más sencillo y no incluye ningún otro.</span><span class="sxs-lookup"><span data-stu-id="09920-154">This runtime is the simplest runtime and doesn't include any other runtime.</span></span> <span data-ttu-id="09920-155">Le recomendamos encarecidamente que instale el *entorno de ejecución de ASP.NET Core* para conseguir la mejor compatibilidad con las aplicaciones de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-155">It's highly recommended that you install *ASP.NET Core runtime* for the best compatibility with .NET Core apps.</span></span>

[<span data-ttu-id="09920-156">Descargue el entorno de ejecución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-156">Download .NET Core Runtime.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="sdk-information"></a><span data-ttu-id="09920-157">Información del SDK</span><span class="sxs-lookup"><span data-stu-id="09920-157">SDK information</span></span>

<span data-ttu-id="09920-158">El SDK se usa para compilar y publicar aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-158">The SDK is used to build and publish .NET Core apps and libraries.</span></span> <span data-ttu-id="09920-159">La instalación del SDK incluye ambos [entornos de ejecución](#runtime-information): ASP.NET Core y .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-159">Installing the SDK includes both [runtimes](#runtime-information): ASP.NET Core and .NET Core.</span></span>

[<span data-ttu-id="09920-160">Descargue el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-160">Download .NET Core SDK.</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

## <a name="dependencies"></a><span data-ttu-id="09920-161">Dependencias</span><span class="sxs-lookup"><span data-stu-id="09920-161">Dependencies</span></span>

<span data-ttu-id="09920-162">.NET Core es compatible con las versiones siguientes de macOS:</span><span class="sxs-lookup"><span data-stu-id="09920-162">.NET Core is supported on the following macOS releases:</span></span>

> [!NOTE]
> <span data-ttu-id="09920-163">Un símbolo `+` representa la versión mínima.</span><span class="sxs-lookup"><span data-stu-id="09920-163">A `+` symbol represents the minimum version.</span></span>

| <span data-ttu-id="09920-164">Versión de .NET Core</span><span class="sxs-lookup"><span data-stu-id="09920-164">.NET Core Version</span></span> | <span data-ttu-id="09920-165">macOS</span><span class="sxs-lookup"><span data-stu-id="09920-165">macOS</span></span>                 | <span data-ttu-id="09920-166">Arquitecturas</span><span class="sxs-lookup"><span data-stu-id="09920-166">Architectures</span></span> |     |
| ----------------- | --------------------- | --------------| --- |
| <span data-ttu-id="09920-167">3.1</span><span class="sxs-lookup"><span data-stu-id="09920-167">3.1</span></span>               | <span data-ttu-id="09920-168">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="09920-168">High Sierra (10.13+)</span></span>  | <span data-ttu-id="09920-169">x64</span><span class="sxs-lookup"><span data-stu-id="09920-169">x64</span></span> | [<span data-ttu-id="09920-170">Más información</span><span class="sxs-lookup"><span data-stu-id="09920-170">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md) |
| <span data-ttu-id="09920-171">3.0</span><span class="sxs-lookup"><span data-stu-id="09920-171">3.0</span></span>               | <span data-ttu-id="09920-172">High Sierra (10.13 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="09920-172">High Sierra (10.13+)</span></span>  | <span data-ttu-id="09920-173">x64</span><span class="sxs-lookup"><span data-stu-id="09920-173">x64</span></span> | [<span data-ttu-id="09920-174">Más información</span><span class="sxs-lookup"><span data-stu-id="09920-174">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md) |
| <span data-ttu-id="09920-175">2.2</span><span class="sxs-lookup"><span data-stu-id="09920-175">2.2</span></span>               | <span data-ttu-id="09920-176">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="09920-176">Sierra (10.12+)</span></span>       | <span data-ttu-id="09920-177">x64</span><span class="sxs-lookup"><span data-stu-id="09920-177">x64</span></span> | [<span data-ttu-id="09920-178">Más información</span><span class="sxs-lookup"><span data-stu-id="09920-178">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md) |
| <span data-ttu-id="09920-179">2.1</span><span class="sxs-lookup"><span data-stu-id="09920-179">2.1</span></span>               | <span data-ttu-id="09920-180">Sierra (10.12 y posteriores)</span><span class="sxs-lookup"><span data-stu-id="09920-180">Sierra (10.12+)</span></span>       | <span data-ttu-id="09920-181">x64</span><span class="sxs-lookup"><span data-stu-id="09920-181">x64</span></span> | [<span data-ttu-id="09920-182">Más información</span><span class="sxs-lookup"><span data-stu-id="09920-182">More information</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md) |

<span data-ttu-id="09920-183">A partir de macOS Catalina (versión 10.15), se debe conceder la certificación a todo el software creado después del 1 de junio de 2019 que se distribuye con el identificador de desarrollador.</span><span class="sxs-lookup"><span data-stu-id="09920-183">Beginning with macOS Catalina (version 10.15), all software built after June 1, 2019 that is distributed with Developer ID, must be notarized.</span></span> <span data-ttu-id="09920-184">Este requisito se aplica al runtime de .NET Core, al SDK de .NET Core y al software creado con .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-184">This requirement applies to the .NET Core runtime, .NET Core SDK, and software created with .NET Core.</span></span>

<span data-ttu-id="09920-185">Desde el 18 de febrero de 2020, se ha concedido la certificación a los instaladores de las versiones 3.1, 3.0 y 2.1 de .NET Core (tanto el runtime como el SDK).</span><span class="sxs-lookup"><span data-stu-id="09920-185">The installers for .NET Core (both runtime and SDK) versions 3.1, 3.0, and 2.1, have been notarized since February 18, 2020.</span></span> <span data-ttu-id="09920-186">A las versiones publicadas anteriores no se les ha concedido la certificación.</span><span class="sxs-lookup"><span data-stu-id="09920-186">Prior released versions aren't notarized.</span></span> <span data-ttu-id="09920-187">Si ejecuta una aplicación sin certificación, verá un error similar al de la imagen siguiente:</span><span class="sxs-lookup"><span data-stu-id="09920-187">If you run a non-notarized app, you'll see an error similar to the following image:</span></span>

![Alerta de certificación de macOS Catalina](media/dependencies/macos-notarized-pkg-warning.png)

<span data-ttu-id="09920-189">Para obtener más información sobre cómo afecta la certificación forzada a .NET Core (y a las aplicaciones de .NET Core), vea [Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09920-189">For more information about how enforced-notarization affects .NET Core (and your .NET Core apps), see [Working with macOS Catalina Notarization](macos-notarization-issues.md).</span></span>

## <a name="libgdiplus"></a><span data-ttu-id="09920-190">libgdiplus</span><span class="sxs-lookup"><span data-stu-id="09920-190">libgdiplus</span></span>

<span data-ttu-id="09920-191">Las aplicaciones .NET Core que usan el ensamblado *System.Drawing.Common* requieren la instalación de libgdiplus.</span><span class="sxs-lookup"><span data-stu-id="09920-191">.NET Core applications that use the *System.Drawing.Common* assembly require libgdiplus to be installed.</span></span>

<span data-ttu-id="09920-192">Una manera fácil de obtener libgdiplus es usar el administrador de paquetes [Homebrew ("brew")](https://brew.sh/) para macOS.</span><span class="sxs-lookup"><span data-stu-id="09920-192">An easy way to obtain libgdiplus is by using the [Homebrew ("brew")](https://brew.sh/) package manager for macOS.</span></span> <span data-ttu-id="09920-193">Después de instalar *brew*, instale libgdiplus mediante la ejecución de los comandos siguientes en un símbolo del sistema de Terminal (comando):</span><span class="sxs-lookup"><span data-stu-id="09920-193">After installing *brew*, install libgdiplus by executing the following commands at a Terminal (command) prompt:</span></span>

```console
brew update
brew install mono-libgdiplus
```

## <a name="install-with-an-installer"></a><span data-ttu-id="09920-194">Instalación mediante un instalador</span><span class="sxs-lookup"><span data-stu-id="09920-194">Install with an installer</span></span>

<span data-ttu-id="09920-195">macOS tiene instaladores independientes que se pueden usar para instalar el SDK de .NET Core 3.1:</span><span class="sxs-lookup"><span data-stu-id="09920-195">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="09920-196">CPU de x64 (64 bits)</span><span class="sxs-lookup"><span data-stu-id="09920-196">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="09920-197">Descarga e instalación de forma manual</span><span class="sxs-lookup"><span data-stu-id="09920-197">Download and manually install</span></span>

<!-- Note, this content is taken from includes/linux-install-manual.md but changed for macOS. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="09920-198">Como alternativa a los instaladores de macOS para .NET Core, puede descargar e instalar manualmente el SDK y el entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09920-198">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="09920-199">La instalación manual se suele llevar a cabo durante las pruebas de integración continua.</span><span class="sxs-lookup"><span data-stu-id="09920-199">Manual install is usually performed as part of continuous integration testing.</span></span> <span data-ttu-id="09920-200">Para un desarrollador o usuario, generalmente es mejor usar un [instalador](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="09920-200">For a developer or user, it's generally better to use an [installer](https://dotnet.microsoft.com/download/dotnet-core).</span></span>

<span data-ttu-id="09920-201">Si instala el SDK de .NET Core, no necesita instalar el entorno de ejecución correspondiente.</span><span class="sxs-lookup"><span data-stu-id="09920-201">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="09920-202">En primer lugar, descargue una versión **binaria** del SDK o del entorno de ejecución de uno de los siguientes sitios:</span><span class="sxs-lookup"><span data-stu-id="09920-202">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="09920-203">✔️ [Descargas de la versión preliminar de .NET 5.0](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="09920-203">✔️ [.NET 5.0 preview downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="09920-204">✔️ [Descargas de .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="09920-204">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="09920-205">✔️ [Descargas de .NET Core 2.1](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="09920-205">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="09920-206">Todas las descargas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="09920-206">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="09920-207">A continuación, extraiga el archivo descargado y use el comando `export` para establecer las variables que se utilizan en .NET Core. Luego, asegúrese de que .NET Core esté en PATH.</span><span class="sxs-lookup"><span data-stu-id="09920-207">Next, extract the downloaded file and use the `export` command to set variables used by .NET Core and then ensure .NET Core is in PATH.</span></span>

<span data-ttu-id="09920-208">Para extraer el entorno de ejecución y hacer que los comandos de la CLI de .NET Core estén disponibles en el terminal, en primer lugar, descargue una versión binaria de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-208">To extract the runtime and make the .NET Core CLI commands available at the terminal, first download a .NET Core binary release.</span></span> <span data-ttu-id="09920-209">Luego, abra un terminal y ejecute los siguientes comandos desde el directorio donde se guardó el archivo.</span><span class="sxs-lookup"><span data-stu-id="09920-209">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="09920-210">El nombre del archivo puede ser distinto en función de lo que haya descargado.</span><span class="sxs-lookup"><span data-stu-id="09920-210">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="09920-211">**Use el comando siguiente para extraer el entorno de ejecución**:</span><span class="sxs-lookup"><span data-stu-id="09920-211">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-3.1.5-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="09920-212">**Use el comando siguiente para extraer el SDK**:</span><span class="sxs-lookup"><span data-stu-id="09920-212">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-3.1.301-osx-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="09920-213">Los comandos `export` anteriores solo hacen que los comandos de la CLI de .NET Core estén disponibles para la sesión de terminal en la que se ha ejecutado.</span><span class="sxs-lookup"><span data-stu-id="09920-213">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="09920-214">Puede editar el perfil del shell para agregar los comandos de forma permanente.</span><span class="sxs-lookup"><span data-stu-id="09920-214">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="09920-215">Hay una serie de shells distintos disponibles para Linux, y cada uno de ellos tiene un perfil diferente.</span><span class="sxs-lookup"><span data-stu-id="09920-215">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="09920-216">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="09920-216">For example:</span></span>
>
> - <span data-ttu-id="09920-217">**Shell de Bash**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="09920-217">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="09920-218">**Shell de Korn**: *~/.kshrc* or *.profile*</span><span class="sxs-lookup"><span data-stu-id="09920-218">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="09920-219">**Shell de Z**: *~/.zshrc* or *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="09920-219">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="09920-220">Edite el archivo de origen adecuado para el shell y agregue `:$HOME/dotnet` al final de la instrucción `PATH` existente.</span><span class="sxs-lookup"><span data-stu-id="09920-220">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="09920-221">Si no se incluye ninguna instrucción `PATH`, agregue una nueva línea con `export PATH=$PATH:$HOME/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="09920-221">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="09920-222">Además, agregue `export DOTNET_ROOT=$HOME/dotnet` al final del archivo.</span><span class="sxs-lookup"><span data-stu-id="09920-222">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="09920-223">Este enfoque le permite instalar diferentes versiones en ubicaciones independientes y elegir explícitamente cuál usará cada aplicación.</span><span class="sxs-lookup"><span data-stu-id="09920-223">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="09920-224">Instalación con Visual Studio para Mac</span><span class="sxs-lookup"><span data-stu-id="09920-224">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="09920-225">Visual Studio para Mac instala el SDK de .NET Core cuando se selecciona la carga de trabajo **.NET Core**.</span><span class="sxs-lookup"><span data-stu-id="09920-225">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="09920-226">Para empezar con el desarrollo en .NET Core en macOS, vea [Instalación de Visual Studio 2019 para Mac](/visualstudio/mac/installation).</span><span class="sxs-lookup"><span data-stu-id="09920-226">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="09920-227">Para obtener la versión más reciente, .NET Core 3.1, se debe usar la versión preliminar de Visual Studio para Mac 8.4.</span><span class="sxs-lookup"><span data-stu-id="09920-227">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="09920-228">[![Visual Studio 2019 para Mac de macOS con la característica de carga de trabajo de .NET Core](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="09920-228">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="09920-229">Instalación junto con Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="09920-229">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="09920-230">Visual Studio Code es un editor de código fuente ligero y eficaz que se ejecuta en el escritorio.</span><span class="sxs-lookup"><span data-stu-id="09920-230">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="09920-231">Visual Studio Code está disponible para Windows, macOS y Linux.</span><span class="sxs-lookup"><span data-stu-id="09920-231">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="09920-232">Aunque Visual Studio Code no viene con un instalador automatizado de .NET Core como Visual Studio, agregar compatibilidad con .NET Core es sencillo.</span><span class="sxs-lookup"><span data-stu-id="09920-232">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="09920-233">[Descargue e instale Visual Studio Code](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="09920-233">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="09920-234">[Descargue e instale el SDK de .NET Core](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="09920-234">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="09920-235">[Instale la extensión de C# desde el Marketplace de Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="09920-235">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

## <a name="install-with-bash-automation"></a><span data-ttu-id="09920-236">Instalación mediante la automatización de Bash</span><span class="sxs-lookup"><span data-stu-id="09920-236">Install with bash automation</span></span>

<span data-ttu-id="09920-237">Los [scripts de dotnet-install](../tools/dotnet-install-script.md) se usan para la automatización y las instalaciones que no son de administrador del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09920-237">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="09920-238">Se puede descargar el script desde la [página de referencia del script dotnet-install](../tools/dotnet-install-script.md).</span><span class="sxs-lookup"><span data-stu-id="09920-238">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="09920-239">El valor predeterminado del script es instalar la versión más reciente de [soporte técnico a largo plazo (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core), que actualmente es .NET Core 3.1.</span><span class="sxs-lookup"><span data-stu-id="09920-239">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="09920-240">Puede elegir una versión concreta especificando el modificador `current`.</span><span class="sxs-lookup"><span data-stu-id="09920-240">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="09920-241">Incluya el modificador `runtime` para instalar un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09920-241">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="09920-242">De lo contrario, el script instala el [SDK](sdk.md).</span><span class="sxs-lookup"><span data-stu-id="09920-242">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="09920-243">El comando anterior instala el entorno de ejecución de ASP.NET Core para obtener la máxima compatibilidad.</span><span class="sxs-lookup"><span data-stu-id="09920-243">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="09920-244">El entorno de ejecución de ASP.NET Core también incluye el estándar de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09920-244">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="docker"></a><span data-ttu-id="09920-245">Docker</span><span class="sxs-lookup"><span data-stu-id="09920-245">Docker</span></span>

<span data-ttu-id="09920-246">Los contenedores proporcionan una manera ligera de aislar la aplicación del resto del sistema host.</span><span class="sxs-lookup"><span data-stu-id="09920-246">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="09920-247">Los contenedores de la misma máquina comparten solo el kernel y usan los recursos proporcionados a la aplicación.</span><span class="sxs-lookup"><span data-stu-id="09920-247">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="09920-248">.NET Core puede ejecutarse en un contenedor de Docker.</span><span class="sxs-lookup"><span data-stu-id="09920-248">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="09920-249">Las imágenes oficiales de Docker en .NET Core se publican en el registro de contenedor de Microsoft (MCR) y se pueden encontrar en el [repositorio de Docker Hub para Microsoft .NET Core](https://hub.docker.com/_/microsoft-dotnet-core/).</span><span class="sxs-lookup"><span data-stu-id="09920-249">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="09920-250">Cada repositorio contiene imágenes para diferentes combinaciones de .NET (SDK o Runtime) y del sistema operativo que puede usar.</span><span class="sxs-lookup"><span data-stu-id="09920-250">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="09920-251">Microsoft ofrece imágenes que se adaptan a escenarios específicos.</span><span class="sxs-lookup"><span data-stu-id="09920-251">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="09920-252">Por ejemplo, el [repositorio de ASP.NET Core](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) proporciona imágenes que se compilan para ejecutar aplicaciones de ASP.NET Core en producción.</span><span class="sxs-lookup"><span data-stu-id="09920-252">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="09920-253">Para obtener más información sobre el uso de .NET Core en un contenedor de Docker, vea [Introducción a .NET y Docker](../docker/introduction.md) y [Ejemplos](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span><span class="sxs-lookup"><span data-stu-id="09920-253">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="09920-254">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="09920-254">Next steps</span></span>

- <span data-ttu-id="09920-255">[Cómo comprobar que .NET Core ya está instalado](how-to-detect-installed-versions.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="09920-255">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md?pivots=os-macos).</span></span>
- <span data-ttu-id="09920-256">[Trabajo con la certificación de macOS Catalina](macos-notarization-issues.md).</span><span class="sxs-lookup"><span data-stu-id="09920-256">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="09920-257">[Tutorial: Introducción a macOS](../tutorials/using-on-mac-vs.md).</span><span class="sxs-lookup"><span data-stu-id="09920-257">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="09920-258">[Tutorial: Creación de una aplicación con Visual Studio Code](../tutorials/with-visual-studio-code.md).</span><span class="sxs-lookup"><span data-stu-id="09920-258">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="09920-259">[Tutorial: Inclusión de una aplicación de .NET Core en un contenedor](../docker/build-container.md).</span><span class="sxs-lookup"><span data-stu-id="09920-259">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

[release-notes-21]: https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md
[release-notes-31]: https://github.com/dotnet/core/blob/master/release-notes/3.1/3.1-supported-os.md
[release-notes-50]: https://github.com/dotnet/core/blob/master/release-notes/5.0/5.0-supported-os.md
[release-notes-20]: https://github.com/dotnet/core/blob/master/release-notes/2.0/2.0-supported-os.md
[release-notes-22]: https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md
[release-notes-30]: https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md
