---
title: Empaquetado de distribución de .NET Core
description: Obtenga información sobre cómo empaquetar, nombrar y versionar .NET Core para su distribución.
author: tmds
ms.date: 03/02/2018
ms.custom: seodec18
ms.openlocfilehash: d72677cba1e7685f8e05cf479ec508683dd77b55
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2019
ms.locfileid: "70394159"
---
# <a name="net-core-distribution-packaging"></a><span data-ttu-id="09814-103">Empaquetado de distribución de .NET Core</span><span class="sxs-lookup"><span data-stu-id="09814-103">.NET Core distribution packaging</span></span>

<span data-ttu-id="09814-104">Como .NET Core está disponible cada vez en más plataformas, resulta útil aprender cómo empaquetarlo, nombrarlo y versionarlo.</span><span class="sxs-lookup"><span data-stu-id="09814-104">As .NET Core becomes available on more and more platforms, it's useful to learn how to package, name, and version it.</span></span> <span data-ttu-id="09814-105">De esta manera, los mantenedores de paquetes pueden ayudar a garantizar una experiencia coherente, independientemente de dónde los usuarios elijan ejecutar .NET.</span><span class="sxs-lookup"><span data-stu-id="09814-105">This way, package maintainers can help ensure a consistent experience no matter where users choose to run .NET.</span></span> <span data-ttu-id="09814-106">Este artículo resultará útil para los usuarios que:</span><span class="sxs-lookup"><span data-stu-id="09814-106">This article is useful for users that are:</span></span>

- <span data-ttu-id="09814-107">Intentan compilar .NET Core desde el origen.</span><span class="sxs-lookup"><span data-stu-id="09814-107">Attempting to build .NET Core from source.</span></span>
- <span data-ttu-id="09814-108">Desean realizar cambios en la CLI de .NET Core que pueden afectar a la distribución o a los paquetes generados resultantes.</span><span class="sxs-lookup"><span data-stu-id="09814-108">Wanting to make changes to the .NET Core CLI that could impact the resulting layout or packages produced.</span></span>

## <a name="disk-layout"></a><span data-ttu-id="09814-109">Diseño de disco</span><span class="sxs-lookup"><span data-stu-id="09814-109">Disk layout</span></span>

<span data-ttu-id="09814-110">Cuando se instala, .NET Core consta de varios componentes que están dispuestos tal y como se indica a continuación en el sistema de archivos:</span><span class="sxs-lookup"><span data-stu-id="09814-110">When installed, .NET Core consists of several components that are laid out as follows in the filesystem:</span></span>

```
.
├── dotnet                       (1)
├── LICENSE.txt                  (8)
├── ThirdPartyNotices.txt        (8)
├── host
│   └── fxr
│       └── <fxr version>        (2)
├── sdk
│   ├── <sdk version>            (3)
│   └── NuGetFallbackFolder      (4)
├── packs
│   ├── Microsoft.AspNetCore.App.Ref
│   │   └── <aspnetcore ref version>     (11)
│   ├── Microsoft.NETCore.App.Ref
│   │   └── <netcore ref version>        (12)
│   ├── Microsoft.NETCore.App.Host.<rid>
│   │   └── <apphost version>            (13)
│   ├── Microsoft.WindowsDesktop.App.Ref
│   │   └── <desktop ref version>        (14)
│   └── NETStandard.Library.Ref
│       └── <netstandard version>        (15)
├── shared
│   ├── Microsoft.NETCore.App
│   │   └── <runtime version>     (5)
│   ├── Microsoft.AspNetCore.App
│   │   └── <aspnetcore version>  (6)
│   ├── Microsoft.AspNetCore.All
│   │   └── <aspnetcore version>  (6)
│   └── Microsoft.WindowsDesktop.App
│       └── <desktop app version> (7)
└── templates
│   └── <templates version>      (17)
/
├── etc/dotnet
│       └── install_location     (16)
├── usr/share/man/man1
│       └── dotnet.1.gz          (9)
└── usr/bin
        └── dotnet               (10)
```

