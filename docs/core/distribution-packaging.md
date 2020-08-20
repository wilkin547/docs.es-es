---
title: Empaquetado de distribución de .NET Core
description: Obtenga información sobre cómo empaquetar, nombrar y versionar .NET Core para su distribución.
author: tmds
ms.date: 10/09/2019
ms.openlocfilehash: 3324a6a151fc6dc46a8f13ea17c89da99d108d82
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062891"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="742ce-103">Empaquetado de distribución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="742ce-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="742ce-104">Como .NET Core está disponible cada vez en más plataformas, resulta útil aprender cómo empaquetarlo, nombrarlo y versionarlo.</span><span class="sxs-lookup"><span data-stu-id="742ce-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="742ce-105">De esta manera, los mantenedores de paquetes pueden ayudar a garantizar una experiencia coherente, independientemente de dónde los usuarios elijan ejecutar .NET.</span><span class="sxs-lookup"><span data-stu-id="742ce-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="742ce-106">Este artículo resultará útil para los usuarios que:</span><span class="sxs-lookup"><span data-stu-id="742ce-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="742ce-107">Intentan compilar .NET Core desde el origen.</span><span class="sxs-lookup"><span data-stu-id="742ce-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="742ce-108">Desean realizar cambios en la CLI de .NET Core que pueden afectar a la distribución o a los paquetes generados resultantes.</span><span class="sxs-lookup"><span data-stu-id="742ce-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="742ce-109">Diseño de disco</span><span class="sxs-lookup"><span data-stu-id="742ce-109">Disk layout</span></span>

<span data-ttu-id="742ce-110">Cuando se instala, .NET Core consta de varios componentes que están dispuestos tal y como se indica a continuación en el sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="742ce-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
{dotnet_root}                                     (*)
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host                                          (*)
│   └── fxr                                       (*)
│       └── <fxr version>        (2)
├── sdk                                           (*)
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)              (*)
├── packs                                         (*)
│   ├── Microsoft.AspNetCore.App.Ref              (*)
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref                 (*)
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>          (*)
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref          (*)
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref                   (*)
│       └── <netstandard version>        (15)
├── shared                                        (*)
│   ├── Microsoft.NETCore.App                     (*)
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App                  (*)
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All                  (*)
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App              (*)
│       └── <desktop app version> (7)
└── templates                                     (*)
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="742ce-111">(1) **dotnet**: el host (también conocido como "muxer") tiene dos roles diferentes: activar un entorno de ejecución para iniciar una aplicación y activar un SDK para enviarle comandos.</span><span class="sxs-lookup"><span data-stu-id="742ce-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="742ce-112">El host es un ejecutable nativo (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="742ce-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="742ce-113">Aunque hay un único host, la mayoría del resto de componentes está en directorios con versión (2,3,5,6).</span><span class="sxs-lookup"><span data-stu-id="742ce-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="742ce-114">Esto significa que puede haber varias versiones en el sistema ya que se instalan en paralelo.</span><span class="sxs-lookup"><span data-stu-id="742ce-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="742ce-115">(2) **host/fxr/\<fxr version>** contiene la lógica de resolución del marco que usa el host.</span><span class="sxs-lookup"><span data-stu-id="742ce-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="742ce-116">El host usa la versión más reciente de hostfxr que está instalada.</span><span class="sxs-lookup"><span data-stu-id="742ce-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="742ce-117">Hostfxr es responsable de seleccionar el entorno de ejecución adecuado cuando se ejecuta una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="742ce-118">Por ejemplo, una aplicación compilada para .NET Core 2.0.0 utiliza el runtime de 2.0.5 cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="742ce-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="742ce-119">De forma similar, hostfxr selecciona el SDK adecuado durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="742ce-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="742ce-120">(3) **sdk/\<sdk version>** El SDK (también conocido como "las herramientas") es un conjunto de herramientas administradas que se usa para escribir y compilar aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="742ce-121">El SDK incluye la CLI de .NET Core, los compiladores de lenguajes administrados, MSBuild y las tareas y los destinos de compilación asociados, NuGet, nuevas plantillas de proyecto, etc.</span><span class="sxs-lookup"><span data-stu-id="742ce-121">The SDK includes the .NET Core CLI, the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="742ce-122">(4) **sdk/NuGetFallbackFolder**: contiene una caché de paquetes NuGet que un SDK usa durante la operación de restauración, como cuando se ejecuta `dotnet restore` o `dotnet build`.</span><span class="sxs-lookup"><span data-stu-id="742ce-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build`.</span></span> <span data-ttu-id="742ce-123">Esta carpeta solo se usa antes de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="742ce-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="742ce-124">No se puede compilar desde el origen, porque contiene recursos binarios compilados previamente desde `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="742ce-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="742ce-125">La carpeta **shared** contiene marcos.</span><span class="sxs-lookup"><span data-stu-id="742ce-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="742ce-126">Un marco compartido proporciona un conjunto de bibliotecas en una ubicación central para que las puedan usar diferentes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="742ce-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="742ce-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** Este marco contiene el entorno de ejecución de .NET Core y compatibilidad con las bibliotecas administradas.</span><span class="sxs-lookup"><span data-stu-id="742ce-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="742ce-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contiene las bibliotecas de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="742ce-129">Las bibliotecas de `Microsoft.AspNetCore.App` se desarrollan y se admiten como parte del proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="742ce-130">Las bibliotecas de `Microsoft.AspNetCore.All` son un superconjunto que también contiene bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="742ce-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="742ce-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contiene las bibliotecas de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="742ce-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="742ce-132">Esto no se incluye en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="742ce-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="742ce-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**: son las licencias .NET Core y de bibliotecas de terceros que se usan en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="742ce-134">(9,10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` es la página manual de dotnet.</span><span class="sxs-lookup"><span data-stu-id="742ce-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="742ce-135">`dotnet` es un vínculo simbólico al host(1) de dotnet.</span><span class="sxs-lookup"><span data-stu-id="742ce-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="742ce-136">Estos archivos se instalan en ubicaciones bien conocidas para la integración del sistema.</span><span class="sxs-lookup"><span data-stu-id="742ce-136">These files are installed at well-known locations for system integration.</span></span>

