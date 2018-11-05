---
title: NuGet y bibliotecas de .NET
description: Procedimientos recomendados para el empaquetado con NuGet para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: 479d1786c232ef1f843877169954e847453681c9
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50185633"
---
# <a name="nuget"></a><span data-ttu-id="14752-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="14752-103">NuGet</span></span>

<span data-ttu-id="14752-104">NuGet es un administrador de paquetes para el ecosistema de. NET y es la principal forma que tienen los desarrolladores para detectar y adquirir bibliotecas de código abierto de .NET.</span><span class="sxs-lookup"><span data-stu-id="14752-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="14752-105">[NuGet.org](https://www.nuget.org/), un servicio gratuito proporcionado por Microsoft para hospedar paquetes NuGet, es el host principal para los paquetes NuGet públicos, pero usted puede publicar en los servicios de NuGet personalizados, como [MyGet](https://www.myget.org/) y [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="14752-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="14752-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="14752-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="14752-107">Creación de un paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="14752-107">Create a NuGet package</span></span>

<span data-ttu-id="14752-108">Un paquete NuGet (`*.nupkg`) es un archivo ZIP que contiene los ensamblados de .NET y los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="14752-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="14752-109">Hay dos formas principales de crear un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="14752-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="14752-110">Es la forma más reciente y recomendada es crear un paquete a partir de un proyecto de estilo SDK (archivo de proyecto cuyo contenido empieza con `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="14752-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="14752-111">Los ensamblados y objetivos se agregan automáticamente al paquete y los metadatos restantes se agregan al archivo de MSBuild, como el nombre del paquete y el número de versión.</span><span class="sxs-lookup"><span data-stu-id="14752-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="14752-112">La compilación con la el comando [`dotnet pack`](../../core/tools/dotnet-pack.md) genera un archivo `*.nupkg` en lugar de ensamblados.</span><span class="sxs-lookup"><span data-stu-id="14752-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
    <AssemblyName>Contoso.Api</AssemblyName>
    <PackageVersion>1.1.0</PackageVersion>
    <Authors>John Doe</Authors>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="14752-113">La forma anterior de crear un paquete NuGet es con un archivo `*.nuspec` y la herramienta de línea de comandos `nuget.exe`.</span><span class="sxs-lookup"><span data-stu-id="14752-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="14752-114">Un archivo nuspec ofrece un excelente control pero debe especificar meticulosamente qué ensamblados y destinos se van a incluir en el paquete NuGet final.</span><span class="sxs-lookup"><span data-stu-id="14752-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="14752-115">Es fácil cometer un error o que alguien se olvide de actualizar nuspec al realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="14752-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="14752-116">La ventaja de nuspec es que se puede usar para crear paquetes NuGet para marcos que aún no admiten un archivo de proyecto de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="14752-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="14752-117">**✔️ ES RECOMENDABLE** usar un archivo de proyecto de estilo SDK para crear el paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="14752-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="14752-118">**✔️ ES RECOMENDABLE** configurar SourceLink para agregar metadatos de control de código fuente a los ensamblados y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="14752-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="14752-119">Dependencias de paquetes</span><span class="sxs-lookup"><span data-stu-id="14752-119">Package dependencies</span></span>

<span data-ttu-id="14752-120">Las dependencias de paquetes NuGet se tratan detalladamente en el artículo [Dependences](./dependencies.md) (Dependencias).</span><span class="sxs-lookup"><span data-stu-id="14752-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="14752-121">Metadatos importantes del paquete NuGet</span><span class="sxs-lookup"><span data-stu-id="14752-121">Important NuGet package metadata</span></span>

<span data-ttu-id="14752-122">Un paquete NuGet admite numerosas [propiedades de metadatos](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="14752-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="14752-123">La tabla siguiente contiene los metadatos principales que deben proporcionar todos los proyectos de código abierto:</span><span class="sxs-lookup"><span data-stu-id="14752-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="14752-124">Nombre de la propiedad de MSBuild</span><span class="sxs-lookup"><span data-stu-id="14752-124">MSBuild Property name</span></span>              | <span data-ttu-id="14752-125">Nombre de nuspec</span><span class="sxs-lookup"><span data-stu-id="14752-125">Nuspec name</span></span>              | <span data-ttu-id="14752-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="14752-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="14752-127">Identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="14752-127">The package identifier.</span></span> <span data-ttu-id="14752-128">Se puede reservar un prefijo del identificador si cumple los [criterios](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="14752-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="14752-129">Versión del paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="14752-129">NuGet package version.</span></span> <span data-ttu-id="14752-130">Para información, vea [NuGet package version](./versioning.md#nuget-package-version) (Versión del paquete NuGet).</span><span class="sxs-lookup"><span data-stu-id="14752-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="14752-131">Título sencillo del paquete.</span><span class="sxs-lookup"><span data-stu-id="14752-131">A human-friendly title of the package.</span></span> <span data-ttu-id="14752-132">El valor predeterminado es `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="14752-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="14752-133">Una descripción larga del paquete que se muestra en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="14752-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="14752-134">Una lista separada por comas de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org.</span><span class="sxs-lookup"><span data-stu-id="14752-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="14752-135">Una lista delimitada por espacios de etiquetas y palabras clave que describen el paquete.</span><span class="sxs-lookup"><span data-stu-id="14752-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="14752-136">Las etiquetas se usan al buscar paquetes.</span><span class="sxs-lookup"><span data-stu-id="14752-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="14752-137">Una dirección URL para una imagen que se va a usar como icono para el paquete.</span><span class="sxs-lookup"><span data-stu-id="14752-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="14752-138">La dirección URL debe ser HTTPS y la imagen debe ser de 64x64 y tener un fondo transparente.</span><span class="sxs-lookup"><span data-stu-id="14752-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="14752-139">Una dirección URL para la página principal del proyecto o el repositorio de origen.</span><span class="sxs-lookup"><span data-stu-id="14752-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="14752-140">Una dirección URL a la licencia del proyecto.</span><span class="sxs-lookup"><span data-stu-id="14752-140">A URL to the project license.</span></span> <span data-ttu-id="14752-141">Puede ser la dirección URL al archivo `LICENSE` en el control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="14752-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="14752-142">**✔️ ES RECOMENDABLE** elegir un nombre de paquete NuGet con un prefijo que cumpla los [criterios](/nuget/reference/id-prefix-reservation) de la reserva de prefijo de NuGet.</span><span class="sxs-lookup"><span data-stu-id="14752-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="14752-143">**✔️ ES RECOMENDABLE** usar el archivo `LICENSE` en el control de código fuente como `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="14752-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="14752-144">Por ejemplo, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="14752-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="14752-145">Un proyecto sin una licencia se establece en [copyright exclusivo](https://choosealicense.com/no-permission/) de forma predeterminada, lo que impide que otras personas lo usen.</span><span class="sxs-lookup"><span data-stu-id="14752-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="14752-146">**✔️ DEBE** utilizar una href HTTPS en el icono de paquete.</span><span class="sxs-lookup"><span data-stu-id="14752-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="14752-147">Los sitios como NuGet.org se ejecutan con HTTPS habilitado y la representación de una imagen que no sea HTTPS creará una advertencia de contenido mixto.</span><span class="sxs-lookup"><span data-stu-id="14752-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="14752-148">**✔️ DEBE** utilizar una imagen de icono de paquete de 64x64 y que tenga un fondo transparente para obtener mejores resultados de visualización.</span><span class="sxs-lookup"><span data-stu-id="14752-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="14752-149">Paquetes de versión preliminar</span><span class="sxs-lookup"><span data-stu-id="14752-149">Pre-release packages</span></span>

<span data-ttu-id="14752-150">Los paquetes NuGet con un sufijo de versión se consideran de [versión preliminar](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="14752-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="14752-151">De forma predeterminada, la interfaz de usuario del administrador de paquetes de NuGet muestra versiones estables a menos que un usuario opte por los paquetes de versión preliminar, lo que hace que dichos paquetes resulten ideales para las pruebas limitadas de usuario.</span><span class="sxs-lookup"><span data-stu-id="14752-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="14752-152">Un paquete estable no puede depender de un paquete de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="14752-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="14752-153">Debe crear su propia versión preliminar de paquete o depender de una versión estable anterior.</span><span class="sxs-lookup"><span data-stu-id="14752-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="14752-154">![Dependencia de paquete de versión preliminar NuGet](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span><span class="sxs-lookup"><span data-stu-id="14752-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="14752-155">**✔️ DEBE** publicar un paquete de versión preliminar cuando pruebe, obtenga una vista previa o experimente.</span><span class="sxs-lookup"><span data-stu-id="14752-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="14752-156">**✔️ DEBE** publicar un paquete estable cuando esté listo, de forma que otros paquetes estables puedan hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="14752-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="14752-157">Paquetes de símbolos</span><span class="sxs-lookup"><span data-stu-id="14752-157">Symbol packages</span></span>

<span data-ttu-id="14752-158">El compilador de .NET genera los archivos de símbolos (`*.pdb`) junto con los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="14752-158">Symbol files (`*.pdb`) are produced by the .NET compiler alongside assemblies.</span></span> <span data-ttu-id="14752-159">Los archivos de símbolos asignan las ubicaciones de ejecución al código fuente original, por lo que puede recorrer dicho código a medida que se ejecuta usando un depurador.</span><span class="sxs-lookup"><span data-stu-id="14752-159">Symbol files map execution locations to the original source code so you can step through source code as it is running using a debugger.</span></span> <span data-ttu-id="14752-160">NuGet admite la [generación de un paquete de símbolos independiente](/nuget/create-packages/symbol-packages) que contiene archivos de símbolos junto con el paquete principal que contiene ensamblados .NET.</span><span class="sxs-lookup"><span data-stu-id="14752-160">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing symbol files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="14752-161">La idea de los paquetes de símbolos es que están hospedados en un servidor de símbolos y solo se descargan mediante una herramienta como Visual Studio a petición.</span><span class="sxs-lookup"><span data-stu-id="14752-161">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="14752-162">Actualmente el host público principal para símbolos ([SymbolSource](http://www.symbolsource.org/)) no es compatible con los nuevos [archivos de símbolos portátiles](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) creados por los proyectos estilo de SDK, y los paquetes de símbolos no son útiles.</span><span class="sxs-lookup"><span data-stu-id="14752-162">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the new [portable symbol files](https://github.com/dotnet/core/blob/master/Documentation/diagnostics/portable_pdb.md) (`*.pdb`) created by SDK-style projects, and symbol packages aren't useful.</span></span> <span data-ttu-id="14752-163">Hasta que haya un host recomendado para los paquetes de símbolos, los archivos de símbolos se pueden incrustar en el paquete NuGet principal.</span><span class="sxs-lookup"><span data-stu-id="14752-163">Until there is a recommended host for symbol packages, symbol files can be embedded in the main NuGet package.</span></span> <span data-ttu-id="14752-164">Si va a crear su paquete NuGet mediante un proyecto de estilo SDK, puede incrustar archivos de símbolos estableciendo la propiedad `AllowedOutputExtensionsInPackageBuildOutputFolder`:</span><span class="sxs-lookup"><span data-stu-id="14752-164">If you are building your NuGet package using an SDK-style project you can embed symbol files by setting the `AllowedOutputExtensionsInPackageBuildOutputFolder` property:</span></span> 

```xml
<Project Sdk="Microsoft.NET.Sdk">
 <PropertyGroup>
    <!-- Include symbol files (*.pdb) in the built .nupkg -->
    <AllowedOutputExtensionsInPackageBuildOutputFolder>$(AllowedOutputExtensionsInPackageBuildOutputFolder);.pdb</AllowedOutputExtensionsInPackageBuildOutputFolder>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="14752-165">**✔️ ES RECOMENDABLE** insertar los archivos de símbolos en el paquete NuGet principal.</span><span class="sxs-lookup"><span data-stu-id="14752-165">**✔️ CONSIDER** embedding symbol files in the main NuGet package.</span></span>

<span data-ttu-id="14752-166">**❌ EVITE** la creación de un paquete de símbolos que contenga archivos de símbolos.</span><span class="sxs-lookup"><span data-stu-id="14752-166">**❌ AVOID** creating a symbols package containing symbol files.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="14752-167">[Anterior](./strong-naming.md)
[Siguiente](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="14752-167">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