- <span data-ttu-id="09814-111">(1) **dotnet**: el host (también conocido como "muxer") tiene dos roles diferentes: activar un entorno de ejecución para iniciar una aplicación y activar un SDK para enviarle comandos.</span><span class="sxs-lookup"><span data-stu-id="09814-111">(1) **dotnet** The host (also known as the "muxer") has two distinct roles: activate a runtime to launch an application, and activate an SDK to dispatch commands to it.</span></span> <span data-ttu-id="09814-112">El host es un ejecutable nativo (`dotnet.exe`).</span><span class="sxs-lookup"><span data-stu-id="09814-112">The host is a native executable (`dotnet.exe`).</span></span>

<span data-ttu-id="09814-113">Aunque hay un único host, la mayoría del resto de componentes está en directorios con versión (2,3,5,6).</span><span class="sxs-lookup"><span data-stu-id="09814-113">While there's a single host, most of the other components are in versioned directories (2,3,5,6).</span></span> <span data-ttu-id="09814-114">Esto significa que puede haber varias versiones en el sistema ya que se instalan en paralelo.</span><span class="sxs-lookup"><span data-stu-id="09814-114">This means multiple versions can be present on the system since they're installed side by side.</span></span>

- <span data-ttu-id="09814-115">(2) **host/fxr/\<versión de fxr>**: contiene la lógica de resolución del marco que usa el host.</span><span class="sxs-lookup"><span data-stu-id="09814-115">(2) **host/fxr/\<fxr version>** contains the framework resolution logic used by the host.</span></span> <span data-ttu-id="09814-116">El host usa la versión más reciente de hostfxr que está instalada.</span><span class="sxs-lookup"><span data-stu-id="09814-116">The host uses the latest hostfxr that is installed.</span></span> <span data-ttu-id="09814-117">Hostfxr es responsable de seleccionar el entorno de ejecución adecuado cuando se ejecuta una aplicación de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-117">The hostfxr is responsible for selecting the appropriate runtime when executing a .NET Core application.</span></span> <span data-ttu-id="09814-118">Por ejemplo, una aplicación compilada para .NET Core 2.0.0 utiliza el runtime de 2.0.5 cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="09814-118">For example, an application built for .NET Core 2.0.0 uses the 2.0.5 runtime when it's available.</span></span> <span data-ttu-id="09814-119">De forma similar, hostfxr selecciona el SDK adecuado durante el desarrollo.</span><span class="sxs-lookup"><span data-stu-id="09814-119">Similarly, hostfxr selects the appropriate SDK during development.</span></span>

- <span data-ttu-id="09814-120">(3) **sdk/\<versión sdk>**: el SDK (también conocido como "las herramientas") es un conjunto de herramientas administradas que se usan para escribir y compilar aplicaciones y bibliotecas de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-120">(3) **sdk/\<sdk version>** The SDK (also known as "the tooling") is a set of managed tools that are used to write and build .NET Core libraries and applications.</span></span> <span data-ttu-id="09814-121">El SDK incluye la interfaz de línea de comandos (CLI) de .NET Core, los compiladores de lenguajes administrados, MSBuild y las tareas y los destinos de compilación asociados, NuGet, nuevas plantillas de proyecto, etcétera.</span><span class="sxs-lookup"><span data-stu-id="09814-121">The SDK includes the .NET Core Command-line interface (CLI), the managed languages compilers, MSBuild, and associated build tasks and targets, NuGet, new project templates, and so on.</span></span>