- <span data-ttu-id="742ce-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref**: describe la API de una versión `x.y` de .NET Core y de ASP.NET Core respectivamente.</span><span class="sxs-lookup"><span data-stu-id="742ce-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="742ce-138">Estos paquetes se utilizan al compilar para esas versiones de destino.</span><span class="sxs-lookup"><span data-stu-id="742ce-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="742ce-139">(13) **Microsoft.NETCore.App.Host.\<rid>**</span><span class="sxs-lookup"><span data-stu-id="742ce-139">(13) **Microsoft.NETCore.App.Host.\<rid>**</span></span> <span data-ttu-id="742ce-140">contiene un binario nativo para la plataforma `rid`.</span><span class="sxs-lookup"><span data-stu-id="742ce-140">contains a native binary for platform `rid`.</span></span> <span data-ttu-id="742ce-141">Este binario es una plantilla cuando se compila una aplicación de .NET Core en un archivo binario nativo para esa plataforma.</span><span class="sxs-lookup"><span data-stu-id="742ce-141">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="742ce-142">(14) **Microsoft.WindowsDesktop.App.Ref**: describe la API de la versión `x.y` de las aplicaciones de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="742ce-142">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="742ce-143">Estos archivos se usan al compilar para ese destino.</span><span class="sxs-lookup"><span data-stu-id="742ce-143">These files are used when compiling for that target.</span></span> <span data-ttu-id="742ce-144">Esto no se proporciona en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="742ce-144">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="742ce-145">(15) **NETStandard.Library.Ref**: describe la API `x.y` de netstandard.</span><span class="sxs-lookup"><span data-stu-id="742ce-145">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="742ce-146">Estos archivos se usan al compilar para ese destino.</span><span class="sxs-lookup"><span data-stu-id="742ce-146">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="742ce-147">(16) **/etc/dotnet/install_location**: es un archivo que contiene la ruta de acceso completa a `{dotnet_root}`.</span><span class="sxs-lookup"><span data-stu-id="742ce-147">(16) **/etc/dotnet/install_location** is a file that contains the full path for `{dotnet_root}`.</span></span> <span data-ttu-id="742ce-148">La ruta de acceso puede terminar con una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="742ce-148">The path may end with a newline.</span></span> <span data-ttu-id="742ce-149">No es necesario agregar este archivo cuando la raíz es `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="742ce-149">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="742ce-150">(17) **templates**: contiene las plantillas que usa el SDK.</span><span class="sxs-lookup"><span data-stu-id="742ce-150">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="742ce-151">Por ejemplo, `dotnet new` busca plantillas de proyecto aquí.</span><span class="sxs-lookup"><span data-stu-id="742ce-151">For example, `dotnet new` finds project templates here.</span></span>

