---
title: referencia de csproj
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
keywords: referencia, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 63c7a6f0aa3a926c7ae01ad6c434ecf296c81811
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="4792f-104">Adiciones al formato csproj para .NET Core</span><span class="sxs-lookup"><span data-stu-id="4792f-104">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="4792f-105">En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="4792f-105">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="4792f-106">Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="4792f-106">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="4792f-107">Referencias implícitas del paquete</span><span class="sxs-lookup"><span data-stu-id="4792f-107">Implicit package references</span></span>
<span data-ttu-id="4792f-108">Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-108">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="4792f-109">`<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.</span><span class="sxs-lookup"><span data-stu-id="4792f-109">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp1.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp1.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="4792f-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="4792f-110">Recommendations</span></span>
<span data-ttu-id="4792f-111">Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library`, estos son los procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="4792f-111">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="4792f-112">Nunca tenga una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library` a través de un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-112">Never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="4792f-113">Si necesita una versión específica del tiempo de ejecución, debe usar la propiedad `<RuntimeFrameworkVersion>` de su proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-113">If you need a specific version of the runtime, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="4792f-114">Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="4792f-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="4792f-115">Si necesita una versión específica del metapaquete `NetStandard.Library`, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="4792f-115">If you need a specific version of the `NetStandard.Library` metapackage, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span> 

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="4792f-116">Inclusiones de compilación predeterminadas en proyectos .NET Core</span><span class="sxs-lookup"><span data-stu-id="4792f-116">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="4792f-117">Con el cambio al formato *csproj* en las últimas versiones del SDK, hemos trasladado las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos incrustados a los archivos de propiedades del SDK.</span><span class="sxs-lookup"><span data-stu-id="4792f-117">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="4792f-118">Esto implica que ya no tiene que especificar dichos elementos en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-118">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="4792f-119">El principal motivo de este cambio consiste en reducir el desorden en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-119">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="4792f-120">Los valores predeterminados presentes en el SDK deberían abarcar los casos de uso más habituales, por lo que no resulta necesario repetirlos en todos los proyectos que cree.</span><span class="sxs-lookup"><span data-stu-id="4792f-120">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="4792f-121">Esto da lugar a archivos de proyecto más pequeños que resultan mucho más fáciles de entender, así como de editar manualmente si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="4792f-121">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="4792f-122">En la siguiente tabla se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK:</span><span class="sxs-lookup"><span data-stu-id="4792f-122">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="4792f-123">Elemento</span><span class="sxs-lookup"><span data-stu-id="4792f-123">Element</span></span>           | <span data-ttu-id="4792f-124">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="4792f-124">Include glob</span></span>                              | <span data-ttu-id="4792f-125">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="4792f-125">Exclude glob</span></span>                                                  | <span data-ttu-id="4792f-126">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="4792f-126">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="4792f-127">Compile</span><span class="sxs-lookup"><span data-stu-id="4792f-127">Compile</span></span>           | <span data-ttu-id="4792f-128">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="4792f-128">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="4792f-129">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="4792f-129">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="4792f-130">N/D</span><span class="sxs-lookup"><span data-stu-id="4792f-130">N/A</span></span>                        |
| <span data-ttu-id="4792f-131">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="4792f-131">EmbeddedResource</span></span>  | <span data-ttu-id="4792f-132">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="4792f-132">\*\*/\*.resx</span></span>                              | <span data-ttu-id="4792f-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="4792f-133">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="4792f-134">N/D</span><span class="sxs-lookup"><span data-stu-id="4792f-134">N/A</span></span>                        |
| <span data-ttu-id="4792f-135">Ninguna</span><span class="sxs-lookup"><span data-stu-id="4792f-135">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="4792f-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="4792f-136">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="4792f-137">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="4792f-137">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="4792f-138">Si tiene globs en el proyecto e intenta crearlo usando el SDK más reciente, le aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="4792f-138">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="4792f-139">Se han incluido elementos de compilación duplicados.</span><span class="sxs-lookup"><span data-stu-id="4792f-139">Duplicate Compile items were included.</span></span> <span data-ttu-id="4792f-140">El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="4792f-140">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="4792f-141">Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-141">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="4792f-142">Para evitar este error, puede quitar los elementos `Compile` explícitos que coinciden con los que aparecen en la tabla anterior o establecer la propiedad `<EnableDefaultCompileItems>` en `false` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="4792f-142">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="4792f-143">Al establecer esta propiedad en `false`, se invalidará la inclusión implícita y el comportamiento se revertirá a los SDK anteriores en los que tenía que especificar los globs predeterminados en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-143">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="4792f-144">Este cambio no modifica los mecanismos principales de otras inclusiones.</span><span class="sxs-lookup"><span data-stu-id="4792f-144">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="4792f-145">En cambio, si quiere especificar, por ejemplo, que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos con los que está familiarizado en *csproj* (por ejemplo, el elemento `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="4792f-145">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