- <span data-ttu-id="09814-122">(4) **sdk/NuGetFallbackFolder**: contiene una caché de paquetes NuGet que un SDK usa durante la operación de restauración, como cuando se ejecuta `dotnet restore` o `dotnet build /t:Restore`.</span><span class="sxs-lookup"><span data-stu-id="09814-122">(4) **sdk/NuGetFallbackFolder** contains a cache of NuGet packages used by an SDK during the restore operation, such as when running `dotnet restore` or `dotnet build /t:Restore`.</span></span> <span data-ttu-id="09814-123">Esta carpeta solo se usa antes de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="09814-123">This folder is only used prior to .NET Core 3.0.</span></span> <span data-ttu-id="09814-124">No se puede compilar desde el origen, porque contiene recursos binarios compilados previamente desde `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="09814-124">It can't be built from source, because it contains prebuilt binary assets from `nuget.org`.</span></span>

<span data-ttu-id="09814-125">La carpeta **shared** contiene marcos.</span><span class="sxs-lookup"><span data-stu-id="09814-125">The **shared** folder contains frameworks.</span></span> <span data-ttu-id="09814-126">Un marco compartido proporciona un conjunto de bibliotecas en una ubicación central para que las puedan usar diferentes aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="09814-126">A shared framework provides a set of libraries at a central location so they can be used by different applications.</span></span>

- <span data-ttu-id="09814-127">(5) **shared/Microsoft.NETCore.App/\<versión del entorno de ejecución>**: este marco contiene el entorno de ejecución de .NET Core y compatibilidad con las bibliotecas administradas.</span><span class="sxs-lookup"><span data-stu-id="09814-127">(5) **shared/Microsoft.NETCore.App/\<runtime version>** This framework contains the .NET Core runtime and supporting managed libraries.</span></span>

- <span data-ttu-id="09814-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<versión de aspnetcore>**: contiene las bibliotecas de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-128">(6) **shared/Microsoft.AspNetCore.{App,All}/\<aspnetcore version>** contains the ASP.NET Core libraries.</span></span> <span data-ttu-id="09814-129">Las bibliotecas de `Microsoft.AspNetCore.App` se desarrollan y se admiten como parte del proyecto de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-129">The libraries under `Microsoft.AspNetCore.App` are developed and supported as part of the .NET Core project.</span></span> <span data-ttu-id="09814-130">Las bibliotecas de `Microsoft.AspNetCore.All` son un superconjunto que también contiene bibliotecas de terceros.</span><span class="sxs-lookup"><span data-stu-id="09814-130">The libraries under `Microsoft.AspNetCore.All` are a superset that also contains third-party libraries.</span></span>

- <span data-ttu-id="09814-131">(7) **shared/Microsoft.Desktop.App/\<versión de aplicación de escritorio>**: contiene las bibliotecas de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="09814-131">(7) **shared/Microsoft.Desktop.App/\<desktop app version>** contains the Windows desktop libraries.</span></span> <span data-ttu-id="09814-132">Esto no se incluye en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="09814-132">This isn't included on non-Windows platforms.</span></span>

- <span data-ttu-id="09814-133">(8) **LICENSE.txt,ThirdPartyNotices.txt**: son las licencias .NET Core y de bibliotecas de terceros que se usan en .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-133">(8) **LICENSE.txt,ThirdPartyNotices.txt** are the .NET Core license and licenses of third-party libraries used in .NET Core, respectively.</span></span>

- <span data-ttu-id="09814-134">(9,10) **dotnet.1.gz, dotnet**: `dotnet.1.gz` es la página manual de dotnet.</span><span class="sxs-lookup"><span data-stu-id="09814-134">(9,10) **dotnet.1.gz, dotnet** `dotnet.1.gz` is the dotnet manual page.</span></span> <span data-ttu-id="09814-135">`dotnet` es un vínculo simbólico al host(1) de dotnet.</span><span class="sxs-lookup"><span data-stu-id="09814-135">`dotnet` is a symlink to the dotnet host(1).</span></span> <span data-ttu-id="09814-136">Estos archivos se instalan en ubicaciones bien conocidas para la integración del sistema.</span><span class="sxs-lookup"><span data-stu-id="09814-136">These files are installed at well known locations for system integration.</span></span>

- <span data-ttu-id="09814-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref**: describe la API de una versión `x.y` de .NET Core y de ASP.NET Core respectivamente.</span><span class="sxs-lookup"><span data-stu-id="09814-137">(11,12) **Microsoft.NETCore.App.Ref,Microsoft.AspNetCore.App.Ref** describe the API of an `x.y` version of .NET Core and ASP.NET Core respectively.</span></span> <span data-ttu-id="09814-138">Estos paquetes se utilizan al compilar para esas versiones de destino.</span><span class="sxs-lookup"><span data-stu-id="09814-138">These packs are used when compiling for those target versions.</span></span>

- <span data-ttu-id="09814-139">(13) **Microsoft.NETCore.App.Host.\<rid>**: contiene un binario nativo para la plataforma `rid`.</span><span class="sxs-lookup"><span data-stu-id="09814-139">(13) **Microsoft.NETCore.App.Host.\<rid>** contains a native binary for platform `rid`.</span></span> <span data-ttu-id="09814-140">Este binario es una plantilla cuando se compila una aplicación de .NET Core en un archivo binario nativo para esa plataforma.</span><span class="sxs-lookup"><span data-stu-id="09814-140">This binary is a template when compiling a .NET Core application into a native binary for that platform.</span></span>

- <span data-ttu-id="09814-141">(14) **Microsoft.WindowsDesktop.App.Ref**: describe la API de la versión `x.y` de las aplicaciones de escritorio de Windows.</span><span class="sxs-lookup"><span data-stu-id="09814-141">(14) **Microsoft.WindowsDesktop.App.Ref** describes the API of `x.y` version of Windows Desktop applications.</span></span> <span data-ttu-id="09814-142">Estos archivos se usan al compilar para ese destino.</span><span class="sxs-lookup"><span data-stu-id="09814-142">These files are used when compiling for that target.</span></span> <span data-ttu-id="09814-143">Esto no se proporciona en plataformas que no son de Windows.</span><span class="sxs-lookup"><span data-stu-id="09814-143">This isn't provided on non-Windows platforms.</span></span>

- <span data-ttu-id="09814-144">(15) **NETStandard.Library.Ref**: describe la API `x.y` de netstandard.</span><span class="sxs-lookup"><span data-stu-id="09814-144">(15) **NETStandard.Library.Ref** describes the netstandard `x.y` API.</span></span> <span data-ttu-id="09814-145">Estos archivos se usan al compilar para ese destino.</span><span class="sxs-lookup"><span data-stu-id="09814-145">These files are used when compiling for that target.</span></span>

- <span data-ttu-id="09814-146">(16) **/etc/dotnet/install_location**: es un archivo que contiene la ruta de acceso completa a la carpeta que contiene el binario del host `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="09814-146">(16) **/etc/dotnet/install_location** is a file that contains the full path to the folder that contains the `dotnet` host binary.</span></span> <span data-ttu-id="09814-147">La ruta de acceso puede terminar con una nueva línea.</span><span class="sxs-lookup"><span data-stu-id="09814-147">The path may be terminated with a newline.</span></span> <span data-ttu-id="09814-148">No es necesario agregar este archivo cuando la raíz es `/usr/share/dotnet`.</span><span class="sxs-lookup"><span data-stu-id="09814-148">It's not necessary to add this file when the root is `/usr/share/dotnet`.</span></span>