<span data-ttu-id="742ce-152">Varios paquetes usan las carpetas marcadas con `(*)`.</span><span class="sxs-lookup"><span data-stu-id="742ce-152">The folders marked with `(*)` are used by multiple packages.</span></span> <span data-ttu-id="742ce-153">Algunos formatos de paquete (por ejemplo, `rpm`) requieren un tratamiento especial de esas carpetas.</span><span class="sxs-lookup"><span data-stu-id="742ce-153">Some package formats (for example, `rpm`) require special handling of such folders.</span></span> <span data-ttu-id="742ce-154">El mantenedor de paquetes debe encargarse de esto.</span><span class="sxs-lookup"><span data-stu-id="742ce-154">The package maintainer must take care of this.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="742ce-155">Paquetes recomendados</span><span class="sxs-lookup"><span data-stu-id="742ce-155">Recommended packages</span></span>

<span data-ttu-id="742ce-156">El control de versiones de .NET Core se basa en los números de versión `[major].[minor]` del componente del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="742ce-156">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="742ce-157">La versión del SDK usa el mismo valor `[major].[minor]` y tiene un valor `[patch]` independiente que combina la semántica de la característica y la revisión del SDK.</span><span class="sxs-lookup"><span data-stu-id="742ce-157">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="742ce-158">Por ejemplo: la versión 2.2.302 del SDK es la segunda versión de revisión de la tercera versión de características del SDK que admite el runtime 2.2.</span><span class="sxs-lookup"><span data-stu-id="742ce-158">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="742ce-159">Para obtener más información sobre el funcionamiento del control de versiones, vea [Introducción a la creación de versiones de .NET Core](./versions/index.md).</span><span class="sxs-lookup"><span data-stu-id="742ce-159">For more information about how versioning works, see [.NET Core versioning overview](./versions/index.md).</span></span>

<span data-ttu-id="742ce-160">Algunos de los paquetes incluyen parte del número de versión en su nombre.</span><span class="sxs-lookup"><span data-stu-id="742ce-160">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="742ce-161">Esto permite instalar una versión concreta.</span><span class="sxs-lookup"><span data-stu-id="742ce-161">This allows you to install a specific version.</span></span>
<span data-ttu-id="742ce-162">No se incluye el resto de la versión en el nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="742ce-162">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="742ce-163">Esto permite al administrador de paquetes del sistema operativo actualizar los paquetes (por ejemplo, instalar automáticamente correcciones de seguridad).</span><span class="sxs-lookup"><span data-stu-id="742ce-163">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="742ce-164">Los administradores de paquetes compatibles son específicos de Linux.</span><span class="sxs-lookup"><span data-stu-id="742ce-164">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="742ce-165">A continuación se enumeran los paquetes recomendados:</span><span class="sxs-lookup"><span data-stu-id="742ce-165">The following lists the recommended packages:</span></span>

