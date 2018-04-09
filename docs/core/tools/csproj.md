---
title: Adiciones al formato csproj para .NET Core
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
keywords: referencia, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.workload:
- dotnetcore
ms.openlocfilehash: fdf91bdb24819c2d92b708e5937980ac2fb0d5fc
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="6eeae-104">Adiciones al formato csproj para .NET Core</span><span class="sxs-lookup"><span data-stu-id="6eeae-104">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="6eeae-105">En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="6eeae-105">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="6eeae-106">Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="6eeae-106">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>  

## <a name="implicit-package-references"></a><span data-ttu-id="6eeae-107">Referencias implícitas del paquete</span><span class="sxs-lookup"><span data-stu-id="6eeae-107">Implicit package references</span></span>
<span data-ttu-id="6eeae-108">Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-108">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="6eeae-109">`<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.</span><span class="sxs-lookup"><span data-stu-id="6eeae-109">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="6eeae-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="6eeae-110">Recommendations</span></span>
<span data-ttu-id="6eeae-111">Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library`, estos son los procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="6eeae-111">Since `Microsoft.NETCore.App` or `NetStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

* <span data-ttu-id="6eeae-112">Si el destino es .NET Core o .NET Standard, nunca incluya una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library` mediante un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NetStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
* <span data-ttu-id="6eeae-113">Si necesita una versión concreta del runtime cuando el destino es .NET Core, debe usar la propiedad `<RuntimeFrameworkVersion>` del proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
    * <span data-ttu-id="6eeae-114">Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="6eeae-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
* <span data-ttu-id="6eeae-115">Si necesita una versión concreta del metapaquete `NetStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="6eeae-115">If you need a specific version of the `NetStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
* <span data-ttu-id="6eeae-116">No agregue referencias a los metapaquetes `Microsoft.NETCore.App` y `NetStandard.Library` ni las actualice explícitamente en proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="6eeae-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NetStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="6eeae-117">Si se necesita alguna versión de `NetStandard.Library` al usar un paquete NuGet basado en .NET Standard, NuGet instala automáticamente esa versión.</span><span class="sxs-lookup"><span data-stu-id="6eeae-117">If any version of `NetStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="6eeae-118">Inclusiones de compilación predeterminadas en proyectos .NET Core</span><span class="sxs-lookup"><span data-stu-id="6eeae-118">Default compilation includes in .NET Core projects</span></span>
<span data-ttu-id="6eeae-119">Con el cambio al formato *csproj* en las últimas versiones del SDK, hemos trasladado las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos incrustados a los archivos de propiedades del SDK.</span><span class="sxs-lookup"><span data-stu-id="6eeae-119">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="6eeae-120">Esto implica que ya no tiene que especificar dichos elementos en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-120">This means that you no longer need to specify these items in your project file.</span></span> 

<span data-ttu-id="6eeae-121">El principal motivo de este cambio consiste en reducir el desorden en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-121">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="6eeae-122">Los valores predeterminados presentes en el SDK deberían abarcar los casos de uso más habituales, por lo que no resulta necesario repetirlos en todos los proyectos que cree.</span><span class="sxs-lookup"><span data-stu-id="6eeae-122">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="6eeae-123">Esto da lugar a archivos de proyecto más pequeños que resultan mucho más fáciles de entender, así como de editar manualmente si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="6eeae-123">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span> 

<span data-ttu-id="6eeae-124">En la siguiente tabla se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK:</span><span class="sxs-lookup"><span data-stu-id="6eeae-124">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span> 