- <span data-ttu-id="09814-149">(17) **templates**: contiene las plantillas que usa el SDK.</span><span class="sxs-lookup"><span data-stu-id="09814-149">(17) **templates** contains the templates used by the SDK.</span></span> <span data-ttu-id="09814-150">Por ejemplo, `dotnet new` busca plantillas de proyecto aquí.</span><span class="sxs-lookup"><span data-stu-id="09814-150">For example, `dotnet new` finds project templates here.</span></span>

## <a name="recommended-packages"></a><span data-ttu-id="09814-151">Paquetes recomendados</span><span class="sxs-lookup"><span data-stu-id="09814-151">Recommended packages</span></span>

<span data-ttu-id="09814-152">El control de versiones de .NET Core se basa en los números de versión `[major].[minor]` del componente del entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09814-152">.NET Core versioning is based on the runtime component `[major].[minor]` version numbers.</span></span>
<span data-ttu-id="09814-153">La versión del SDK usa el mismo valor `[major].[minor]` y tiene un valor `[patch]` independiente que combina la semántica de la característica y la revisión del SDK.</span><span class="sxs-lookup"><span data-stu-id="09814-153">The SDK version uses the same `[major].[minor]` and has an independent `[patch]` that combines feature and patch semantics for the SDK.</span></span>
<span data-ttu-id="09814-154">Por ejemplo:  la versión 2.2.302 del SDK es la segunda versión de revisión de la tercera versión de características del SDK que admite el runtime 2.2.</span><span class="sxs-lookup"><span data-stu-id="09814-154">For example: SDK version 2.2.302 is the second patch release of the third feature release of the SDK that supports the 2.2 runtime.</span></span> <span data-ttu-id="09814-155">Para obtener más información sobre el funcionamiento del control de versiones, vea [.NET Core versioning overview](../versions/index.md) (Introducción al control de versiones de .NET Core).</span><span class="sxs-lookup"><span data-stu-id="09814-155">For more information about how versioning works, see [.NET Core versioning overview](../versions/index.md).</span></span>