- <span data-ttu-id="742ce-166">`dotnet-sdk-[major].[minor]`: instala el SDK más reciente del runtime concreto.</span><span class="sxs-lookup"><span data-stu-id="742ce-166">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="742ce-167">**Versión:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="742ce-167">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="742ce-168">**Ejemplo:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="742ce-168">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="742ce-169">**Contiene:** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="742ce-169">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="742ce-170">**Dependencias:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]` y `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="742ce-170">**Dependencies:** `dotnet-runtime-[major].[minor]`, `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="742ce-171">`aspnetcore-runtime-[major].[minor]`: instala un runtime concreto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-171">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="742ce-172">**Versión:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-172">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="742ce-173">**Ejemplo:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="742ce-173">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="742ce-174">**Contiene:** (6)</span><span class="sxs-lookup"><span data-stu-id="742ce-174">**Contains:** (6)</span></span>
  - <span data-ttu-id="742ce-175">**Dependencias:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="742ce-175">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="742ce-176">`dotnet-runtime-deps-[major].[minor]` _(Opcional)_ : instala las dependencias para ejecutar aplicaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="742ce-176">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="742ce-177">**Version:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-178">**Ejemplo:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="742ce-178">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="742ce-179">**Dependencias:** _dependencias específicas de la distribución_</span><span class="sxs-lookup"><span data-stu-id="742ce-179">**Dependencies:** _distribution-specific dependencies_</span></span>

- <span data-ttu-id="742ce-180">`dotnet-runtime-[major].[minor]`: instala un runtime concreto.</span><span class="sxs-lookup"><span data-stu-id="742ce-180">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="742ce-181">**Versión:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-181">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-182">**Ejemplo:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="742ce-182">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="742ce-183">**Contiene:** (5)</span><span class="sxs-lookup"><span data-stu-id="742ce-183">**Contains:** (5)</span></span>
  - <span data-ttu-id="742ce-184">**Dependencias:** `dotnet-hostfxr-[major].[minor]` y `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="742ce-184">**Dependencies:** `dotnet-hostfxr-[major].[minor]`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="742ce-185">`dotnet-hostfxr-[major].[minor]`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="742ce-185">`dotnet-hostfxr-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="742ce-186">**Versión:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-186">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-187">**Ejemplo:** dotnet-hostfxr-3.0</span><span class="sxs-lookup"><span data-stu-id="742ce-187">**Example:** dotnet-hostfxr-3.0</span></span>
  - <span data-ttu-id="742ce-188">**Contiene:** (2)</span><span class="sxs-lookup"><span data-stu-id="742ce-188">**Contains:** (2)</span></span>
  - <span data-ttu-id="742ce-189">**Dependencias:** `dotnet-host`</span><span class="sxs-lookup"><span data-stu-id="742ce-189">**Dependencies:** `dotnet-host`</span></span>

- <span data-ttu-id="742ce-190">`dotnet-host`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="742ce-190">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="742ce-191">**Versión:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-192">**Ejemplo:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="742ce-192">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="742ce-193">**Contiene:** (1), (8), (9), (10), (16)</span><span class="sxs-lookup"><span data-stu-id="742ce-193">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="742ce-194">`dotnet-apphost-pack-[major].[minor]`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="742ce-194">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="742ce-195">**Versión:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-195">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-196">**Contiene:** (13)</span><span class="sxs-lookup"><span data-stu-id="742ce-196">**Contains:** (13)</span></span>

- <span data-ttu-id="742ce-197">`dotnet-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.</span><span class="sxs-lookup"><span data-stu-id="742ce-197">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="742ce-198">**Versión:** \<runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-198">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="742ce-199">**Contiene:** (12)</span><span class="sxs-lookup"><span data-stu-id="742ce-199">**Contains:** (12)</span></span>