| <span data-ttu-id="6eeae-125">Elemento</span><span class="sxs-lookup"><span data-stu-id="6eeae-125">Element</span></span>           | <span data-ttu-id="6eeae-126">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="6eeae-126">Include glob</span></span>                              | <span data-ttu-id="6eeae-127">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="6eeae-127">Exclude glob</span></span>                                                  | <span data-ttu-id="6eeae-128">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="6eeae-128">Remove glob</span></span>                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="6eeae-129">Compile</span><span class="sxs-lookup"><span data-stu-id="6eeae-129">Compile</span></span>           | <span data-ttu-id="6eeae-130">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="6eeae-130">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="6eeae-131">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="6eeae-131">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="6eeae-132">N/D</span><span class="sxs-lookup"><span data-stu-id="6eeae-132">N/A</span></span>                        |
| <span data-ttu-id="6eeae-133">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="6eeae-133">EmbeddedResource</span></span>  | <span data-ttu-id="6eeae-134">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="6eeae-134">\*\*/\*.resx</span></span>                              | <span data-ttu-id="6eeae-135">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="6eeae-135">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="6eeae-136">N/D</span><span class="sxs-lookup"><span data-stu-id="6eeae-136">N/A</span></span>                        |
| <span data-ttu-id="6eeae-137">Ninguna</span><span class="sxs-lookup"><span data-stu-id="6eeae-137">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="6eeae-138">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="6eeae-138">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="6eeae-139">- \*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="6eeae-139">- \*\*/\*.cs; \*\*/\*.resx</span></span> |

<span data-ttu-id="6eeae-140">Si tiene globs en el proyecto e intenta crearlo usando el SDK más reciente, le aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="6eeae-140">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="6eeae-141">Se han incluido elementos de compilación duplicados.</span><span class="sxs-lookup"><span data-stu-id="6eeae-141">Duplicate Compile items were included.</span></span> <span data-ttu-id="6eeae-142">El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="6eeae-142">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="6eeae-143">Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-143">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span> 

<span data-ttu-id="6eeae-144">Para evitar este error, puede quitar los elementos `Compile` explícitos que coinciden con los que aparecen en la tabla anterior o establecer la propiedad `<EnableDefaultCompileItems>` en `false` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="6eeae-144">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
<span data-ttu-id="6eeae-145">Al establecer esta propiedad en `false`, se invalidará la inclusión implícita y el comportamiento se revertirá a los SDK anteriores en los que tenía que especificar los globs predeterminados en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-145">Setting this property to `false` will override implicit inclusion and the behavior will revert back to the previous SDKs where you had to specify the default globs in your project.</span></span> 

