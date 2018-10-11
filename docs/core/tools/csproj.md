---
title: Adiciones al formato csproj para .NET Core
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.openlocfilehash: 1fd264da2863fbeb88900be0f6fe000acac08a09
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47216921"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="47764-103">Adiciones al formato csproj para .NET Core</span><span class="sxs-lookup"><span data-stu-id="47764-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="47764-104">En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="47764-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="47764-105">Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="47764-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="47764-106">Referencias implícitas del paquete</span><span class="sxs-lookup"><span data-stu-id="47764-106">Implicit package references</span></span>
<span data-ttu-id="47764-107">Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="47764-108">`<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.</span><span class="sxs-lookup"><span data-stu-id="47764-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a><span data-ttu-id="47764-109">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="47764-109">Recommendations</span></span>
<span data-ttu-id="47764-110">Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library`, estos son los procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="47764-110">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="47764-111">Si el destino es .NET Core o .NET Standard, nunca incluya una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library` mediante un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-111">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="47764-112">Si necesita una versión concreta del runtime cuando el destino es .NET Core, debe usar la propiedad `<RuntimeFrameworkVersion>` del proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="47764-112">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="47764-113">Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="47764-113">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="47764-114">Si necesita una versión concreta del metapaquete `NetStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="47764-114">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="47764-115">No agregue referencias a los metapaquetes `Microsoft.NETCore.App` y `NetStandard.Library` ni las actualice explícitamente en proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="47764-115">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="47764-116">Si se necesita alguna versión de `NetStandard.Library` al usar un paquete NuGet basado en .NET Standard, NuGet instala automáticamente esa versión.</span><span class="sxs-lookup"><span data-stu-id="47764-116">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="47764-117">Inclusiones de compilación predeterminadas en proyectos .NET Core</span><span class="sxs-lookup"><span data-stu-id="47764-117">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="47764-118">Con el cambio al formato *csproj* en las últimas versiones del SDK, hemos trasladado las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos incrustados a los archivos de propiedades del SDK.</span><span class="sxs-lookup"><span data-stu-id="47764-118">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="47764-119">Esto implica que ya no tiene que especificar dichos elementos en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-119">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="47764-120">El principal motivo de este cambio consiste en reducir el desorden en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-120">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="47764-121">Los valores predeterminados presentes en el SDK deberían abarcar los casos de uso más habituales, por lo que no resulta necesario repetirlos en todos los proyectos que cree.</span><span class="sxs-lookup"><span data-stu-id="47764-121">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="47764-122">Esto da lugar a archivos de proyecto más pequeños que resultan mucho más fáciles de entender, así como de editar manualmente si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="47764-122">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="47764-123">En la siguiente tabla se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK:</span><span class="sxs-lookup"><span data-stu-id="47764-123">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="47764-124">Elemento</span><span class="sxs-lookup"><span data-stu-id="47764-124">Element</span></span>           | <span data-ttu-id="47764-125">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="47764-125">Include glob</span></span>                              | <span data-ttu-id="47764-126">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="47764-126">Exclude glob</span></span>                                                  | <span data-ttu-id="47764-127">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="47764-127">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="47764-128">Compile</span><span class="sxs-lookup"><span data-stu-id="47764-128">Compile</span></span>           | <span data-ttu-id="47764-129">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="47764-129">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="47764-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47764-130">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="47764-131">N/D</span><span class="sxs-lookup"><span data-stu-id="47764-131">N/A</span></span>                        |
| <span data-ttu-id="47764-132">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="47764-132">EmbeddedResource</span></span>  | <span data-ttu-id="47764-133">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="47764-133">\*\*/\*.resx</span></span>                              | <span data-ttu-id="47764-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47764-134">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="47764-135">N/D</span><span class="sxs-lookup"><span data-stu-id="47764-135">N/A</span></span>                        |
| <span data-ttu-id="47764-136">Ninguna</span><span class="sxs-lookup"><span data-stu-id="47764-136">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="47764-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="47764-137">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="47764-138">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="47764-138">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="47764-139">Si tiene globs en el proyecto e intenta crearlo usando el SDK más reciente, le aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="47764-139">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="47764-140">Se han incluido elementos de compilación duplicados.</span><span class="sxs-lookup"><span data-stu-id="47764-140">Duplicate Compile items were included.</span></span> <span data-ttu-id="47764-141">El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="47764-141">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="47764-142">Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-142">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="47764-143">Para evitar este error, puede quitar los elementos `Compile` explícitos que coinciden con los que aparecen en la tabla anterior o establecer la propiedad `<EnableDefaultCompileItems>` en `false` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="47764-143">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="47764-144">Al establecer esta propiedad en `false`, se invalidará la inclusión implícita y el comportamiento se revertirá a los SDK anteriores en los que tenía que especificar los globs predeterminados en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-144">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="47764-145">Este cambio no modifica los mecanismos principales de otras inclusiones.</span><span class="sxs-lookup"><span data-stu-id="47764-145">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="47764-146">En cambio, si quiere especificar, por ejemplo, que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos con los que está familiarizado en *csproj* (por ejemplo, el elemento `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="47764-146">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="47764-147">`<EnableDefaultCompileItems>` solo deshabilita globs `Compile`, pero no afecta a otros globs, como el glob `None` implícito, que también se aplica a elementos \*.cs.</span><span class="sxs-lookup"><span data-stu-id="47764-147">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="47764-148">Por eso, el **Explorador de soluciones** sigue mostrando elementos \*.cs como parte del proyecto, incluso como elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="47764-148">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="47764-149">Del mismo modo, puede usar `<EnableDefaultNoneItems>` para deshabilitar el glob `None` implícito.</span><span class="sxs-lookup"><span data-stu-id="47764-149">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="47764-150">Para deshabilitar **todos los globs implícitos**, puede establecer la propiedad `<EnableDefaultItems>` en `false` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="47764-150">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a><span data-ttu-id="47764-151">Recomendación</span><span class="sxs-lookup"><span data-stu-id="47764-151">Recommendation</span></span>
<span data-ttu-id="47764-152">Con csproj, se recomienda quitar los globs predeterminados del proyecto y agregar solo rutas de archivos con globs para aquellos artefactos que su aplicación o biblioteca necesita para varios escenarios (por ejemplo, tiempo de ejecución y empaquetado NuGet).</span><span class="sxs-lookup"><span data-stu-id="47764-152">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="47764-153">Visualización del proyecto completo tal como MSBuild lo ve</span><span class="sxs-lookup"><span data-stu-id="47764-153">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="47764-154">Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos.</span><span class="sxs-lookup"><span data-stu-id="47764-154">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="47764-155">Preprocese el proyecto con [el conmutador `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:</span><span class="sxs-lookup"><span data-stu-id="47764-155">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="47764-156">Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="47764-156">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="47764-157">Adiciones</span><span class="sxs-lookup"><span data-stu-id="47764-157">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="47764-158">Atributo Sdk</span><span class="sxs-lookup"><span data-stu-id="47764-158">Sdk attribute</span></span> 
<span data-ttu-id="47764-159">El elemento `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="47764-159">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="47764-160">`Sdk` especifica qué SDK usará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-160">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="47764-161">El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](/visualstudio/msbuild/msbuild-tasks) y [destinos](/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="47764-161">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="47764-162">Se incluyen dos SDK principales con las herramientas de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="47764-162">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="47764-163">El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="47764-163">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="47764-164">El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="47764-164">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="47764-165">Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código.</span><span class="sxs-lookup"><span data-stu-id="47764-165">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="47764-166">PackageReference</span><span class="sxs-lookup"><span data-stu-id="47764-166">PackageReference</span></span>
<span data-ttu-id="47764-167">Elemento que especifica una dependencia de NuGet en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-167">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="47764-168">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-168">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="47764-169">Versión</span><span class="sxs-lookup"><span data-stu-id="47764-169">Version</span></span>
<span data-ttu-id="47764-170">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="47764-170">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="47764-171">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="47764-171">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="47764-172">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="47764-172">The default behavior is an exact version match.</span></span> <span data-ttu-id="47764-173">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-173">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="47764-174">IncludeAssets, ExcludeAssets y PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="47764-174">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="47764-175">El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="47764-175">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="47764-176">El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="47764-176">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="47764-177">El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="47764-177">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="47764-178">`PrivateAssets` es equivalente al elemento *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="47764-178">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="47764-179">Estos atributos pueden contener uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="47764-179">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="47764-180">`Compile`: el contenido de la carpeta lib está disponible para compilación.</span><span class="sxs-lookup"><span data-stu-id="47764-180">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="47764-181">`Runtime`: el contenido de la carpeta runtime está distribuido.</span><span class="sxs-lookup"><span data-stu-id="47764-181">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="47764-182">`ContentFiles`: se usa el contenido de la carpeta *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="47764-182">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="47764-183">`Build`: se usan los archivos props/targets de la carpeta de compilación.</span><span class="sxs-lookup"><span data-stu-id="47764-183">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="47764-184">`Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="47764-184">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="47764-185">`Analyzers`: se usan los analizadores.</span><span class="sxs-lookup"><span data-stu-id="47764-185">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="47764-186">Como alternativa, el atributo puede contener:</span><span class="sxs-lookup"><span data-stu-id="47764-186">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="47764-187">`None`: no se usa ninguno de los recursos.</span><span class="sxs-lookup"><span data-stu-id="47764-187">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="47764-188">`All`: se usan todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="47764-188">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="47764-189">DotnetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="47764-189">DotNetCliToolReference</span></span>
<span data-ttu-id="47764-190">El elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-190">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="47764-191">Es un sustituto del nodo `tools` de *project.json*.</span><span class="sxs-lookup"><span data-stu-id="47764-191">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="47764-192">Versión</span><span class="sxs-lookup"><span data-stu-id="47764-192">Version</span></span>
<span data-ttu-id="47764-193">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="47764-193">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="47764-194">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="47764-194">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="47764-195">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="47764-195">The default behavior is an exact version match.</span></span> <span data-ttu-id="47764-196">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-196">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="47764-197">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="47764-197">RuntimeIdentifiers</span></span>
<span data-ttu-id="47764-198">El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-198">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="47764-199">Los RID permiten publicar implementaciones autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="47764-199">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="47764-200">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="47764-200">RuntimeIdentifier</span></span>
<span data-ttu-id="47764-201">El elemento `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-201">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="47764-202">Los RID permiten publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="47764-202">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="47764-203">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="47764-203">PackageTargetFallback</span></span> 
<span data-ttu-id="47764-204">El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="47764-204">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="47764-205">Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="47764-205">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="47764-206">Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet.</span><span class="sxs-lookup"><span data-stu-id="47764-206">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="47764-207">En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto:</span><span class="sxs-lookup"><span data-stu-id="47764-207">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="47764-208">En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="47764-208">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="47764-209">Propiedades de metadatos de NuGet</span><span class="sxs-lookup"><span data-stu-id="47764-209">NuGet metadata properties</span></span>
<span data-ttu-id="47764-210">Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete de NuGet de archivos *project.json* a *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="47764-210">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="47764-211">Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="47764-211">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="47764-212">La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK.</span><span class="sxs-lookup"><span data-stu-id="47764-212">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="47764-213">IsPackable</span><span class="sxs-lookup"><span data-stu-id="47764-213">IsPackable</span></span>
<span data-ttu-id="47764-214">Un valor booleano que especifica si se puede empaquetar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-214">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="47764-215">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="47764-215">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="47764-216">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="47764-216">PackageVersion</span></span>
<span data-ttu-id="47764-217">Especifica la versión que tendrá el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="47764-217">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="47764-218">Acepta todos los formatos de la cadena de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="47764-218">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="47764-219">El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-219">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="47764-220">PackageId</span><span class="sxs-lookup"><span data-stu-id="47764-220">PackageId</span></span>
<span data-ttu-id="47764-221">Especifica el nombre para el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="47764-221">Specifies the name for the resulting package.</span></span> <span data-ttu-id="47764-222">Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-222">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="47764-223">Title</span><span class="sxs-lookup"><span data-stu-id="47764-223">Title</span></span>
<span data-ttu-id="47764-224">Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47764-224">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="47764-225">Si no se especifica, se usa el identificador del paquete en su lugar.</span><span class="sxs-lookup"><span data-stu-id="47764-225">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="47764-226">Authors</span><span class="sxs-lookup"><span data-stu-id="47764-226">Authors</span></span>
<span data-ttu-id="47764-227">Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="47764-227">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="47764-228">Description</span><span class="sxs-lookup"><span data-stu-id="47764-228">Description</span></span>
<span data-ttu-id="47764-229">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="47764-229">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="47764-230">Copyright</span><span class="sxs-lookup"><span data-stu-id="47764-230">Copyright</span></span>
<span data-ttu-id="47764-231">Detalles de copyright del paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-231">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="47764-232">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="47764-232">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="47764-233">Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo.</span><span class="sxs-lookup"><span data-stu-id="47764-233">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="47764-234">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="47764-234">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="47764-235">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="47764-235">PackageLicenseUrl</span></span>
<span data-ttu-id="47764-236">Una dirección URL a la licencia que se aplica al paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-236">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="47764-237">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="47764-237">PackageProjectUrl</span></span>
<span data-ttu-id="47764-238">Una dirección URL de la página principal del paquete, que a menudo se muestra en las visualizaciones de la interfaz de usuario, así como en nuget.org.</span><span class="sxs-lookup"><span data-stu-id="47764-238">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="47764-239">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="47764-239">PackageIconUrl</span></span>
<span data-ttu-id="47764-240">Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="47764-240">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="47764-241">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="47764-241">PackageReleaseNotes</span></span>
<span data-ttu-id="47764-242">Notas de la versión para el paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-242">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="47764-243">PackageTags</span><span class="sxs-lookup"><span data-stu-id="47764-243">PackageTags</span></span>
<span data-ttu-id="47764-244">Una lista de etiquetas delimitada por punto y coma que designa el paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-244">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="47764-245">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="47764-245">PackageOutputPath</span></span>
<span data-ttu-id="47764-246">Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado.</span><span class="sxs-lookup"><span data-stu-id="47764-246">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="47764-247">El valor predeterminado es `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="47764-247">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="47764-248">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="47764-248">IncludeSymbols</span></span>
<span data-ttu-id="47764-249">Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto.</span><span class="sxs-lookup"><span data-stu-id="47764-249">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="47764-250">Este paquete tendrá una extensión *.symbols.nupkg* y copiará los archivos PDB junto con el archivo DLL y otros archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="47764-250">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="47764-251">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="47764-251">IncludeSource</span></span>
<span data-ttu-id="47764-252">Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen.</span><span class="sxs-lookup"><span data-stu-id="47764-252">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="47764-253">El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="47764-253">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="47764-254">Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="47764-254">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="47764-255">IsTool</span><span class="sxs-lookup"><span data-stu-id="47764-255">IsTool</span></span>
<span data-ttu-id="47764-256">Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*.</span><span class="sxs-lookup"><span data-stu-id="47764-256">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="47764-257">Tenga en cuenta que esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="47764-257">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="47764-258">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="47764-258">RepositoryUrl</span></span>
<span data-ttu-id="47764-259">Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando.</span><span class="sxs-lookup"><span data-stu-id="47764-259">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="47764-260">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="47764-260">RepositoryType</span></span>
<span data-ttu-id="47764-261">Especifica el tipo del repositorio.</span><span class="sxs-lookup"><span data-stu-id="47764-261">Specifies the type of the repository.</span></span> <span data-ttu-id="47764-262">El valor predeterminado es “git”.</span><span class="sxs-lookup"><span data-stu-id="47764-262">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="47764-263">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="47764-263">NoPackageAnalysis</span></span>
<span data-ttu-id="47764-264">Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="47764-264">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="47764-265">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="47764-265">MinClientVersion</span></span>
<span data-ttu-id="47764-266">Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="47764-266">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="47764-267">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="47764-267">IncludeBuildOutput</span></span>
<span data-ttu-id="47764-268">Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.</span><span class="sxs-lookup"><span data-stu-id="47764-268">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="47764-269">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="47764-269">IncludeContentInPack</span></span>
<span data-ttu-id="47764-270">Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="47764-270">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="47764-271">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="47764-271">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="47764-272">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="47764-272">BuildOutputTargetFolder</span></span>
<span data-ttu-id="47764-273">Especifica la carpeta en la que se colocarán los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="47764-273">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="47764-274">Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.</span><span class="sxs-lookup"><span data-stu-id="47764-274">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="47764-275">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="47764-275">ContentTargetFolders</span></span>
<span data-ttu-id="47764-276">Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos.</span><span class="sxs-lookup"><span data-stu-id="47764-276">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="47764-277">El valor predeterminado es “content;contentFiles”.</span><span class="sxs-lookup"><span data-stu-id="47764-277">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="47764-278">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="47764-278">NuspecFile</span></span>
<span data-ttu-id="47764-279">Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="47764-279">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="47764-280">Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos.</span><span class="sxs-lookup"><span data-stu-id="47764-280">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="47764-281">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="47764-281">NuspecBasePath</span></span>
<span data-ttu-id="47764-282">Ruta de acceso base para el archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="47764-282">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="47764-283">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="47764-283">NuspecProperties</span></span>
<span data-ttu-id="47764-284">Lista separada por punto y coma de pares clave=valor.</span><span class="sxs-lookup"><span data-stu-id="47764-284">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="47764-285">Propiedades de AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="47764-285">AssemblyInfo properties</span></span>
<span data-ttu-id="47764-286">Los [atributos de ensamblado](../../framework/app-domains/set-assembly-attributes.md) que solían estar presentes en un archivo *AssemblyInfo* ahora se generan automáticamente a partir de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="47764-286">[Assembly attributes](../../framework/app-domains/set-assembly-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="47764-287">Propiedades por atributo</span><span class="sxs-lookup"><span data-stu-id="47764-287">Properties per attribute</span></span>

<span data-ttu-id="47764-288">Cada atributo tiene una propiedad que controla su contenido y otra para deshabilitar la generación, tal como se muestra en la tabla siguiente:</span><span class="sxs-lookup"><span data-stu-id="47764-288">Each attribute has a property that control its content and another to disable its generation as shown in the following table:</span></span>

| <span data-ttu-id="47764-289">Atributo</span><span class="sxs-lookup"><span data-stu-id="47764-289">Attribute</span></span>                                                      | <span data-ttu-id="47764-290">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="47764-290">Property</span></span>               | <span data-ttu-id="47764-291">Propiedad que se va a deshabilitar</span><span class="sxs-lookup"><span data-stu-id="47764-291">Property to disable</span></span>                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

<span data-ttu-id="47764-292">Notas:</span><span class="sxs-lookup"><span data-stu-id="47764-292">Notes:</span></span>

* <span data-ttu-id="47764-293">El comportamiento predeterminado de `AssemblyVersion` y `FileVersion` consiste en adoptar el valor de `$(Version)` sin sufijo.</span><span class="sxs-lookup"><span data-stu-id="47764-293">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="47764-294">Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="47764-294">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
* <span data-ttu-id="47764-295">El valor predeterminado de `InformationalVersion` es el de `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="47764-295">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
* <span data-ttu-id="47764-296">`InformationalVersion` tiene `$(SourceRevisionId)` anexado si la propiedad está presente.</span><span class="sxs-lookup"><span data-stu-id="47764-296">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="47764-297">Puede deshabilitarse mediante `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="47764-297">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
* <span data-ttu-id="47764-298">Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.</span><span class="sxs-lookup"><span data-stu-id="47764-298">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
* <span data-ttu-id="47764-299">`Configuration` se comparte con todos los procesos de compilación y se establece mediante el parámetro `--configuration` de los comandos `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="47764-299">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="47764-300">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="47764-300">GenerateAssemblyInfo</span></span> 
<span data-ttu-id="47764-301">Un valor booleano que habilita o deshabilita toda la generación de AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="47764-301">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="47764-302">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="47764-302">The default value is `true`.</span></span> 

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="47764-303">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="47764-303">GeneratedAssemblyInfoFile</span></span> 
<span data-ttu-id="47764-304">La ruta de acceso del archivo de información del ensamblado generado.</span><span class="sxs-lookup"><span data-stu-id="47764-304">The path of the generated assembly info file.</span></span> <span data-ttu-id="47764-305">De forma predeterminada, se trata de un archivo del directorio `$(IntermediateOutputPath)` (obj).</span><span class="sxs-lookup"><span data-stu-id="47764-305">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