<span data-ttu-id="09814-156">Algunos de los paquetes incluyen parte del número de versión en su nombre.</span><span class="sxs-lookup"><span data-stu-id="09814-156">Some of the packages include part of the version number in their name.</span></span> <span data-ttu-id="09814-157">Esto permite instalar una versión concreta.</span><span class="sxs-lookup"><span data-stu-id="09814-157">This allows you to install a specific version.</span></span>
<span data-ttu-id="09814-158">No se incluye el resto de la versión en el nombre de la versión.</span><span class="sxs-lookup"><span data-stu-id="09814-158">The rest of the version isn't included in the version name.</span></span> <span data-ttu-id="09814-159">Esto permite al administrador de paquetes del sistema operativo actualizar los paquetes (por ejemplo, instalar automáticamente correcciones de seguridad).</span><span class="sxs-lookup"><span data-stu-id="09814-159">This allows the OS package manager to update the packages (for example, automatically installing security fixes).</span></span> <span data-ttu-id="09814-160">Los administradores de paquetes compatibles son específicos de Linux.</span><span class="sxs-lookup"><span data-stu-id="09814-160">Supported package managers are Linux specific.</span></span>

<span data-ttu-id="09814-161">A continuación se enumeran los paquetes recomendados:</span><span class="sxs-lookup"><span data-stu-id="09814-161">The following lists the recommended packages:</span></span>

- <span data-ttu-id="09814-162">`dotnet-sdk-[major].[minor]`: instala el SDK más reciente del runtime concreto.</span><span class="sxs-lookup"><span data-stu-id="09814-162">`dotnet-sdk-[major].[minor]` - Installs the latest sdk for specific runtime</span></span>
  - <span data-ttu-id="09814-163">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-163">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-164">**Ejemplo:** dotnet-sdk-2.1</span><span class="sxs-lookup"><span data-stu-id="09814-164">**Example:** dotnet-sdk-2.1</span></span>
  - <span data-ttu-id="09814-165">**Contiene:** (3),(4)</span><span class="sxs-lookup"><span data-stu-id="09814-165">**Contains:** (3),(4)</span></span>
  - <span data-ttu-id="09814-166">**Dependencias:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="09814-166">**Dependencies:** `aspnetcore-runtime-[major].[minor]`, `dotnet-targeting-pack-[major].[minor]`, `aspnetcore-targeting-pack-[major].[minor]`, `netstandard-targeting-pack-[netstandard_major].[netstandard_minor]`, `dotnet-apphost-pack-[major].[minor]`, `dotnet-templates-[major].[minor]`</span></span>