- <span data-ttu-id="742ce-200">`aspnetcore-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.</span><span class="sxs-lookup"><span data-stu-id="742ce-200">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="742ce-201">**Versión:** \<aspnetcore runtime version></span><span class="sxs-lookup"><span data-stu-id="742ce-201">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="742ce-202">**Contiene:** (11)</span><span class="sxs-lookup"><span data-stu-id="742ce-202">**Contains:** (11)</span></span>

- <span data-ttu-id="742ce-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`: permite establecer como destino una versión de netstandard.</span><span class="sxs-lookup"><span data-stu-id="742ce-203">`netstandard-targeting-pack-[netstandard_major].[netstandard_minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="742ce-204">**Versión:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="742ce-204">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="742ce-205">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="742ce-205">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="742ce-206">**Versión:** \<sdk version></span><span class="sxs-lookup"><span data-stu-id="742ce-206">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="742ce-207">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="742ce-207">**Contains:** (15)</span></span>

<span data-ttu-id="742ce-208">`dotnet-runtime-deps-[major].[minor]` requiere el conocimiento de las _dependencias concretas de distribución_.</span><span class="sxs-lookup"><span data-stu-id="742ce-208">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro-specific dependencies_.</span></span> <span data-ttu-id="742ce-209">Dado que el sistema de compilación de distribución puede derivar esto de forma automática, el paquete es opcional, en cuyo caso estas dependencias se agregan directamente al paquete `dotnet-runtime-[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="742ce-209">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="742ce-210">Cuando el contenido del paquete se encuentra en una carpeta con versión, el nombre del paquete `[major].[minor]` coincide con el nombre de la carpeta con versión.</span><span class="sxs-lookup"><span data-stu-id="742ce-210">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="742ce-211">En todos los paquetes, excepto en `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, esto también coincide con la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="742ce-211">For all packages, except the `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="742ce-212">Las dependencias entre paquetes deben usar un requisito de versión _igual o mayor que_.</span><span class="sxs-lookup"><span data-stu-id="742ce-212">Dependencies between packages should use an _equal or greater than_ version requirement.</span></span> <span data-ttu-id="742ce-213">Por ejemplo, `dotnet-sdk-2.2:2.2.401` requiere `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="742ce-213">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="742ce-214">Esto hace posible que el usuario actualice su instalación mediante un paquete raíz (por ejemplo, `dnf update dotnet-sdk-2.2`).</span><span class="sxs-lookup"><span data-stu-id="742ce-214">This makes it possible for the user to upgrade their installation via a root package (for example, `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="742ce-215">La mayoría de las distribuciones requieren que todos los artefactos se compilen desde el origen.</span><span class="sxs-lookup"><span data-stu-id="742ce-215">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="742ce-216">Esto tiene algún impacto en los paquetes:</span><span class="sxs-lookup"><span data-stu-id="742ce-216">This has some impact on the packages:</span></span>

- <span data-ttu-id="742ce-217">Las bibliotecas de terceros de `shared/Microsoft.AspNetCore.All` no se pueden compilar fácilmente desde el origen.</span><span class="sxs-lookup"><span data-stu-id="742ce-217">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="742ce-218">Por tanto, se omite esa carpeta en el paquete `aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="742ce-218">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="742ce-219">La carpeta `NuGetFallbackFolder` se rellena con artefactos binarios desde `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="742ce-219">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="742ce-220">Debe permanecer vacía.</span><span class="sxs-lookup"><span data-stu-id="742ce-220">It should remain empty.</span></span>

<span data-ttu-id="742ce-221">Es posible que varios paquetes `dotnet-sdk` proporcionen los mismos archivos para la carpeta `NuGetFallbackFolder`.</span><span class="sxs-lookup"><span data-stu-id="742ce-221">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="742ce-222">Para evitar problemas con el administrador de paquetes, estos archivos deben ser idénticos (suma de comprobación, fecha de modificación, etc.).</span><span class="sxs-lookup"><span data-stu-id="742ce-222">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="742ce-223">Compilar paquetes</span><span class="sxs-lookup"><span data-stu-id="742ce-223">Building packages</span></span>

<span data-ttu-id="742ce-224">El repositorio [dotnet/source-build](https://github.com/dotnet/source-build) proporciona instrucciones sobre cómo crear un paquete tarball de origen del SDK de .NET Core y todos sus componentes.</span><span class="sxs-lookup"><span data-stu-id="742ce-224">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="742ce-225">La salida del repositorio de compilación de código fuente coincide con el diseño que se describe en la primera sección de este artículo.</span><span class="sxs-lookup"><span data-stu-id="742ce-225">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