<span data-ttu-id="6eeae-146">Este cambio no modifica los mecanismos principales de otras inclusiones.</span><span class="sxs-lookup"><span data-stu-id="6eeae-146">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="6eeae-147">En cambio, si quiere especificar, por ejemplo, que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos con los que está familiarizado en *csproj* (por ejemplo, el elemento `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="6eeae-147">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="6eeae-148">`<EnableDefaultCompileItems>` solo deshabilita globs `Compile`, pero no afecta a otros globs, como el glob `None` implícito, que también se aplica a elementos \*.cs.</span><span class="sxs-lookup"><span data-stu-id="6eeae-148">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="6eeae-149">Por eso, el **Explorador de soluciones** sigue mostrando elementos \*.cs como parte del proyecto, incluso como elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-149">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="6eeae-150">Del mismo modo, puede usar `<EnableDefaultNoneItems>` para deshabilitar el glob `None` implícito.</span><span class="sxs-lookup"><span data-stu-id="6eeae-150">In a similar way, you can use `<EnableDefaultNoneItems>` to disable the implicit `None` glob.</span></span>

<span data-ttu-id="6eeae-151">Para deshabilitar **todos los globs implícitos**, puede establecer la propiedad `<EnableDefaultItems>` en `false` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="6eeae-151">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a><span data-ttu-id="6eeae-152">Recomendación</span><span class="sxs-lookup"><span data-stu-id="6eeae-152">Recommendation</span></span>
<span data-ttu-id="6eeae-153">Con csproj, se recomienda quitar los globs predeterminados del proyecto y agregar solo rutas de archivos con globs para aquellos artefactos que su aplicación o biblioteca necesita para varios escenarios (por ejemplo, tiempo de ejecución y empaquetado NuGet).</span><span class="sxs-lookup"><span data-stu-id="6eeae-153">With csproj, we recommend that you remove the default globs from your project and only add file paths with globs for those artifacts that your app/library needs for various scenarios (for example, runtime and NuGet packaging).</span></span>

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="6eeae-154">Visualización del proyecto completo tal como MSBuild lo ve</span><span class="sxs-lookup"><span data-stu-id="6eeae-154">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="6eeae-155">Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos.</span><span class="sxs-lookup"><span data-stu-id="6eeae-155">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="6eeae-156">Preprocese el proyecto con [el conmutador `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:</span><span class="sxs-lookup"><span data-stu-id="6eeae-156">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild /pp:fullproject.xml`

<span data-ttu-id="6eeae-157">Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="6eeae-157">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="6eeae-158">Adiciones</span><span class="sxs-lookup"><span data-stu-id="6eeae-158">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="6eeae-159">Atributo Sdk</span><span class="sxs-lookup"><span data-stu-id="6eeae-159">Sdk attribute</span></span> 
<span data-ttu-id="6eeae-160">El elemento `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-160">The `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="6eeae-161">`Sdk` especifica qué SDK usará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-161">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="6eeae-162">El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](/visualstudio/msbuild/msbuild-tasks) y [destinos](/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="6eeae-162">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="6eeae-163">Se incluyen dos SDK principales con las herramientas de .NET Core:</span><span class="sxs-lookup"><span data-stu-id="6eeae-163">We ship two main SDKs with the .NET Core tools:</span></span>

1. <span data-ttu-id="6eeae-164">El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="6eeae-164">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="6eeae-165">El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="6eeae-165">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>

<span data-ttu-id="6eeae-166">Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código.</span><span class="sxs-lookup"><span data-stu-id="6eeae-166">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span> 

### <a name="packagereference"></a><span data-ttu-id="6eeae-167">PackageReference</span><span class="sxs-lookup"><span data-stu-id="6eeae-167">PackageReference</span></span>
<span data-ttu-id="6eeae-168">Elemento que especifica una dependencia de NuGet en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-168">Item that specifies a NuGet dependency in the project.</span></span> <span data-ttu-id="6eeae-169">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-169">The `Include` attribute specifies the package ID.</span></span> 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="6eeae-170">Versión</span><span class="sxs-lookup"><span data-stu-id="6eeae-170">Version</span></span>
<span data-ttu-id="6eeae-171">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="6eeae-171">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="6eeae-172">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6eeae-172">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="6eeae-173">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="6eeae-173">The default behavior is an exact version match.</span></span> <span data-ttu-id="6eeae-174">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-174">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="6eeae-175">IncludeAssets, ExcludeAssets y PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="6eeae-175">IncludeAssets, ExcludeAssets and PrivateAssets</span></span>
<span data-ttu-id="6eeae-176">El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="6eeae-176">`IncludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> 

<span data-ttu-id="6eeae-177">El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="6eeae-177">`ExcludeAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="6eeae-178">El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="6eeae-178">`PrivateAssets` attribute specifies what assets belonging to the package specified by `<PackageReference>` should be consumed but that they should not flow to the next project.</span></span> 

> [!NOTE]
> <span data-ttu-id="6eeae-179">`PrivateAssets` es equivalente al elemento *project.json*/*xproj* `SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-179">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="6eeae-180">Estos atributos pueden contener uno o varios de los siguientes elementos:</span><span class="sxs-lookup"><span data-stu-id="6eeae-180">These attributes can contain one or more of the following items:</span></span>

* <span data-ttu-id="6eeae-181">`Compile`: el contenido de la carpeta lib está disponible para compilación.</span><span class="sxs-lookup"><span data-stu-id="6eeae-181">`Compile` – the contents of the lib folder are available to compile against.</span></span>
* <span data-ttu-id="6eeae-182">`Runtime`: el contenido de la carpeta runtime está distribuido.</span><span class="sxs-lookup"><span data-stu-id="6eeae-182">`Runtime` – the contents of the runtime folder are distributed.</span></span>
* <span data-ttu-id="6eeae-183">`ContentFiles`: se usa el contenido de la carpeta *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-183">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
* <span data-ttu-id="6eeae-184">`Build`: se usan los archivos props/targets de la carpeta de compilación.</span><span class="sxs-lookup"><span data-stu-id="6eeae-184">`Build` – the props/targets in the build folder are used.</span></span>
* <span data-ttu-id="6eeae-185">`Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="6eeae-185">`Native` – the contents from native assets are copied to the output folder for runtime.</span></span>
* <span data-ttu-id="6eeae-186">`Analyzers`: se usan los analizadores.</span><span class="sxs-lookup"><span data-stu-id="6eeae-186">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="6eeae-187">Como alternativa, el atributo puede contener:</span><span class="sxs-lookup"><span data-stu-id="6eeae-187">Alternatively, the attribute can contain:</span></span>

* <span data-ttu-id="6eeae-188">`None`: no se usa ninguno de los recursos.</span><span class="sxs-lookup"><span data-stu-id="6eeae-188">`None` – none of the assets are used.</span></span>
* <span data-ttu-id="6eeae-189">`All`: se usan todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="6eeae-189">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="6eeae-190">DotnetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="6eeae-190">DotNetCliToolReference</span></span>
<span data-ttu-id="6eeae-191">El elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-191">`<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="6eeae-192">Es un sustituto del nodo `tools` de *project.json*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-192">It's a replacement for the `tools` node in *project.json*.</span></span> 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a><span data-ttu-id="6eeae-193">Versión</span><span class="sxs-lookup"><span data-stu-id="6eeae-193">Version</span></span>
<span data-ttu-id="6eeae-194">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="6eeae-194">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="6eeae-195">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="6eeae-195">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="6eeae-196">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="6eeae-196">The default behavior is an exact version match.</span></span> <span data-ttu-id="6eeae-197">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-197">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="6eeae-198">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="6eeae-198">RuntimeIdentifiers</span></span>
<span data-ttu-id="6eeae-199">El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-199">The `<RuntimeIdentifiers>` element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="6eeae-200">Los RID permiten publicar implementaciones autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="6eeae-200">RIDs enable publishing a self-contained deployments.</span></span> 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="6eeae-201">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="6eeae-201">RuntimeIdentifier</span></span>
<span data-ttu-id="6eeae-202">El elemento `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-202">The `<RuntimeIdentifier>` element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="6eeae-203">Los RID permiten publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="6eeae-203">RIDs enable publishing a self-contained deployment.</span></span> 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a><span data-ttu-id="6eeae-204">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="6eeae-204">PackageTargetFallback</span></span> 
<span data-ttu-id="6eeae-205">El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes.</span><span class="sxs-lookup"><span data-stu-id="6eeae-205">The `<PackageTargetFallback>` element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="6eeae-206">Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="6eeae-206">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="6eeae-207">Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet.</span><span class="sxs-lookup"><span data-stu-id="6eeae-207">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span> 

<span data-ttu-id="6eeae-208">En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto:</span><span class="sxs-lookup"><span data-stu-id="6eeae-208">The following example provides the fallbacks for all targets in your project:</span></span> 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="6eeae-209">En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp1.0`:</span><span class="sxs-lookup"><span data-stu-id="6eeae-209">The following example specifies the fallbacks only for the `netcoreapp1.0` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a><span data-ttu-id="6eeae-210">Propiedades de metadatos de NuGet</span><span class="sxs-lookup"><span data-stu-id="6eeae-210">NuGet metadata properties</span></span>
<span data-ttu-id="6eeae-211">Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete de NuGet de archivos *project.json* a *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-211">With the move to MSbuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="6eeae-212">Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-212">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="6eeae-213">La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK.</span><span class="sxs-lookup"><span data-stu-id="6eeae-213">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK.</span></span> 

### <a name="ispackable"></a><span data-ttu-id="6eeae-214">IsPackable</span><span class="sxs-lookup"><span data-stu-id="6eeae-214">IsPackable</span></span>
<span data-ttu-id="6eeae-215">Un valor booleano que especifica si se puede empaquetar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-215">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="6eeae-216">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-216">The default value is `true`.</span></span> 

### <a name="packageversion"></a><span data-ttu-id="6eeae-217">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="6eeae-217">PackageVersion</span></span>
<span data-ttu-id="6eeae-218">Especifica la versión que tendrá el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="6eeae-218">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="6eeae-219">Acepta todos los formatos de la cadena de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="6eeae-219">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="6eeae-220">El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-220">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span> 

### <a name="packageid"></a><span data-ttu-id="6eeae-221">PackageId</span><span class="sxs-lookup"><span data-stu-id="6eeae-221">PackageId</span></span>
<span data-ttu-id="6eeae-222">Especifica el nombre para el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="6eeae-222">Specifies the name for the resulting package.</span></span> <span data-ttu-id="6eeae-223">Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-223">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span> 

### <a name="title"></a><span data-ttu-id="6eeae-224">Title</span><span class="sxs-lookup"><span data-stu-id="6eeae-224">Title</span></span>
<span data-ttu-id="6eeae-225">Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6eeae-225">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="6eeae-226">Si no se especifica, se usa el identificador del paquete en su lugar.</span><span class="sxs-lookup"><span data-stu-id="6eeae-226">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="6eeae-227">Authors</span><span class="sxs-lookup"><span data-stu-id="6eeae-227">Authors</span></span>
<span data-ttu-id="6eeae-228">Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="6eeae-228">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="description"></a><span data-ttu-id="6eeae-229">Description</span><span class="sxs-lookup"><span data-stu-id="6eeae-229">Description</span></span>
<span data-ttu-id="6eeae-230">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6eeae-230">A long description of the package for UI display.</span></span>

### <a name="copyright"></a><span data-ttu-id="6eeae-231">Copyright</span><span class="sxs-lookup"><span data-stu-id="6eeae-231">Copyright</span></span>
<span data-ttu-id="6eeae-232">Detalles de copyright del paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-232">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="6eeae-233">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="6eeae-233">PackageRequireLicenseAcceptance</span></span>
<span data-ttu-id="6eeae-234">Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo.</span><span class="sxs-lookup"><span data-stu-id="6eeae-234">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="6eeae-235">El valor predeterminado es `false`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-235">The default is `false`.</span></span>

### <a name="packagelicenseurl"></a><span data-ttu-id="6eeae-236">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="6eeae-236">PackageLicenseUrl</span></span>
<span data-ttu-id="6eeae-237">Una dirección URL a la licencia que se aplica al paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-237">An URL to the license that is applicable to the package.</span></span>

### <a name="packageprojecturl"></a><span data-ttu-id="6eeae-238">PackageProjectUrl</span><span class="sxs-lookup"><span data-stu-id="6eeae-238">PackageProjectUrl</span></span>
<span data-ttu-id="6eeae-239">Una dirección URL de la página principal del paquete, que a menudo se muestra en las visualizaciones de la interfaz de usuario, así como en nuget.org.</span><span class="sxs-lookup"><span data-stu-id="6eeae-239">A URL for the package's home page, often shown in UI displays as well as nuget.org.</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="6eeae-240">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="6eeae-240">PackageIconUrl</span></span>
<span data-ttu-id="6eeae-241">Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="6eeae-241">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="6eeae-242">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="6eeae-242">PackageReleaseNotes</span></span>
<span data-ttu-id="6eeae-243">Notas de la versión para el paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-243">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="6eeae-244">PackageTags</span><span class="sxs-lookup"><span data-stu-id="6eeae-244">PackageTags</span></span>
<span data-ttu-id="6eeae-245">Una lista de etiquetas delimitada por punto y coma que designa el paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-245">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="6eeae-246">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="6eeae-246">PackageOutputPath</span></span>
<span data-ttu-id="6eeae-247">Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado.</span><span class="sxs-lookup"><span data-stu-id="6eeae-247">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="6eeae-248">El valor predeterminado es `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-248">Default is `$(OutputPath)`.</span></span> 

### <a name="includesymbols"></a><span data-ttu-id="6eeae-249">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="6eeae-249">IncludeSymbols</span></span>
<span data-ttu-id="6eeae-250">Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto.</span><span class="sxs-lookup"><span data-stu-id="6eeae-250">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="6eeae-251">Este paquete tendrá una extensión *.symbols.nupkg* y copiará los archivos PDB junto con el archivo DLL y otros archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="6eeae-251">This package will have a *.symbols.nupkg* extension and will copy the PDB files along with the DLL and other output files.</span></span>

### <a name="includesource"></a><span data-ttu-id="6eeae-252">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="6eeae-252">IncludeSource</span></span>
<span data-ttu-id="6eeae-253">Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen.</span><span class="sxs-lookup"><span data-stu-id="6eeae-253">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="6eeae-254">El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="6eeae-254">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="6eeae-255">Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="6eeae-255">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span> 

### <a name="istool"></a><span data-ttu-id="6eeae-256">IsTool</span><span class="sxs-lookup"><span data-stu-id="6eeae-256">IsTool</span></span>
<span data-ttu-id="6eeae-257">Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-257">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="6eeae-258">Tenga en cuenta que esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-258">Note that this is different from a `DotNetCliTool` which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="6eeae-259">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="6eeae-259">RepositoryUrl</span></span>
<span data-ttu-id="6eeae-260">Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando.</span><span class="sxs-lookup"><span data-stu-id="6eeae-260">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span> 

### <a name="repositorytype"></a><span data-ttu-id="6eeae-261">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="6eeae-261">RepositoryType</span></span>
<span data-ttu-id="6eeae-262">Especifica el tipo del repositorio.</span><span class="sxs-lookup"><span data-stu-id="6eeae-262">Specifies the type of the repository.</span></span> <span data-ttu-id="6eeae-263">El valor predeterminado es “git”.</span><span class="sxs-lookup"><span data-stu-id="6eeae-263">Default is "git".</span></span> 

### <a name="nopackageanalysis"></a><span data-ttu-id="6eeae-264">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="6eeae-264">NoPackageAnalysis</span></span>
<span data-ttu-id="6eeae-265">Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="6eeae-265">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="6eeae-266">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="6eeae-266">MinClientVersion</span></span>
<span data-ttu-id="6eeae-267">Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="6eeae-267">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="6eeae-268">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="6eeae-268">IncludeBuildOutput</span></span>
<span data-ttu-id="6eeae-269">Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.</span><span class="sxs-lookup"><span data-stu-id="6eeae-269">This Boolean values specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="6eeae-270">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="6eeae-270">IncludeContentInPack</span></span>
<span data-ttu-id="6eeae-271">Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="6eeae-271">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="6eeae-272">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="6eeae-272">The default is `true`.</span></span> 

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="6eeae-273">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="6eeae-273">BuildOutputTargetFolder</span></span>
<span data-ttu-id="6eeae-274">Especifica la carpeta en la que se colocarán los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="6eeae-274">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="6eeae-275">Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.</span><span class="sxs-lookup"><span data-stu-id="6eeae-275">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="6eeae-276">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="6eeae-276">ContentTargetFolders</span></span>
<span data-ttu-id="6eeae-277">Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos.</span><span class="sxs-lookup"><span data-stu-id="6eeae-277">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="6eeae-278">El valor predeterminado es “content;contentFiles”.</span><span class="sxs-lookup"><span data-stu-id="6eeae-278">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="6eeae-279">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="6eeae-279">NuspecFile</span></span>
<span data-ttu-id="6eeae-280">Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="6eeae-280">Relative or absolute path to the *.nuspec* file being used for packing.</span></span> 

> [!NOTE]
> <span data-ttu-id="6eeae-281">Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos.</span><span class="sxs-lookup"><span data-stu-id="6eeae-281">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span> 

### <a name="nuspecbasepath"></a><span data-ttu-id="6eeae-282">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="6eeae-282">NuspecBasePath</span></span>
<span data-ttu-id="6eeae-283">Ruta de acceso base para el archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="6eeae-283">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="6eeae-284">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="6eeae-284">NuspecProperties</span></span>
<span data-ttu-id="6eeae-285">Lista separada por punto y coma de pares clave=valor.</span><span class="sxs-lookup"><span data-stu-id="6eeae-285">Semicolon separated list of key=value pairs.</span></span>
