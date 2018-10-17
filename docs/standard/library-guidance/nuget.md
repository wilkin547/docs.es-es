---
title: Bibliotecas de NuGet y .NET
description: Prácticas recomendadas para el empaquetado con NuGet para bibliotecas de. NET.
author: jamesnk
ms.author: mairaw
ms.date: 10/02/2018
ms.openlocfilehash: d0ea462a7f52dd9a6b2f14be9ed5770160bf66b1
ms.sourcegitcommit: e42d09e5966dd9fd02847d3e7eeb4ec0877069f8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2018
ms.locfileid: "49374508"
---
# <a name="nuget"></a><span data-ttu-id="aaf20-103">NuGet</span><span class="sxs-lookup"><span data-stu-id="aaf20-103">NuGet</span></span>

<span data-ttu-id="aaf20-104">NuGet es un administrador de paquetes para el ecosistema de. NET y es los principales desarrolladores detectarán y adquieren bibliotecas de código abierto. NET.</span><span class="sxs-lookup"><span data-stu-id="aaf20-104">NuGet is a package manager for the .NET ecosystem and is the primary way developers discover and acquire .NET open-source libraries.</span></span> <span data-ttu-id="aaf20-105">[NuGet.org](https://www.nuget.org/), un servicio gratuito proporcionado por Microsoft para hospedar paquetes de NuGet, es el host principal para los paquetes de NuGet públicos, pero puede publicar en los servicios de NuGet personalizados como [MyGet](https://www.myget.org/) y [artefactos de Azure ](https://azure.microsoft.com/services/devops/artifacts/).</span><span class="sxs-lookup"><span data-stu-id="aaf20-105">[NuGet.org](https://www.nuget.org/), a free service provided by Microsoft for hosting NuGet packages, is the primary host for public NuGet packages, but you can publish to custom NuGet services like [MyGet](https://www.myget.org/) and [Azure Artifacts](https://azure.microsoft.com/services/devops/artifacts/).</span></span>

<span data-ttu-id="aaf20-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span><span class="sxs-lookup"><span data-stu-id="aaf20-106">![NuGet](./media/nuget/nuget-logo.png "NuGet")</span></span>

## <a name="create-a-nuget-package"></a><span data-ttu-id="aaf20-107">Crear un paquete de NuGet</span><span class="sxs-lookup"><span data-stu-id="aaf20-107">Create a NuGet package</span></span>

<span data-ttu-id="aaf20-108">Un paquete NuGet (`*.nupkg`) es un archivo zip que contiene los ensamblados de .NET y los metadatos asociados.</span><span class="sxs-lookup"><span data-stu-id="aaf20-108">A NuGet package (`*.nupkg`) is a zip file that contains .NET assemblies and associated metadata.</span></span>

<span data-ttu-id="aaf20-109">Hay dos formas principales para crear un paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="aaf20-109">There are two main ways to create a NuGet package.</span></span> <span data-ttu-id="aaf20-110">Es la forma recomendada y más reciente crear un paquete desde un proyecto de estilo SDK (cuyo contenido se inicia con el archivo de proyecto `<Project Sdk="Microsoft.NET.Sdk">`).</span><span class="sxs-lookup"><span data-stu-id="aaf20-110">The newer and recommended way is to create a package from a SDK-style project (project file whose content starts with `<Project Sdk="Microsoft.NET.Sdk">`).</span></span> <span data-ttu-id="aaf20-111">Objetivos y los ensamblados se agregan automáticamente al paquete y restante de los metadatos se agrega al archivo de MSBuild, como el número de nombre y la versión del paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-111">Assemblies and targets are automatically added to the package and remaining metadata is added to the MSBuild file, like package name and version number.</span></span> <span data-ttu-id="aaf20-112">Compilar con la [ `dotnet pack` ](../../core/tools/dotnet-pack.md) salidas de comandos un `*.nupkg` archivo en lugar de los ensamblados.</span><span class="sxs-lookup"><span data-stu-id="aaf20-112">Compiling with the [`dotnet pack`](../../core/tools/dotnet-pack.md) command outputs a `*.nupkg` file instead of assemblies.</span></span>

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

<span data-ttu-id="aaf20-113">Es la forma anterior de la creación de un paquete de NuGet con un `*.nuspec` archivo y el `nuget.exe` herramienta de línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="aaf20-113">The older way of creating a NuGet package is with a `*.nuspec` file and the `nuget.exe` command-line tool.</span></span> <span data-ttu-id="aaf20-114">Un archivo nuspec ofrece un excelente control pero debe especificar meticulosamente qué ensamblados y destinos para incluir en el último paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="aaf20-114">A nuspec file gives you great control but you must carefully specify what assemblies and targets to include in the final NuGet package.</span></span> <span data-ttu-id="aaf20-115">Es fácil cometer un error o para que alguien se olvide de actualizar el archivo nuspec al realizar cambios.</span><span class="sxs-lookup"><span data-stu-id="aaf20-115">It's easy to make a mistake or for someone to forget to update the nuspec when making changes.</span></span> <span data-ttu-id="aaf20-116">La ventaja de nuspec es que puede usar crear paquetes de NuGet para marcos de trabajo que aún no admiten un archivo de proyecto de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="aaf20-116">The advantage of a nuspec is you can use it create NuGet packages for frameworks that don't yet support an SDK-style project file.</span></span>

<span data-ttu-id="aaf20-117">**Considere la posibilidad de ✔️** mediante un archivo de proyecto de estilo del SDK para crear el paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="aaf20-117">**✔️ CONSIDER** using an SDK-style project file to create the NuGet package.</span></span>

<span data-ttu-id="aaf20-118">**Considere la posibilidad de ✔️** configurar SourceLink para agregar metadatos de control de origen a los ensamblados y paquetes de NuGet.</span><span class="sxs-lookup"><span data-stu-id="aaf20-118">**✔️ CONSIDER** setting up SourceLink to add source control metadata to your assemblies and NuGet package.</span></span>

## <a name="package-dependencies"></a><span data-ttu-id="aaf20-119">Dependencias de paquetes</span><span class="sxs-lookup"><span data-stu-id="aaf20-119">Package dependencies</span></span>

<span data-ttu-id="aaf20-120">Dependencias de paquetes de NuGet se tratan detalladamente en el [dependencias](./dependencies.md) artículo.</span><span class="sxs-lookup"><span data-stu-id="aaf20-120">NuGet package dependencies are covered in detail in the [Dependencies](./dependencies.md) article.</span></span>

## <a name="important-nuget-package-metadata"></a><span data-ttu-id="aaf20-121">Metadatos del paquete NuGet importantes</span><span class="sxs-lookup"><span data-stu-id="aaf20-121">Important NuGet package metadata</span></span>

<span data-ttu-id="aaf20-122">Un paquete NuGet es compatible con muchos [propiedades de metadatos](/nuget/reference/nuspec).</span><span class="sxs-lookup"><span data-stu-id="aaf20-122">A NuGet package supports many [metadata properties](/nuget/reference/nuspec).</span></span> <span data-ttu-id="aaf20-123">En la tabla siguiente contiene los metadatos básicos que deben proporcionar todos los proyectos de código abierto:</span><span class="sxs-lookup"><span data-stu-id="aaf20-123">The following table contains the core metadata that every open-source project should provide:</span></span>

| <span data-ttu-id="aaf20-124">Nombre de la propiedad de MSBuild</span><span class="sxs-lookup"><span data-stu-id="aaf20-124">MSBuild Property name</span></span>              | <span data-ttu-id="aaf20-125">Nombre de archivo NuSpec</span><span class="sxs-lookup"><span data-stu-id="aaf20-125">Nuspec name</span></span>              | <span data-ttu-id="aaf20-126">Descripción</span><span class="sxs-lookup"><span data-stu-id="aaf20-126">Description</span></span>  |
| ---------------------------------- | ------------------------ | ------------ |
| `PackageId`                        | `id`                       | <span data-ttu-id="aaf20-127">El identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-127">The package identifier.</span></span> <span data-ttu-id="aaf20-128">Se puede reservar un prefijo del identificador de si cumple la [criterios](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="aaf20-128">A prefix from the identifier can be reserved if it meets the [criteria](/nuget/reference/id-prefix-reservation).</span></span> |
| `PackageVersion`                   | `version`                  | <span data-ttu-id="aaf20-129">Versión del paquete de NuGet.</span><span class="sxs-lookup"><span data-stu-id="aaf20-129">NuGet package version.</span></span> <span data-ttu-id="aaf20-130">Para obtener más información, consulte [versión del paquete NuGet](./versioning.md#nuget-package-version).</span><span class="sxs-lookup"><span data-stu-id="aaf20-130">For more information, see [NuGet package version](./versioning.md#nuget-package-version).</span></span>             |
| `Title`                            | `title`                    | <span data-ttu-id="aaf20-131">Un título fácil de usar del paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-131">A human-friendly title of the package.</span></span> <span data-ttu-id="aaf20-132">El valor predeterminado es el `PackageId`.</span><span class="sxs-lookup"><span data-stu-id="aaf20-132">It defaults to the `PackageId`.</span></span>             |
| `Description`                      | `description`              | <span data-ttu-id="aaf20-133">Una descripción larga del paquete que se muestra en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="aaf20-133">A long description of the package displayed in UI.</span></span>             |
| `Authors`                          | `authors`                  | <span data-ttu-id="aaf20-134">Una lista separada por comas de los autores de paquetes que coinciden con los nombres de perfil en nuget.org.</span><span class="sxs-lookup"><span data-stu-id="aaf20-134">A comma-separated list of package authors, matching the profile names on nuget.org.</span></span>             |
| `PackageTags`                      | `tags`                     | <span data-ttu-id="aaf20-135">Una lista delimitada por espacios de las etiquetas y palabras clave que describen el paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-135">A space-delimited list of tags and keywords that describe the package.</span></span> <span data-ttu-id="aaf20-136">Las etiquetas se usan al buscar paquetes.</span><span class="sxs-lookup"><span data-stu-id="aaf20-136">Tags are used when searching for packages.</span></span>             |
| `PackageIconUrl`                   | `iconUrl`                  | <span data-ttu-id="aaf20-137">Una dirección URL para una imagen para usarla como icono para el paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-137">A URL for an image to use as the icon for the package.</span></span> <span data-ttu-id="aaf20-138">Dirección URL debe ser HTTPS y la imagen debe ser de 64 x 64 y tienen un fondo transparente.</span><span class="sxs-lookup"><span data-stu-id="aaf20-138">URL should be HTTPS and the image should be 64x64 and have a transparent background.</span></span>             |
| `PackageProjectUrl`                | `projectUrl`               | <span data-ttu-id="aaf20-139">Una dirección URL para el repositorio de origen o de la página principal de proyecto.</span><span class="sxs-lookup"><span data-stu-id="aaf20-139">A URL for the project homepage or source repository.</span></span>             |
| `PackageLicenseUrl`                | `licenseUrl`               | <span data-ttu-id="aaf20-140">Una dirección URL a la licencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="aaf20-140">A URL to the project license.</span></span> <span data-ttu-id="aaf20-141">Puede ser la dirección URL a la `LICENSE` archivo de control de código fuente.</span><span class="sxs-lookup"><span data-stu-id="aaf20-141">Can be the URL to the `LICENSE` file in source control.</span></span>             |

<span data-ttu-id="aaf20-142">**Considere la posibilidad de ✔️** elegir un nombre de paquete de NuGet con un prefijo que cumpla la reserva de prefijo de NuGet [criterios](/nuget/reference/id-prefix-reservation).</span><span class="sxs-lookup"><span data-stu-id="aaf20-142">**✔️ CONSIDER** choosing a NuGet package name with a prefix that meets NuGet's prefix reservation [criteria](/nuget/reference/id-prefix-reservation).</span></span>

<span data-ttu-id="aaf20-143">**✔️, considere la posibilidad de** utilizando el `LICENSE` archivo de control de código fuente como el `LicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="aaf20-143">**✔️ CONSIDER** using the `LICENSE` file in source control as the `LicenseUrl`.</span></span> <span data-ttu-id="aaf20-144">Por ejemplo, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span><span class="sxs-lookup"><span data-stu-id="aaf20-144">For example, [LICENSE.md](https://github.com/JamesNK/Newtonsoft.Json/blob/c4af75c8e91ca0d75aa6c335e8c106780c4f7712/LICENSE.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aaf20-145">Un proyecto sin el valor predeterminado es una licencia [copyright exclusivo](https://choosealicense.com/no-permission/), lo que sea imposible que otras personas.</span><span class="sxs-lookup"><span data-stu-id="aaf20-145">A project without a license defaults to [exclusive copyright](https://choosealicense.com/no-permission/), making it impossible for other people to use.</span></span>

<span data-ttu-id="aaf20-146">**HACER ✔️** utilizar un href HTTPS en el icono de paquete.</span><span class="sxs-lookup"><span data-stu-id="aaf20-146">**✔️ DO** use an HTTPS href to your package icon.</span></span>

> <span data-ttu-id="aaf20-147">Ejecutan sitios como NuGet.org con habilitadas para HTTPS y mostrar una imagen que no sean HTTPS, se creará una advertencia de contenido mixto.</span><span class="sxs-lookup"><span data-stu-id="aaf20-147">Sites like NuGet.org run with HTTPS enabled and displaying a non-HTTPS image will create a mixed content warning.</span></span>

<span data-ttu-id="aaf20-148">**HACER ✔️** usar una imagen de icono de paquete que es 64 x 64 y tiene un fondo transparente para ver mejor.</span><span class="sxs-lookup"><span data-stu-id="aaf20-148">**✔️ DO** use a package icon image that is 64x64 and has a transparent background for best viewing results.</span></span>

## <a name="pre-release-packages"></a><span data-ttu-id="aaf20-149">Paquetes de versión preliminar</span><span class="sxs-lookup"><span data-stu-id="aaf20-149">Pre-release packages</span></span>

<span data-ttu-id="aaf20-150">Paquetes de NuGet con un sufijo de versión se consideran [preliminares](/nuget/create-packages/prerelease-packages).</span><span class="sxs-lookup"><span data-stu-id="aaf20-150">NuGet packages with a version suffix are considered [pre-release](/nuget/create-packages/prerelease-packages).</span></span> <span data-ttu-id="aaf20-151">De forma predeterminada, el Administrador de paquetes NuGet de UI muestra versiones estables a menos que un usuario opta por participar en preliminares de los paquetes, por lo que los paquetes preliminares ideal para las pruebas de usuario limitada.</span><span class="sxs-lookup"><span data-stu-id="aaf20-151">By default, the NuGet Package Manager UI shows stable releases unless a user opts-in to pre-release packages, making pre-release packages ideal for limited user testing.</span></span>

```xml
<PackageVersion>1.0.1-beta1</PackageVersion>
```

> [!NOTE]
> <span data-ttu-id="aaf20-152">Un paquete estable no puede depender de un paquete de versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="aaf20-152">A stable package cannot depend on a pre-release package.</span></span> <span data-ttu-id="aaf20-153">Debe realizar su propio paquete de versión preliminar o dependen de una versión estable anterior.</span><span class="sxs-lookup"><span data-stu-id="aaf20-153">You must either make your own package pre-release or depend on an older stable version.</span></span>

<span data-ttu-id="aaf20-154">![Dependencia de paquetes de versión preliminar](./media/nuget/nuget-prerelease-package.png "dependencia de paquetes de versión preliminar")</span><span class="sxs-lookup"><span data-stu-id="aaf20-154">![NuGet pre-release package dependency](./media/nuget/nuget-prerelease-package.png "NuGet pre-release package dependency")</span></span>

<span data-ttu-id="aaf20-155">**HACER ✔️** publicar un paquete de versión preliminar para probar, obtener una vista previa o experimentar.</span><span class="sxs-lookup"><span data-stu-id="aaf20-155">**✔️ DO** publish a pre-release package when testing, previewing, or experimenting.</span></span>

<span data-ttu-id="aaf20-156">**HACER ✔️** publicar un paquete estable cuando su listos para otros paquetes estables pueden hacer referencia a él.</span><span class="sxs-lookup"><span data-stu-id="aaf20-156">**✔️ DO** publish a stable package when its ready so other stable packages can reference it.</span></span>

## <a name="symbol-packages"></a><span data-ttu-id="aaf20-157">Paquetes de símbolos</span><span class="sxs-lookup"><span data-stu-id="aaf20-157">Symbol packages</span></span>

<span data-ttu-id="aaf20-158">NuGet admite [generar un paquete de símbolos independiente](/nuget/create-packages/symbol-packages) que contiene los archivos PDB junto con el paquete principal que contiene los ensamblados de .NET de depuración.</span><span class="sxs-lookup"><span data-stu-id="aaf20-158">NuGet supports [generating a separate symbol package](/nuget/create-packages/symbol-packages) containing debug PDB files alongside the main package containing .NET assemblies.</span></span> <span data-ttu-id="aaf20-159">La idea de los paquetes de símbolos es que están hospedados en un servidor de símbolos y sólo se descargan mediante una herramienta como Visual Studio a petición.</span><span class="sxs-lookup"><span data-stu-id="aaf20-159">The idea of symbol packages is they're hosted on a symbol server and are only downloaded by a tool like Visual Studio on demand.</span></span>

<span data-ttu-id="aaf20-160">Actualmente el host público principal para símbolos - [SymbolSource](http://www.symbolsource.org/) -no es compatible con los archivos PDB portátiles creados por el estilo del SDK de proyectos y paquetes de símbolos no son útiles.</span><span class="sxs-lookup"><span data-stu-id="aaf20-160">Currently the main public host for symbols - [SymbolSource](http://www.symbolsource.org/) - doesn't support the portable PDBs created by SDK-style projects and symbol packages aren't useful.</span></span>

<span data-ttu-id="aaf20-161">**Considere la posibilidad de ✔️** incrustar los archivos PDB en el paquete NuGet principal.</span><span class="sxs-lookup"><span data-stu-id="aaf20-161">**✔️ CONSIDER** embedding PDBs in the main NuGet package.</span></span>

<span data-ttu-id="aaf20-162">**Evite ❌** creación de un paquete de símbolos que contiene los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="aaf20-162">**❌ AVOID** creating a symbols package containing PDBs.</span></span>

>[!div class="step-by-step"]
<span data-ttu-id="aaf20-163">[Anterior](./strong-naming.md)
[Siguiente](./dependencies.md)</span><span class="sxs-lookup"><span data-stu-id="aaf20-163">[Previous](./strong-naming.md)
[Next](./dependencies.md)</span></span>