- <span data-ttu-id="09814-167">`aspnetcore-runtime-[major].[minor]`: instala un runtime concreto de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-167">`aspnetcore-runtime-[major].[minor]` - Installs a specific ASP.NET Core runtime</span></span>
  - <span data-ttu-id="09814-168">**Versión:** \<versión aspnetcore de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-168">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="09814-169">**Ejemplo:** aspnetcore-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="09814-169">**Example:** aspnetcore-runtime-2.1</span></span>
  - <span data-ttu-id="09814-170">**Contiene:**  (6)</span><span class="sxs-lookup"><span data-stu-id="09814-170">**Contains:** (6)</span></span>
  - <span data-ttu-id="09814-171">**Dependencias:** `dotnet-runtime-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="09814-171">**Dependencies:** `dotnet-runtime-[major].[minor]`</span></span>

- <span data-ttu-id="09814-172">`dotnet-runtime-deps-[major].[minor]` _(Opcional)_: instala las dependencias para ejecutar aplicaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="09814-172">`dotnet-runtime-deps-[major].[minor]` _(Optional)_ - Installs the dependencies for running self-contained applications</span></span>
  - <span data-ttu-id="09814-173">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-173">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-174">**Ejemplo:** dotnet-runtime-deps-2.1</span><span class="sxs-lookup"><span data-stu-id="09814-174">**Example:** dotnet-runtime-deps-2.1</span></span>
  - <span data-ttu-id="09814-175">**Dependencias:** _dependencias concretas de distribución_</span><span class="sxs-lookup"><span data-stu-id="09814-175">**Dependencies:** _distro specific dependencies_</span></span>

- <span data-ttu-id="09814-176">`dotnet-runtime-[major].[minor]`: instala un runtime concreto.</span><span class="sxs-lookup"><span data-stu-id="09814-176">`dotnet-runtime-[major].[minor]` - Installs a specific runtime</span></span>
  - <span data-ttu-id="09814-177">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-177">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-178">**Ejemplo:** dotnet-runtime-2.1</span><span class="sxs-lookup"><span data-stu-id="09814-178">**Example:** dotnet-runtime-2.1</span></span>
  - <span data-ttu-id="09814-179">**Contiene:** (5)</span><span class="sxs-lookup"><span data-stu-id="09814-179">**Contains:** (5)</span></span>
  - <span data-ttu-id="09814-180">**Dependencias:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span><span class="sxs-lookup"><span data-stu-id="09814-180">**Dependencies:** `dotnet-hostfxr:<runtime version>+`, `dotnet-runtime-deps-[major].[minor]`</span></span>

- <span data-ttu-id="09814-181">`dotnet-hostfxr`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="09814-181">`dotnet-hostfxr` - dependency</span></span>
  - <span data-ttu-id="09814-182">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-182">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-183">**Ejemplo:** dotnet-hostfxr</span><span class="sxs-lookup"><span data-stu-id="09814-183">**Example:** dotnet-hostfxr</span></span>
  - <span data-ttu-id="09814-184">**Contiene:** (2)</span><span class="sxs-lookup"><span data-stu-id="09814-184">**Contains:** (2)</span></span>
  - <span data-ttu-id="09814-185">**Dependencias:** `host:<runtime version>+`</span><span class="sxs-lookup"><span data-stu-id="09814-185">**Dependencies:** `host:<runtime version>+`</span></span>

- <span data-ttu-id="09814-186">`dotnet-host`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="09814-186">`dotnet-host` - dependency</span></span>
  - <span data-ttu-id="09814-187">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-187">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-188">**Ejemplo:** dotnet-host</span><span class="sxs-lookup"><span data-stu-id="09814-188">**Example:** dotnet-host</span></span>
  - <span data-ttu-id="09814-189">**Contiene:** (1), (8), (9), (10), (16)</span><span class="sxs-lookup"><span data-stu-id="09814-189">**Contains:** (1),(8),(9),(10),(16)</span></span>

- <span data-ttu-id="09814-190">`dotnet-apphost-pack-[major].[minor]`: dependencia.</span><span class="sxs-lookup"><span data-stu-id="09814-190">`dotnet-apphost-pack-[major].[minor]` - dependency</span></span>
  - <span data-ttu-id="09814-191">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-191">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-192">**Contiene:** (13)</span><span class="sxs-lookup"><span data-stu-id="09814-192">**Contains:** (13)</span></span>

- <span data-ttu-id="09814-193">`dotnet-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.</span><span class="sxs-lookup"><span data-stu-id="09814-193">`dotnet-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="09814-194">**Versión:** \<versión de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-194">**Version:** \<runtime version></span></span>
  - <span data-ttu-id="09814-195">**Contiene:** (12)</span><span class="sxs-lookup"><span data-stu-id="09814-195">**Contains:** (12)</span></span>

- <span data-ttu-id="09814-196">`aspnetcore-targeting-pack-[major].[minor]`: permite establecer como destino un runtime que no sea el más reciente.</span><span class="sxs-lookup"><span data-stu-id="09814-196">`aspnetcore-targeting-pack-[major].[minor]` - Allows targeting a non-latest runtime</span></span>
  - <span data-ttu-id="09814-197">**Versión:** \<versión aspnetcore de runtime></span><span class="sxs-lookup"><span data-stu-id="09814-197">**Version:** \<aspnetcore runtime version></span></span>
  - <span data-ttu-id="09814-198">**Contiene:** (11)</span><span class="sxs-lookup"><span data-stu-id="09814-198">**Contains:** (11)</span></span>

- <span data-ttu-id="09814-199">`netstandard-targeting-pack-[major].[minor]`: permite establecer como destino una versión de netstandard.</span><span class="sxs-lookup"><span data-stu-id="09814-199">`netstandard-targeting-pack-[major].[minor]` - Allows targeting a netstandard version</span></span>
  - <span data-ttu-id="09814-200">**Versión:** \<versión de sdk></span><span class="sxs-lookup"><span data-stu-id="09814-200">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="09814-201">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="09814-201">**Contains:** (15)</span></span>

- `dotnet-templates-[major].[minor]`
  - <span data-ttu-id="09814-202">**Versión:** \<versión de sdk></span><span class="sxs-lookup"><span data-stu-id="09814-202">**Version:** \<sdk version></span></span>
  - <span data-ttu-id="09814-203">**Contiene:** (15)</span><span class="sxs-lookup"><span data-stu-id="09814-203">**Contains:** (15)</span></span>

<span data-ttu-id="09814-204">`dotnet-runtime-deps-[major].[minor]` requiere el conocimiento de las _dependencias concretas de distribución_.</span><span class="sxs-lookup"><span data-stu-id="09814-204">The `dotnet-runtime-deps-[major].[minor]` requires understanding the _distro specific dependencies_.</span></span> <span data-ttu-id="09814-205">Dado que el sistema de compilación de distribución puede derivar esto de forma automática, el paquete es opcional, en cuyo caso estas dependencias se agregan directamente al paquete `dotnet-runtime-[major].[minor]`.</span><span class="sxs-lookup"><span data-stu-id="09814-205">Because the distro build system may be able to derive this automatically, the package is optional, in which case these dependencies are added directly to the `dotnet-runtime-[major].[minor]` package.</span></span>

<span data-ttu-id="09814-206">Cuando el contenido del paquete se encuentra en una carpeta con versión, el nombre del paquete `[major].[minor]` coincide con el nombre de la carpeta con versión.</span><span class="sxs-lookup"><span data-stu-id="09814-206">When package content is under a versioned folder, the package name `[major].[minor]` match the versioned folder name.</span></span> <span data-ttu-id="09814-207">En todos los paquetes, excepto en `netstandard-targeting-pack-[major].[minor]`, esto también coincide con la versión de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="09814-207">For all packages, except the `netstandard-targeting-pack-[major].[minor]`, this also matches with the .NET Core version.</span></span>

<span data-ttu-id="09814-208">Las dependencias entre paquetes deben usar un requisito de versión _igual o mayor que_.</span><span class="sxs-lookup"><span data-stu-id="09814-208">Dependencies between packages should use a _equal or greater than_ version requirement.</span></span> <span data-ttu-id="09814-209">Por ejemplo, `dotnet-sdk-2.2:2.2.401` requiere `aspnetcore-runtime-2.2 >= 2.2.6`.</span><span class="sxs-lookup"><span data-stu-id="09814-209">For example, `dotnet-sdk-2.2:2.2.401` requires `aspnetcore-runtime-2.2 >= 2.2.6`.</span></span> <span data-ttu-id="09814-210">Esto hace posible que el usuario actualice su instalación mediante un paquete raíz (por ejemplo, `dnf update dotnet-sdk-2.2`).</span><span class="sxs-lookup"><span data-stu-id="09814-210">This makes it possible for the user to upgrade their installation via a root package (e.g. `dnf update dotnet-sdk-2.2`).</span></span>

<span data-ttu-id="09814-211">La mayoría de las distribuciones requieren que todos los artefactos se compilen desde el origen.</span><span class="sxs-lookup"><span data-stu-id="09814-211">Most distributions require all artifacts to be built from source.</span></span> <span data-ttu-id="09814-212">Esto tiene algún impacto en los paquetes:</span><span class="sxs-lookup"><span data-stu-id="09814-212">This has some impact on the packages:</span></span>

- <span data-ttu-id="09814-213">Las bibliotecas de terceros de `shared/Microsoft.AspNetCore.All` no se pueden compilar fácilmente desde el origen.</span><span class="sxs-lookup"><span data-stu-id="09814-213">The third-party libraries under `shared/Microsoft.AspNetCore.All` can't be easily built from source.</span></span> <span data-ttu-id="09814-214">Por tanto, se omite esa carpeta en el paquete `aspnetcore-runtime`.</span><span class="sxs-lookup"><span data-stu-id="09814-214">So that folder is omitted from the `aspnetcore-runtime` package.</span></span>

- <span data-ttu-id="09814-215">La carpeta `NuGetFallbackFolder` se rellena con artefactos binarios desde `nuget.org`.</span><span class="sxs-lookup"><span data-stu-id="09814-215">The `NuGetFallbackFolder` is populated using binary artifacts from `nuget.org`.</span></span> <span data-ttu-id="09814-216">Debe permanecer vacía.</span><span class="sxs-lookup"><span data-stu-id="09814-216">It should remain empty.</span></span>

<span data-ttu-id="09814-217">Es posible que varios paquetes `dotnet-sdk` proporcionen los mismos archivos para la carpeta `NuGetFallbackFolder`.</span><span class="sxs-lookup"><span data-stu-id="09814-217">Multiple `dotnet-sdk` packages may provide the same files for the `NuGetFallbackFolder`.</span></span> <span data-ttu-id="09814-218">Para evitar problemas con el administrador de paquetes, estos archivos deben ser idénticos (suma de comprobación, fecha de modificación, etc.).</span><span class="sxs-lookup"><span data-stu-id="09814-218">To avoid issues with the package manager, these files should be identical (checksum, modification date, and so on).</span></span>

## <a name="building-packages"></a><span data-ttu-id="09814-219">Compilar paquetes</span><span class="sxs-lookup"><span data-stu-id="09814-219">Building packages</span></span>

<span data-ttu-id="09814-220">El repositorio [dotnet/source-build](https://github.com/dotnet/source-build) proporciona instrucciones sobre cómo crear un paquete tarball de origen del SDK de .NET Core y todos sus componentes.</span><span class="sxs-lookup"><span data-stu-id="09814-220">The [dotnet/source-build](https://github.com/dotnet/source-build) repository provides instructions on how to build a source tarball of the .NET Core SDK and all its components.</span></span> <span data-ttu-id="09814-221">La salida del repositorio de compilación de código fuente coincide con el diseño que se describe en la primera sección de este artículo.</span><span class="sxs-lookup"><span data-stu-id="09814-221">The output of the source-build repository matches the layout described in the first section of this article.</span></span>