### <a name="recommendation"></a><span data-ttu-id="4792f-146">Recomendación</span><span class="sxs-lookup"><span data-stu-id="4792f-146">Recommendation</span></span>
<span data-ttu-id="4792f-147">Con csproj, se recomienda quitar los globs predeterminados del proyecto y agregar solo rutas de archivos con globs para aquellos artefactos que su aplicación o biblioteca necesita para varios escenarios (por ejemplo, tiempo de ejecución y empaquetado NuGet).</span><span class="sxs-lookup"><span data-stu-id="4792f-147">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="4792f-148">Visualización del proyecto completo tal como MSBuild lo ve</span><span class="sxs-lookup"><span data-stu-id="4792f-148">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="4792f-149">Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos.</span><span class="sxs-lookup"><span data-stu-id="4792f-149">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="4792f-150">Preprocese el proyecto con [el conmutador `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:</span><span class="sxs-lookup"><span data-stu-id="4792f-150">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="4792f-151">Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="4792f-151">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="4792f-152">Adiciones</span><span class="sxs-lookup"><span data-stu-id="4792f-152">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="4792f-153">Atributo Sdk</span><span class="sxs-lookup"><span data-stu-id="4792f-153">Sdk attribute</span></span> 
<span data-ttu-id="4792f-154">El elemento `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="4792f-154">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="4792f-155">`Sdk` especifica qué SDK usará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-155">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="4792f-156">El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](/visualstudio/msbuild/msbuild-tasks) y [destinos](/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="4792f-156">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="4792f-157">Se incluyen dos SDK principales con las herramientas de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="4792f-157">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="4792f-158">El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="4792f-158">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="4792f-159">El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="4792f-159">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="4792f-160">Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código.</span><span class="sxs-lookup"><span data-stu-id="4792f-160">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="4792f-161">PackageReference</span><span class="sxs-lookup"><span data-stu-id="4792f-161">PackageReference</span></span>
<span data-ttu-id="4792f-162">Elemento que especifica una dependencia de NuGet en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-162">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="4792f-163">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-163">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="4792f-164">Versión</span><span class="sxs-lookup"><span data-stu-id="4792f-164">Version</span></span>
<span data-ttu-id="4792f-165">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="4792f-165">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="4792f-166">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="4792f-166">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="4792f-167">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="4792f-167">The default behavior is an exact version match.</span></span> <span data-ttu-id="4792f-168">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-168">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="4792f-169">IncludeAssets, ExcludeAssets y PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="4792f-169">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="4792f-170">El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="4792f-170">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="4792f-171">El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="4792f-171">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="4792f-172">El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="4792f-172">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="4792f-173">`PrivateAssets` es equivalente al elemento *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="4792f-173">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="4792f-174">Estos atributos pueden contener uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="4792f-174">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="4792f-175">`Compile`: el contenido de la carpeta lib está disponible para compilación.</span><span class="sxs-lookup"><span data-stu-id="4792f-175">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="4792f-176">`Runtime`: el contenido de la carpeta runtime está distribuido.</span><span class="sxs-lookup"><span data-stu-id="4792f-176">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="4792f-177">`ContentFiles`: se usa el contenido de la carpeta *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="4792f-177">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="4792f-178">`Build`: se usan los archivos props/targets de la carpeta de compilación.</span><span class="sxs-lookup"><span data-stu-id="4792f-178">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="4792f-179">`Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="4792f-179">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="4792f-180">`Analyzers`: se usan los analizadores.</span><span class="sxs-lookup"><span data-stu-id="4792f-180">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="4792f-181">Como alternativa, el atributo puede contener:</span><span class="sxs-lookup"><span data-stu-id="4792f-181">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="4792f-182">`None`: no se usa ninguno de los recursos.</span><span class="sxs-lookup"><span data-stu-id="4792f-182">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="4792f-183">`All`: se usan todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="4792f-183">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="4792f-184">DotnetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="4792f-184">DotNetCliToolReference</span></span>
<span data-ttu-id="4792f-185">El elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-185">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="4792f-186">Es un sustituto del nodo `tools` de *project.json*.</span><span class="sxs-lookup"><span data-stu-id="4792f-186">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="4792f-187">Versión</span><span class="sxs-lookup"><span data-stu-id="4792f-187">Version</span></span>
<span data-ttu-id="4792f-188">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="4792f-188">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="4792f-189">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="4792f-189">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="4792f-190">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="4792f-190">The default behavior is an exact version match.</span></span> <span data-ttu-id="4792f-191">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-191">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="4792f-192">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="4792f-192">RuntimeIdentifiers</span></span>
<span data-ttu-id="4792f-193">El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-193">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4792f-194">Los RID permiten publicar implementaciones autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="4792f-194">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="4792f-195">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="4792f-195">RuntimeIdentifier</span></span>
<span data-ttu-id="4792f-196">El elemento `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-196">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="4792f-197">Los RID permiten publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="4792f-197">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="4792f-198">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="4792f-198">PackageTargetFallback</span></span> 
<span data-ttu-id="4792f-199">El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="4792f-199">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="4792f-200">Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="4792f-200">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="4792f-201">Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet.</span><span class="sxs-lookup"><span data-stu-id="4792f-201">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="4792f-202">En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto:</span><span class="sxs-lookup"><span data-stu-id="4792f-202">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="4792f-203">En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp1.0`:</span><span class="sxs-lookup"><span data-stu-id="4792f-203">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="4792f-204">Propiedades de metadatos de NuGet</span><span class="sxs-lookup"><span data-stu-id="4792f-204">NuGet metadata properties</span></span>
<span data-ttu-id="4792f-205">Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete de NuGet de archivos *project.json* a *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="4792f-205">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="4792f-206">Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="4792f-206">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="4792f-207">La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK.</span><span class="sxs-lookup"><span data-stu-id="4792f-207">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="4792f-208">IsPackable</span><span class="sxs-lookup"><span data-stu-id="4792f-208">IsPackable</span></span>
<span data-ttu-id="4792f-209">Un valor booleano que especifica si se puede empaquetar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-209">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="4792f-210">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="4792f-210">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="4792f-211">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="4792f-211">PackageVersion</span></span>
<span data-ttu-id="4792f-212">Especifica la versión que tendrá el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="4792f-212">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="4792f-213">Acepta todos los formatos de la cadena de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="4792f-213">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="4792f-214">El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-214">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="4792f-215">PackageId</span><span class="sxs-lookup"><span data-stu-id="4792f-215">PackageId</span></span>
<span data-ttu-id="4792f-216">Especifica el nombre para el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="4792f-216">Specifies the name for the resulting package.</span></span> <span data-ttu-id="4792f-217">Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-217">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="4792f-218">Title</span><span class="sxs-lookup"><span data-stu-id="4792f-218">Title</span></span>
<span data-ttu-id="4792f-219">Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4792f-219">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="4792f-220">Si no se especifica, se usa el identificador del paquete en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4792f-220">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="4792f-221">Authors</span><span class="sxs-lookup"><span data-stu-id="4792f-221">Authors</span></span>
<span data-ttu-id="4792f-222">Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org.</span><span class="sxs-lookup"><span data-stu-id="4792f-222">A semicolon-separated list of packages authors, matching the profile names on nuget.org.</span></span> <span data-ttu-id="4792f-223">Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="4792f-223">These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="4792f-224">Description</span><span class="sxs-lookup"><span data-stu-id="4792f-224">Description</span></span>
<span data-ttu-id="4792f-225">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4792f-225">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="4792f-226">Copyright</span><span class="sxs-lookup"><span data-stu-id="4792f-226">Copyright</span></span>
<span data-ttu-id="4792f-227">Detalles de copyright del paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-227">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="4792f-228">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="4792f-228">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="4792f-229">Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo.</span><span class="sxs-lookup"><span data-stu-id="4792f-229">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="4792f-230">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="4792f-230">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="4792f-231">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="4792f-231">PackageLicenseUrl</span></span>
<span data-ttu-id="4792f-232">Una dirección URL a la licencia que se aplica al paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-232">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="4792f-233">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="4792f-233">PackageProjectUrl</span></span>
<span data-ttu-id="4792f-234">Una dirección URL de la página principal del paquete, que a menudo se muestra en las visualizaciones de la interfaz de usuario, así como en nuget.org.</span><span class="sxs-lookup"><span data-stu-id="4792f-234">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="4792f-235">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="4792f-235">PackageIconUrl</span></span>
<span data-ttu-id="4792f-236">Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="4792f-236">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="4792f-237">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="4792f-237">PackageReleaseNotes</span></span>
<span data-ttu-id="4792f-238">Notas de la versión para el paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-238">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="4792f-239">PackageTags</span><span class="sxs-lookup"><span data-stu-id="4792f-239">PackageTags</span></span>
<span data-ttu-id="4792f-240">Una lista de etiquetas delimitada por punto y coma que designa el paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-240">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="4792f-241">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="4792f-241">PackageOutputPath</span></span>
<span data-ttu-id="4792f-242">Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado.</span><span class="sxs-lookup"><span data-stu-id="4792f-242">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="4792f-243">El valor predeterminado es `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="4792f-243">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="4792f-244">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="4792f-244">IncludeSymbols</span></span>
<span data-ttu-id="4792f-245">Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto.</span><span class="sxs-lookup"><span data-stu-id="4792f-245">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="4792f-246">Este paquete tendrá una extensión *.symbols.nupkg* y copiará los archivos PDB junto con el archivo DLL y otros archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="4792f-246">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="4792f-247">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="4792f-247">IncludeSource</span></span>
<span data-ttu-id="4792f-248">Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen.</span><span class="sxs-lookup"><span data-stu-id="4792f-248">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="4792f-249">El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="4792f-249">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="4792f-250">Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="4792f-250">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="4792f-251">IsTool</span><span class="sxs-lookup"><span data-stu-id="4792f-251">IsTool</span></span>
<span data-ttu-id="4792f-252">Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*.</span><span class="sxs-lookup"><span data-stu-id="4792f-252">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="4792f-253">Tenga en cuenta que esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="4792f-253">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="4792f-254">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="4792f-254">RepositoryUrl</span></span>
<span data-ttu-id="4792f-255">Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando.</span><span class="sxs-lookup"><span data-stu-id="4792f-255">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="4792f-256">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="4792f-256">RepositoryType</span></span>
<span data-ttu-id="4792f-257">Especifica el tipo del repositorio.</span><span class="sxs-lookup"><span data-stu-id="4792f-257">Specifies the type of the repository.</span></span> <span data-ttu-id="4792f-258">El valor predeterminado es “git”.</span><span class="sxs-lookup"><span data-stu-id="4792f-258">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="4792f-259">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="4792f-259">NoPackageAnalysis</span></span>
<span data-ttu-id="4792f-260">Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="4792f-260">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="4792f-261">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="4792f-261">MinClientVersion</span></span>
<span data-ttu-id="4792f-262">Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="4792f-262">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="4792f-263">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="4792f-263">IncludeBuildOutput</span></span>
<span data-ttu-id="4792f-264">Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.</span><span class="sxs-lookup"><span data-stu-id="4792f-264">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="4792f-265">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="4792f-265">IncludeContentInPack</span></span>
<span data-ttu-id="4792f-266">Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="4792f-266">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="4792f-267">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="4792f-267">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="4792f-268">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="4792f-268">BuildOutputTargetFolder</span></span>
<span data-ttu-id="4792f-269">Especifica la carpeta en la que se colocarán los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="4792f-269">Specifies the folder where to place the output assemblies..</span></span> <span data-ttu-id="4792f-270">Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.</span><span class="sxs-lookup"><span data-stu-id="4792f-270">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="4792f-271">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="4792f-271">ContentTargetFolders</span></span>
<span data-ttu-id="4792f-272">Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos.</span><span class="sxs-lookup"><span data-stu-id="4792f-272">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="4792f-273">El valor predeterminado es “content;contentFiles”.</span><span class="sxs-lookup"><span data-stu-id="4792f-273">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="4792f-274">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="4792f-274">NuspecFile</span></span>
<span data-ttu-id="4792f-275">Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="4792f-275">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="4792f-276">Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos.</span><span class="sxs-lookup"><span data-stu-id="4792f-276">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="4792f-277">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="4792f-277">NuspecBasePath</span></span>
<span data-ttu-id="4792f-278">Ruta de acceso base para el archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="4792f-278">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="4792f-279">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="4792f-279">NuspecProperties</span></span>
<span data-ttu-id="4792f-280">Lista separada por punto y coma de pares clave=valor.</span><span class="sxs-lookup"><span data-stu-id="4792f-280">Semicolon separated list of key=value pairs.</span></span>

