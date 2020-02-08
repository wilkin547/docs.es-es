---
title: Adiciones al formato csproj para .NET Core
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
ms.date: 04/08/2019
ms.openlocfilehash: 126f5b10999e65d9715e9b52cb54a2bf1dbd3933
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76787879"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a><span data-ttu-id="a5194-103">Adiciones al formato csproj para .NET Core</span><span class="sxs-lookup"><span data-stu-id="a5194-103">Additions to the csproj format for .NET Core</span></span>

<span data-ttu-id="a5194-104">En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild).</span><span class="sxs-lookup"><span data-stu-id="a5194-104">This document outlines the changes that were added to the project files as part of the move from *project.json* to *csproj* and [MSBuild](https://github.com/Microsoft/MSBuild).</span></span> <span data-ttu-id="a5194-105">Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).</span><span class="sxs-lookup"><span data-stu-id="a5194-105">For more information about general project file syntax and reference, see [the MSBuild project file](/visualstudio/msbuild/msbuild-project-file-schema-reference) documentation.</span></span>

## <a name="implicit-package-references"></a><span data-ttu-id="a5194-106">Referencias implícitas del paquete</span><span class="sxs-lookup"><span data-stu-id="a5194-106">Implicit package references</span></span>

<span data-ttu-id="a5194-107">Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-107">Metapackages are implicitly referenced based on the target framework(s) specified in the `<TargetFramework>` or `<TargetFrameworks>` property of your project file.</span></span> <span data-ttu-id="a5194-108">`<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.</span><span class="sxs-lookup"><span data-stu-id="a5194-108">`<TargetFrameworks>` is ignored if `<TargetFramework>` is specified, independent of order.</span></span> <span data-ttu-id="a5194-109">Para obtener más información, vea [Paquetes, metapaquetes y marcos de trabajo](../packages.md).</span><span class="sxs-lookup"><span data-stu-id="a5194-109">For more information, see [Packages, metapackages, and frameworks](../packages.md).</span></span>

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

### <a name="recommendations"></a><span data-ttu-id="a5194-110">Recomendaciones</span><span class="sxs-lookup"><span data-stu-id="a5194-110">Recommendations</span></span>

<span data-ttu-id="a5194-111">Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NETStandard.Library`, estos son los procedimientos recomendados:</span><span class="sxs-lookup"><span data-stu-id="a5194-111">Since `Microsoft.NETCore.App` or `NETStandard.Library` metapackages are implicitly referenced, the following are our recommended best practices:</span></span>

- <span data-ttu-id="a5194-112">Si el destino es .NET Core o .NET Standard, nunca incluya una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NETStandard.Library` mediante un elemento `<PackageReference>` en el archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-112">When targeting .NET Core or .NET Standard, never have an explicit reference to the `Microsoft.NETCore.App` or `NETStandard.Library` metapackages via a `<PackageReference>` item in your project file.</span></span>
- <span data-ttu-id="a5194-113">Si necesita una versión concreta del runtime cuando el destino es .NET Core, debe usar la propiedad `<RuntimeFrameworkVersion>` del proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-113">If you need a specific version of the runtime when targeting .NET Core, you should use the `<RuntimeFrameworkVersion>` property in your project (for example, `1.0.4`) instead of referencing the metapackage.</span></span>
  - <span data-ttu-id="a5194-114">Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.</span><span class="sxs-lookup"><span data-stu-id="a5194-114">This might happen if you are using [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) and you need a specific patch version of 1.0.0 LTS runtime, for example.</span></span>
- <span data-ttu-id="a5194-115">Si necesita una versión concreta del metapaquete `NETStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.</span><span class="sxs-lookup"><span data-stu-id="a5194-115">If you need a specific version of the `NETStandard.Library` metapackage when targeting .NET Standard, you can use the `<NetStandardImplicitPackageVersion>` property and set the version you need.</span></span>
- <span data-ttu-id="a5194-116">No agregue referencias a los metapaquetes `Microsoft.NETCore.App` y `NETStandard.Library` ni las actualice explícitamente en proyectos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="a5194-116">Don't explicitly add or update references to either the `Microsoft.NETCore.App` or `NETStandard.Library` metapackage in .NET Framework projects.</span></span> <span data-ttu-id="a5194-117">Si se necesita alguna versión de `NETStandard.Library` al usar un paquete NuGet basado en .NET Standard, NuGet instala automáticamente esa versión.</span><span class="sxs-lookup"><span data-stu-id="a5194-117">If any version of `NETStandard.Library` is needed when using a .NET Standard-based NuGet package, NuGet automatically installs that version.</span></span>

## <a name="implicit-version-for-some-package-references"></a><span data-ttu-id="a5194-118">Versión implícita para algunas referencias de paquete</span><span class="sxs-lookup"><span data-stu-id="a5194-118">Implicit version for some package references</span></span>

<span data-ttu-id="a5194-119">La mayoría de los usos de [`<PackageReference>`](#packagereference) requieren establecer el atributo `Version` para especificar la versión del paquete de NuGet que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="a5194-119">Most usages of [`<PackageReference>`](#packagereference) require setting the `Version` attribute to specify the NuGet package version to be used.</span></span> <span data-ttu-id="a5194-120">Sin embargo, el atributo es innecesario si se usa .NET Core 2.1 o 2.2 y se hace referencia a [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) o a [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage).</span><span class="sxs-lookup"><span data-stu-id="a5194-120">When using .NET Core 2.1 or 2.2 and referencing [Microsoft.AspNetCore.App](/aspnet/core/fundamentals/metapackage-app) or [Microsoft.AspNetCore.All](/aspnet/core/fundamentals/metapackage), however, the  attribute is unnecessary.</span></span> <span data-ttu-id="a5194-121">El SDK de .NET Core puede seleccionar automáticamente la versión que se debe usar de estos paquetes.</span><span class="sxs-lookup"><span data-stu-id="a5194-121">The .NET Core SDK can automatically select the version of these packages that should be used.</span></span>

### <a name="recommendation"></a><span data-ttu-id="a5194-122">Recomendación</span><span class="sxs-lookup"><span data-stu-id="a5194-122">Recommendation</span></span>

<span data-ttu-id="a5194-123">Cuando haga referencia al paquete `Microsoft.AspNetCore.App` o al paquete `Microsoft.AspNetCore.All`, no especifique la versión.</span><span class="sxs-lookup"><span data-stu-id="a5194-123">When referencing the `Microsoft.AspNetCore.App` or `Microsoft.AspNetCore.All` packages, do not specify their version.</span></span> <span data-ttu-id="a5194-124">Si se especifica una versión, el SDK podría generar la advertencia NETSDK1071.</span><span class="sxs-lookup"><span data-stu-id="a5194-124">If a version is specified, the SDK may produce warning NETSDK1071.</span></span> <span data-ttu-id="a5194-125">Para corregir esta advertencia, quite la versión de paquete como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5194-125">To fix this warning, remove the package version like in the following example:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore.App" />
</ItemGroup>
```

> <span data-ttu-id="a5194-126">Problema conocido: el SDK de .NET Core 2.1 solo admite esta sintaxis cuando el proyecto también usa Microsoft.NET.Sdk.Web.</span><span class="sxs-lookup"><span data-stu-id="a5194-126">Known issue: the .NET Core 2.1 SDK only supported this syntax when the project also uses Microsoft.NET.Sdk.Web.</span></span> <span data-ttu-id="a5194-127">Esto se resuelve en el SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="a5194-127">This is resolved in the .NET Core 2.2 SDK.</span></span>

<span data-ttu-id="a5194-128">Estas referencias a los metapaquetes de ASP.NET Core tienen un comportamiento ligeramente distinto de los paquetes más habituales de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5194-128">These references to ASP.NET Core metapackages have a slightly different behavior from most normal NuGet packages.</span></span> <span data-ttu-id="a5194-129">Las [implementaciones dependientes del marco](../deploying/index.md#framework-dependent-deployments-fdd) de las aplicaciones que usan estos metapaquetes aprovechan automáticamente el marco de uso compartido de ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5194-129">[Framework-dependent deployments](../deploying/index.md#framework-dependent-deployments-fdd) of applications that use these metapackages automatically take advantage of the ASP.NET Core shared framework.</span></span> <span data-ttu-id="a5194-130">Al usar los metapaquetes, **no** se implementa ningún recurso de los paquetes NuGet de ASP.NET Core a los que se hace referencia con la aplicación, porque el marco de uso compartido de ASP.NET Core ya contiene estos recursos.</span><span class="sxs-lookup"><span data-stu-id="a5194-130">When you use the metapackages, **no** assets from the referenced ASP.NET Core NuGet packages are deployed with the application—the ASP.NET Core shared framework contains these assets.</span></span> <span data-ttu-id="a5194-131">Los recursos del marco de uso compartido están optimizados para que la plataforma de destino mejore el tiempo de inicio de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="a5194-131">The assets in the shared framework are optimized for the target platform to improve application startup time.</span></span> <span data-ttu-id="a5194-132">Para más información sobre el marco de uso compartido, consulte [Empaquetado de distribución de .NET Core](../distribution-packaging.md).</span><span class="sxs-lookup"><span data-stu-id="a5194-132">For more information about shared framework, see [.NET Core distribution packaging](../distribution-packaging.md).</span></span>

<span data-ttu-id="a5194-133">Si *se especifica* una versión, se trata como la versión *mínima* del marco de uso compartido de ASP.NET Core para las implementaciones dependientes del marco y como una versión *exacta* de las implementaciones autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="a5194-133">If a version *is* specified, it's treated as the *minimum* version of ASP.NET Core shared framework for framework-dependent deployments and as an *exact* version for self-contained deployments.</span></span> <span data-ttu-id="a5194-134">Esto puede deberse a las siguientes consecuencias:</span><span class="sxs-lookup"><span data-stu-id="a5194-134">This can have the following consequences:</span></span>

- <span data-ttu-id="a5194-135">Si la versión de ASP.NET Core instalada en el servidor es anterior a la versión especificada en PackageReference, no se iniciará el proceso de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5194-135">If the version of ASP.NET Core installed on the server is less than the version specified on the PackageReference, the .NET Core process fails to launch.</span></span> <span data-ttu-id="a5194-136">Por lo general, las actualizaciones del metapaquete están disponibles en NuGet.org antes de que se aparezcan en entornos de hospedaje como Azure.</span><span class="sxs-lookup"><span data-stu-id="a5194-136">Updates to the metapackage are often available on NuGet.org before updates have been made available in hosting environments such as Azure.</span></span> <span data-ttu-id="a5194-137">Actualizar la versión de PackageReference a ASP.NET Core podría provocar un error en una aplicación implementada.</span><span class="sxs-lookup"><span data-stu-id="a5194-137">Updating the version on the PackageReference to ASP.NET Core could cause a deployed application to fail.</span></span>
- <span data-ttu-id="a5194-138">Si la aplicación se implementa como una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd), es posible que no contenga las actualizaciones de seguridad más recientes a .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5194-138">If the application is deployed as a [self-contained deployment](../deploying/index.md#self-contained-deployments-scd), the application may not contain the latest security updates to .NET Core.</span></span> <span data-ttu-id="a5194-139">Cuando no se especifica una versión, el SDK puede incluir automáticamente la versión más reciente de ASP.NET Core en la implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="a5194-139">When a version isn't specified, the SDK can automatically include the newest version of ASP.NET Core in the self-contained deployment.</span></span>

## <a name="default-compilation-includes-in-net-core-projects"></a><span data-ttu-id="a5194-140">Inclusiones de compilación predeterminadas en proyectos .NET Core</span><span class="sxs-lookup"><span data-stu-id="a5194-140">Default compilation includes in .NET Core projects</span></span>

<span data-ttu-id="a5194-141">Con el cambio al formato *csproj* en las últimas versiones del SDK, hemos trasladado las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos incrustados a los archivos de propiedades del SDK.</span><span class="sxs-lookup"><span data-stu-id="a5194-141">With the move to the *csproj* format in the latest SDK versions, we've moved the default includes and excludes for compile items and embedded resources to the SDK properties files.</span></span> <span data-ttu-id="a5194-142">Esto implica que ya no tiene que especificar dichos elementos en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-142">This means that you no longer need to specify these items in your project file.</span></span>

<span data-ttu-id="a5194-143">El principal motivo de este cambio consiste en reducir el desorden en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-143">The main reason for doing this is to reduce the clutter in your project file.</span></span> <span data-ttu-id="a5194-144">Los valores predeterminados presentes en el SDK deberían abarcar los casos de uso más habituales, por lo que no resulta necesario repetirlos en todos los proyectos que cree.</span><span class="sxs-lookup"><span data-stu-id="a5194-144">The defaults that are present in the SDK should cover most common use cases, so there is no need to repeat them in every project that you create.</span></span> <span data-ttu-id="a5194-145">Esto da lugar a archivos de proyecto más pequeños que resultan mucho más fáciles de entender, así como de editar manualmente si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="a5194-145">This leads to smaller project files that are much easier to understand as well as edit by hand, if needed.</span></span>

<span data-ttu-id="a5194-146">En la siguiente tabla se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK:</span><span class="sxs-lookup"><span data-stu-id="a5194-146">The following table shows which element and which [globs](https://en.wikipedia.org/wiki/Glob_(programming)) are both included and excluded in the SDK:</span></span>

| <span data-ttu-id="a5194-147">Elemento</span><span class="sxs-lookup"><span data-stu-id="a5194-147">Element</span></span>           | <span data-ttu-id="a5194-148">Glob para incluir</span><span class="sxs-lookup"><span data-stu-id="a5194-148">Include glob</span></span>                              | <span data-ttu-id="a5194-149">Glob para excluir</span><span class="sxs-lookup"><span data-stu-id="a5194-149">Exclude glob</span></span>                                                  | <span data-ttu-id="a5194-150">Glob para quitar</span><span class="sxs-lookup"><span data-stu-id="a5194-150">Remove glob</span></span>              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| <span data-ttu-id="a5194-151">Compile</span><span class="sxs-lookup"><span data-stu-id="a5194-151">Compile</span></span>           | <span data-ttu-id="a5194-152">\*\*/\*.cs (u otras extensiones de lenguaje)</span><span class="sxs-lookup"><span data-stu-id="a5194-152">\*\*/\*.cs (or other language extensions)</span></span> | <span data-ttu-id="a5194-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a5194-153">\*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc</span></span>  | <span data-ttu-id="a5194-154">N/D</span><span class="sxs-lookup"><span data-stu-id="a5194-154">N/A</span></span>                      |
| <span data-ttu-id="a5194-155">EmbeddedResource</span><span class="sxs-lookup"><span data-stu-id="a5194-155">EmbeddedResource</span></span>  | <span data-ttu-id="a5194-156">\*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a5194-156">\*\*/\*.resx</span></span>                              | <span data-ttu-id="a5194-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a5194-157">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a5194-158">N/D</span><span class="sxs-lookup"><span data-stu-id="a5194-158">N/A</span></span>                      |
| <span data-ttu-id="a5194-159">None</span><span class="sxs-lookup"><span data-stu-id="a5194-159">None</span></span>              | \*\*/\*                                   | <span data-ttu-id="a5194-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span><span class="sxs-lookup"><span data-stu-id="a5194-160">\*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc</span></span>     | <span data-ttu-id="a5194-161">\*\*/\*.cs; \*\*/\*.resx</span><span class="sxs-lookup"><span data-stu-id="a5194-161">\*\*/\*.cs; \*\*/\*.resx</span></span>   |

> [!NOTE]
> <span data-ttu-id="a5194-162">**Glob para excluir** siempre excluye las carpetas `./bin` y `./obj`, que se representan mediante las propiedades `$(BaseOutputPath)` y `$(BaseIntermediateOutputPath)` de MSBuild, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="a5194-162">**Exclude glob** always excludes the `./bin` and `./obj` folders, which are represented by the `$(BaseOutputPath)` and `$(BaseIntermediateOutputPath)` MSBuild properties, respectively.</span></span> <span data-ttu-id="a5194-163">En su conjunto, todos los "exclude" se representan mediante `$(DefaultItemExcludes)`.</span><span class="sxs-lookup"><span data-stu-id="a5194-163">As a whole, all excludes are represented by `$(DefaultItemExcludes)`.</span></span>

<span data-ttu-id="a5194-164">Si tiene globs en el proyecto e intenta crearlo usando el SDK más reciente, le aparecerá el siguiente error:</span><span class="sxs-lookup"><span data-stu-id="a5194-164">If you have globs in your project and you try to build it using the newest SDK, you'll get the following error:</span></span>

> <span data-ttu-id="a5194-165">Se han incluido elementos de compilación duplicados.</span><span class="sxs-lookup"><span data-stu-id="a5194-165">Duplicate Compile items were included.</span></span> <span data-ttu-id="a5194-166">El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5194-166">The .NET SDK includes Compile items from your project directory by default.</span></span> <span data-ttu-id="a5194-167">Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-167">You can either remove these items from your project file, or set the 'EnableDefaultCompileItems' property to 'false' if you want to explicitly include them in your project file.</span></span>

<span data-ttu-id="a5194-168">Para evitar este error, puede quitar los elementos `Compile` explícitos que coinciden con los que aparecen en la tabla anterior o establecer la propiedad `<EnableDefaultCompileItems>` en `false` de esta forma:</span><span class="sxs-lookup"><span data-stu-id="a5194-168">In order to get around this error, you can either remove the explicit `Compile` items that match the ones listed on the previous table, or you can set the `<EnableDefaultCompileItems>` property to `false`, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

<span data-ttu-id="a5194-169">Al establecer esta propiedad en `false`, se deshabilita la inclusión implícita y se revierte el comportamiento de SDK anteriores en los que había que especificar los globs predeterminados del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-169">Setting this property to `false` will disable implicit inclusion, reverting to the behavior of previous SDKs where you had to specify the default globs in your project.</span></span>

<span data-ttu-id="a5194-170">Este cambio no modifica los mecanismos principales de otras inclusiones.</span><span class="sxs-lookup"><span data-stu-id="a5194-170">This change does not modify the main mechanics of other includes.</span></span> <span data-ttu-id="a5194-171">En cambio, si quiere especificar, por ejemplo, que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos con los que está familiarizado en *csproj* (por ejemplo, el elemento `<Content>`).</span><span class="sxs-lookup"><span data-stu-id="a5194-171">However, if you wish to specify, for example, some files to get published with your app, you can still use the known mechanisms in *csproj* for that (for example, the `<Content>` element).</span></span>

<span data-ttu-id="a5194-172">`<EnableDefaultCompileItems>` solo deshabilita globs `Compile`, pero no afecta a otros globs, como el glob `None` implícito, que también se aplica a elementos \*.cs.</span><span class="sxs-lookup"><span data-stu-id="a5194-172">`<EnableDefaultCompileItems>` only disables `Compile` globs but doesn't affect other globs, like the implicit `None` glob, which also applies to \*.cs items.</span></span> <span data-ttu-id="a5194-173">Por eso, el **Explorador de soluciones** sigue mostrando elementos \*.cs como parte del proyecto, incluso como elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="a5194-173">Because of that, **Solution Explorer** will continue show \*.cs items as part of the project, included as `None` items.</span></span> <span data-ttu-id="a5194-174">Del mismo modo, puede establecer `<EnableDefaultNoneItems>` en false para deshabilitar el glob `None` implícito, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="a5194-174">In a similar way, you can set `<EnableDefaultNoneItems>` to false to disable the implicit `None` glob, like this:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

<span data-ttu-id="a5194-175">Para deshabilitar **todos los globs implícitos**, puede establecer la propiedad `<EnableDefaultItems>` en `false` como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5194-175">To disable **all implicit globs**, you can set the `<EnableDefaultItems>` property to `false` as in the following example:</span></span>

```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a><span data-ttu-id="a5194-176">Visualización del proyecto completo tal como MSBuild lo ve</span><span class="sxs-lookup"><span data-stu-id="a5194-176">How to see the whole project as MSBuild sees it</span></span>

<span data-ttu-id="a5194-177">Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos.</span><span class="sxs-lookup"><span data-stu-id="a5194-177">While those csproj changes greatly simplify project files, you might want to see the fully expanded project as MSBuild sees it once the SDK and its targets are included.</span></span> <span data-ttu-id="a5194-178">Preprocese el proyecto con [el conmutador `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:</span><span class="sxs-lookup"><span data-stu-id="a5194-178">Preprocess the project with [the `/pp` switch](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) of the [`dotnet msbuild`](dotnet-msbuild.md) command, which shows which files are imported, their sources, and their contributions to the build without actually building the project:</span></span>

`dotnet msbuild -pp:fullproject.xml`

<span data-ttu-id="a5194-179">Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="a5194-179">If the project has multiple target frameworks, the results of the command should be focused on only one of them by specifying it as an MSBuild property:</span></span>

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a><span data-ttu-id="a5194-180">Adiciones</span><span class="sxs-lookup"><span data-stu-id="a5194-180">Additions</span></span>

### <a name="sdk-attribute"></a><span data-ttu-id="a5194-181">Atributo Sdk</span><span class="sxs-lookup"><span data-stu-id="a5194-181">Sdk attribute</span></span>

<span data-ttu-id="a5194-182">El elemento raíz `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`.</span><span class="sxs-lookup"><span data-stu-id="a5194-182">The root `<Project>` element of the *.csproj* file has a new attribute called `Sdk`.</span></span> <span data-ttu-id="a5194-183">`Sdk` especifica qué SDK usará el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-183">`Sdk` specifies which SDK will be used by the project.</span></span> <span data-ttu-id="a5194-184">El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](/visualstudio/msbuild/msbuild-tasks) y [destinos](/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="a5194-184">The SDK, as the [layering document](cli-msbuild-architecture.md) describes, is a set of MSBuild [tasks](/visualstudio/msbuild/msbuild-tasks) and [targets](/visualstudio/msbuild/msbuild-targets) that can build .NET Core code.</span></span> <span data-ttu-id="a5194-185">Los siguientes SDK están disponibles para .NET Core:</span><span class="sxs-lookup"><span data-stu-id="a5194-185">The following SDKs are available for .NET Core:</span></span>

1. <span data-ttu-id="a5194-186">El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`</span><span class="sxs-lookup"><span data-stu-id="a5194-186">The .NET Core SDK with the ID of `Microsoft.NET.Sdk`</span></span>
2. <span data-ttu-id="a5194-187">El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`</span><span class="sxs-lookup"><span data-stu-id="a5194-187">The .NET Core web SDK with the ID of `Microsoft.NET.Sdk.Web`</span></span>
3. <span data-ttu-id="a5194-188">El SDK de la biblioteca de clases de Razor de .NET Core con el id. `Microsoft.NET.Sdk.Razor`</span><span class="sxs-lookup"><span data-stu-id="a5194-188">The .NET Core Razor Class Library SDK with the ID of `Microsoft.NET.Sdk.Razor`</span></span>
4. <span data-ttu-id="a5194-189">El servicio de trabajo de .NET Core con el id. de `Microsoft.NET.Sdk.Worker` (a partir de .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="a5194-189">The .NET Core Worker Service with the ID of `Microsoft.NET.Sdk.Worker` (since .NET Core 3.0)</span></span>
5. <span data-ttu-id="a5194-190">WinForms y WPF de .NET Core con el id. de `Microsoft.NET.Sdk.WindowsDesktop` (a partir de .NET Core 3.0)</span><span class="sxs-lookup"><span data-stu-id="a5194-190">The .NET Core WinForms and WPF with the ID of `Microsoft.NET.Sdk.WindowsDesktop` (since .NET Core 3.0)</span></span>

<span data-ttu-id="a5194-191">Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código.</span><span class="sxs-lookup"><span data-stu-id="a5194-191">You need to have the `Sdk` attribute set to one of those IDs on the `<Project>` element in order to use the .NET Core tools and build your code.</span></span>

### <a name="packagereference"></a><span data-ttu-id="a5194-192">PackageReference</span><span class="sxs-lookup"><span data-stu-id="a5194-192">PackageReference</span></span>

<span data-ttu-id="a5194-193">Elemento `<PackageReference>` que especifica una [dependencia de NuGet en el proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="a5194-193">A `<PackageReference>` item element specifies a [NuGet dependency in the project](/nuget/consume-packages/package-references-in-project-files).</span></span> <span data-ttu-id="a5194-194">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-194">The `Include` attribute specifies the package ID.</span></span>

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a><span data-ttu-id="a5194-195">Versión</span><span class="sxs-lookup"><span data-stu-id="a5194-195">Version</span></span>

<span data-ttu-id="a5194-196">El atributo `Version` necesario especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="a5194-196">The required `Version` attribute specifies the version of the package to restore.</span></span> <span data-ttu-id="a5194-197">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/reference/package-versioning#version-ranges-and-wildcards).</span><span class="sxs-lookup"><span data-stu-id="a5194-197">The attribute respects the rules of the [NuGet versioning](/nuget/reference/package-versioning#version-ranges-and-wildcards) scheme.</span></span> <span data-ttu-id="a5194-198">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="a5194-198">The default behavior is an exact version match.</span></span> <span data-ttu-id="a5194-199">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-199">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

#### <a name="includeassets-excludeassets-and-privateassets"></a><span data-ttu-id="a5194-200">IncludeAssets, ExcludeAssets y PrivateAssets</span><span class="sxs-lookup"><span data-stu-id="a5194-200">IncludeAssets, ExcludeAssets, and PrivateAssets</span></span>

<span data-ttu-id="a5194-201">El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="a5194-201">`IncludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="a5194-202">De forma predeterminada, se incluyen todos los recursos del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-202">By default, all package assets are included.</span></span>

<span data-ttu-id="a5194-203">El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="a5194-203">`ExcludeAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span>

<span data-ttu-id="a5194-204">El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero no pasar al proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="a5194-204">`PrivateAssets` attribute specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="a5194-205">Cuando este atributo no existe, los recursos `Analyzers`, `Build` y `ContentFiles` son privados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="a5194-205">The `Analyzers`, `Build` and `ContentFiles` assets are private by default when this attribute is not present.</span></span>

> [!NOTE]
> <span data-ttu-id="a5194-206">`PrivateAssets` es equivalente al elemento *project.json*/*xproj*`SuppressParent`.</span><span class="sxs-lookup"><span data-stu-id="a5194-206">`PrivateAssets` is equivalent to the *project.json*/*xproj* `SuppressParent` element.</span></span>

<span data-ttu-id="a5194-207">Estos atributos pueden contener uno o varios de los siguientes elementos, separados por punto y coma `;` si aparece más de uno:</span><span class="sxs-lookup"><span data-stu-id="a5194-207">These attributes can contain one or more of the following items, separated by the semicolon `;` character if more than one is listed:</span></span>

- <span data-ttu-id="a5194-208">`Compile`: el contenido de la carpeta *lib* está disponible para compilación.</span><span class="sxs-lookup"><span data-stu-id="a5194-208">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="a5194-209">`Runtime`: el contenido de la carpeta *runtime* está distribuido.</span><span class="sxs-lookup"><span data-stu-id="a5194-209">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="a5194-210">`ContentFiles`: se usa el contenido de la carpeta *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="a5194-210">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="a5194-211">`Build`: se usan los archivos props/targets de la carpeta *build*.</span><span class="sxs-lookup"><span data-stu-id="a5194-211">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="a5194-212">`Native`: el contenido de recursos nativos se copia en la carpeta *output* en runtime.</span><span class="sxs-lookup"><span data-stu-id="a5194-212">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="a5194-213">`Analyzers`: se usan los analizadores.</span><span class="sxs-lookup"><span data-stu-id="a5194-213">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="a5194-214">Como alternativa, el atributo puede contener:</span><span class="sxs-lookup"><span data-stu-id="a5194-214">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="a5194-215">`None`: no se usa ninguno de los recursos.</span><span class="sxs-lookup"><span data-stu-id="a5194-215">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="a5194-216">`All`: se usan todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="a5194-216">`All` – all assets are used.</span></span>

### <a name="dotnetclitoolreference"></a><span data-ttu-id="a5194-217">DotnetCliToolReference</span><span class="sxs-lookup"><span data-stu-id="a5194-217">DotNetCliToolReference</span></span>

<span data-ttu-id="a5194-218">Un elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-218">A `<DotNetCliToolReference>` item element specifies the CLI tool that the user wants to restore in the context of the project.</span></span> <span data-ttu-id="a5194-219">Es un sustituto del nodo `tools` de *project.json*.</span><span class="sxs-lookup"><span data-stu-id="a5194-219">It's a replacement for the `tools` node in *project.json*.</span></span>

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

<span data-ttu-id="a5194-220">Tenga en cuenta que `DotNetCliToolReference` está [ahora en desuso](https://github.com/dotnet/announcements/issues/107) en favor de las [herramientas locales de .NET Core](https://aka.ms/local-tools).</span><span class="sxs-lookup"><span data-stu-id="a5194-220">Note that `DotNetCliToolReference` is [now deprecated](https://github.com/dotnet/announcements/issues/107) in favor of [.NET Core Local Tools](https://aka.ms/local-tools).</span></span>

#### <a name="version"></a><span data-ttu-id="a5194-221">Versión</span><span class="sxs-lookup"><span data-stu-id="a5194-221">Version</span></span>

<span data-ttu-id="a5194-222">`Version` especifica la versión del paquete que se va a restaurar.</span><span class="sxs-lookup"><span data-stu-id="a5194-222">`Version` specifies the version of the package to restore.</span></span> <span data-ttu-id="a5194-223">El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="a5194-223">The attribute respects the rules of the [NuGet versioning](/nuget/create-packages/dependency-versions#version-ranges) scheme.</span></span> <span data-ttu-id="a5194-224">El comportamiento predeterminado es una coincidencia de versión exacta.</span><span class="sxs-lookup"><span data-stu-id="a5194-224">The default behavior is an exact version match.</span></span> <span data-ttu-id="a5194-225">Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-225">For example, specifying `Version="1.2.3"` is equivalent to NuGet notation `[1.2.3]` for the exact 1.2.3 version of the package.</span></span>

### <a name="runtimeidentifiers"></a><span data-ttu-id="a5194-226">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="a5194-226">RuntimeIdentifiers</span></span>

<span data-ttu-id="a5194-227">El elemento de propiedad `<RuntimeIdentifiers>` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-227">The `<RuntimeIdentifiers>` property element lets you specify a semicolon-delimited list of [Runtime Identifiers (RIDs)](../rid-catalog.md) for the project.</span></span>
<span data-ttu-id="a5194-228">Los RID permiten publicar implementaciones autocontenidas.</span><span class="sxs-lookup"><span data-stu-id="a5194-228">RIDs enable publishing self-contained deployments.</span></span>

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a><span data-ttu-id="a5194-229">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="a5194-229">RuntimeIdentifier</span></span>

<span data-ttu-id="a5194-230">El elemento de propiedad `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-230">The `<RuntimeIdentifier>` property element allows you to specify only one [Runtime Identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="a5194-231">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="a5194-231">The RID enables publishing a self-contained deployment.</span></span>

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

<span data-ttu-id="a5194-232">Use `<RuntimeIdentifiers>` (en plural) en su lugar si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5194-232">Use `<RuntimeIdentifiers>` (plural) instead if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="a5194-233">`<RuntimeIdentifier>` puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a5194-233">`<RuntimeIdentifier>` can provide faster builds when only a single runtime is required.</span></span>

### <a name="packagetargetfallback"></a><span data-ttu-id="a5194-234">PackageTargetFallback</span><span class="sxs-lookup"><span data-stu-id="a5194-234">PackageTargetFallback</span></span>

<span data-ttu-id="a5194-235">El elemento de propiedad `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se van a usar al restaurar paquetes.</span><span class="sxs-lookup"><span data-stu-id="a5194-235">The `<PackageTargetFallback>` property element allows you to specify a set of compatible targets to be used when restoring packages.</span></span> <span data-ttu-id="a5194-236">Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM.</span><span class="sxs-lookup"><span data-stu-id="a5194-236">It's designed to allow packages that use the dotnet [TxM (Target x Moniker)](/nuget/schema/target-frameworks) to operate with packages that don't declare a dotnet TxM.</span></span> <span data-ttu-id="a5194-237">Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet.</span><span class="sxs-lookup"><span data-stu-id="a5194-237">If your project uses the dotnet TxM, then all the packages it depends on must also have a dotnet TxM, unless you add the `<PackageTargetFallback>` to your project in order to allow non-dotnet platforms to be compatible with dotnet.</span></span>

<span data-ttu-id="a5194-238">En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto:</span><span class="sxs-lookup"><span data-stu-id="a5194-238">The following example provides the fallbacks for all targets in your project:</span></span>

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

<span data-ttu-id="a5194-239">En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp2.1`:</span><span class="sxs-lookup"><span data-stu-id="a5194-239">The following example specifies the fallbacks only for the `netcoreapp2.1` target:</span></span>

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="build-events"></a><span data-ttu-id="a5194-240">Eventos de compilación</span><span class="sxs-lookup"><span data-stu-id="a5194-240">Build events</span></span>

<span data-ttu-id="a5194-241">La forma en que se especifican los eventos anteriores y posteriores a la compilación en el archivo de proyecto ha cambiado.</span><span class="sxs-lookup"><span data-stu-id="a5194-241">The way that pre-build and post-build events are specified in the project file has changed.</span></span> <span data-ttu-id="a5194-242">No se recomiendan las propiedades PreBuildEvent y PostBuildEvent en el formato de proyecto de estilo SDK, ya que las macros como $(ProjectDir) no se resuelven.</span><span class="sxs-lookup"><span data-stu-id="a5194-242">The properties PreBuildEvent and PostBuildEvent are not recommended in the SDK-style project format, because macros such as $(ProjectDir) are not resolved.</span></span> <span data-ttu-id="a5194-243">Por ejemplo, el código siguiente ya no se admite:</span><span class="sxs-lookup"><span data-stu-id="a5194-243">For example, the following code is no longer supported:</span></span>

```xml
<PropertyGroup>
    <PreBuildEvent>"$(ProjectDir)PreBuildEvent.bat" "$(ProjectDir)..\" "$(ProjectDir)" "$(TargetDir)" />
</PropertyGroup>
```

<span data-ttu-id="a5194-244">En los proyectos de estilo SDK, use un destino de MSBuild denominado `PreBuild` o `PostBuild`, y establezca la propiedad `BeforeTargets` para `PreBuild`, o bien la propiedad `AfterTargets` para `PostBuild`.</span><span class="sxs-lookup"><span data-stu-id="a5194-244">In SDK-style projects, use an MSBuild target named `PreBuild` or `PostBuild` and set the `BeforeTargets` property for `PreBuild` or the `AfterTargets` property for `PostBuild`.</span></span> <span data-ttu-id="a5194-245">Para el ejemplo anterior, use el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="a5194-245">For the preceding example, use the following code:</span></span>

```xml
<Target Name="PreBuild" BeforeTargets="PreBuildEvent">
    <Exec Command="&quot;$(ProjectDir)PreBuildEvent.bat&quot; &quot;$(ProjectDir)..\&quot; &quot;$(ProjectDir)&quot; &quot;$(TargetDir)&quot;" />
</Target>

<Target Name="PostBuild" AfterTargets="PostBuildEvent">
   <Exec Command="echo Output written to $(TargetDir)" />
</Target>
```

> [!NOTE]
><span data-ttu-id="a5194-246">Puede usar cualquier nombre para los destinos de MSBuild, pero el IDE de Visual Studio reconoce los destinos `PreBuild` y `PostBuild`, por lo que se recomienda usar esos nombres para poder editar los comandos en el IDE de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5194-246">You can use any name for the MSBuild targets, but the Visual Studio IDE recognizes `PreBuild` and `PostBuild` targets, so we recommend using those names so that you can edit the commands in the Visual Studio IDE.</span></span>

## <a name="nuget-metadata-properties"></a><span data-ttu-id="a5194-247">Propiedades de metadatos de NuGet</span><span class="sxs-lookup"><span data-stu-id="a5194-247">NuGet metadata properties</span></span>

<span data-ttu-id="a5194-248">Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete NuGet de archivos *project.json* a archivos *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="a5194-248">With the move to MSBuild, we have moved the input metadata that is used when packing a NuGet package from *project.json* to *.csproj* files.</span></span> <span data-ttu-id="a5194-249">Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`.</span><span class="sxs-lookup"><span data-stu-id="a5194-249">The inputs are MSBuild properties so they have to go within a `<PropertyGroup>` group.</span></span> <span data-ttu-id="a5194-250">La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack`, que forma parte del SDK:</span><span class="sxs-lookup"><span data-stu-id="a5194-250">The following is the list of properties that are used as inputs to the packing process when using the `dotnet pack` command or the `Pack` MSBuild target that is part of the SDK:</span></span>

### <a name="ispackable"></a><span data-ttu-id="a5194-251">IsPackable</span><span class="sxs-lookup"><span data-stu-id="a5194-251">IsPackable</span></span>

<span data-ttu-id="a5194-252">Un valor booleano que especifica si se puede empaquetar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-252">A Boolean value that specifies whether the project can be packed.</span></span> <span data-ttu-id="a5194-253">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a5194-253">The default value is `true`.</span></span>

### <a name="packageversion"></a><span data-ttu-id="a5194-254">PackageVersion</span><span class="sxs-lookup"><span data-stu-id="a5194-254">PackageVersion</span></span>

<span data-ttu-id="a5194-255">Especifica la versión que tendrá el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="a5194-255">Specifies the version that the resulting package will have.</span></span> <span data-ttu-id="a5194-256">Acepta todos los formatos de la cadena de versión de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5194-256">Accepts all forms of NuGet version string.</span></span> <span data-ttu-id="a5194-257">El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-257">Default is the value of `$(Version)`, that is, of the property `Version` in the project.</span></span>

### <a name="packageid"></a><span data-ttu-id="a5194-258">PackageId</span><span class="sxs-lookup"><span data-stu-id="a5194-258">PackageId</span></span>

<span data-ttu-id="a5194-259">Especifica el nombre para el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="a5194-259">Specifies the name for the resulting package.</span></span> <span data-ttu-id="a5194-260">Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-260">If not specified, the `pack` operation will default to using the `AssemblyName` or directory name as the name of the package.</span></span>

### <a name="title"></a><span data-ttu-id="a5194-261">Title</span><span class="sxs-lookup"><span data-stu-id="a5194-261">Title</span></span>

<span data-ttu-id="a5194-262">Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5194-262">A human-friendly title of the package, typically used in UI displays as on nuget.org and the Package Manager in Visual Studio.</span></span> <span data-ttu-id="a5194-263">Si no se especifica, se usa el identificador del paquete en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a5194-263">If not specified, the package ID is used instead.</span></span>

### <a name="authors"></a><span data-ttu-id="a5194-264">Authors</span><span class="sxs-lookup"><span data-stu-id="a5194-264">Authors</span></span>

<span data-ttu-id="a5194-265">Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.</span><span class="sxs-lookup"><span data-stu-id="a5194-265">A semicolon-separated list of packages authors, matching the profile names on nuget.org. These are displayed in the NuGet Gallery on nuget.org and are used to cross-reference packages by the same authors.</span></span>

### <a name="packagedescription"></a><span data-ttu-id="a5194-266">PackageDescription</span><span class="sxs-lookup"><span data-stu-id="a5194-266">PackageDescription</span></span>

<span data-ttu-id="a5194-267">Una descripción larga del paquete para su visualización en la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a5194-267">A long description of the package for UI display.</span></span>

### <a name="description"></a><span data-ttu-id="a5194-268">Descripción</span><span class="sxs-lookup"><span data-stu-id="a5194-268">Description</span></span>

<span data-ttu-id="a5194-269">Una descripción larga del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="a5194-269">A long description for the assembly.</span></span> <span data-ttu-id="a5194-270">Si `PackageDescription` no se especifica, esta propiedad también se utiliza como la descripción del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-270">If `PackageDescription` is not specified, then this property is also used as the description of the package.</span></span>

### <a name="copyright"></a><span data-ttu-id="a5194-271">Copyright</span><span class="sxs-lookup"><span data-stu-id="a5194-271">Copyright</span></span>

<span data-ttu-id="a5194-272">Detalles de copyright del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-272">Copyright details for the package.</span></span>

### <a name="packagerequirelicenseacceptance"></a><span data-ttu-id="a5194-273">PackageRequireLicenseAcceptance</span><span class="sxs-lookup"><span data-stu-id="a5194-273">PackageRequireLicenseAcceptance</span></span>

<span data-ttu-id="a5194-274">Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo.</span><span class="sxs-lookup"><span data-stu-id="a5194-274">A Boolean value that specifies whether the client must prompt the consumer to accept the package license before installing the package.</span></span> <span data-ttu-id="a5194-275">De manera predeterminada, es `false`.</span><span class="sxs-lookup"><span data-stu-id="a5194-275">The default is `false`.</span></span>

### <a name="packagelicenseexpression"></a><span data-ttu-id="a5194-276">PackageLicenseExpression</span><span class="sxs-lookup"><span data-stu-id="a5194-276">PackageLicenseExpression</span></span>

<span data-ttu-id="a5194-277">[Identificador de licencia SPDX](https://spdx.org/licenses/) o expresión.</span><span class="sxs-lookup"><span data-stu-id="a5194-277">An [SPDX license identifier](https://spdx.org/licenses/) or expression.</span></span> <span data-ttu-id="a5194-278">Por ejemplo: `Apache-2.0`.</span><span class="sxs-lookup"><span data-stu-id="a5194-278">For example, `Apache-2.0`.</span></span>

<span data-ttu-id="a5194-279">Esta es la lista completa de [identificadores de licencia SPDX](https://spdx.org/licenses/).</span><span class="sxs-lookup"><span data-stu-id="a5194-279">Here is the complete list of [SPDX license identifiers](https://spdx.org/licenses/).</span></span> <span data-ttu-id="a5194-280">NuGet.org acepta solo licencias aprobadas de OSI o FSF cuando se usa la expresión de tipo de licencia.</span><span class="sxs-lookup"><span data-stu-id="a5194-280">NuGet.org accepts only OSI or FSF approved licenses when using license type expression.</span></span>

<span data-ttu-id="a5194-281">La sintaxis exacta de las expresiones de licencia se describe a continuación en [ABNF](https://tools.ietf.org/html/rfc5234).</span><span class="sxs-lookup"><span data-stu-id="a5194-281">The exact syntax of the license expressions is described below in [ABNF](https://tools.ietf.org/html/rfc5234).</span></span>

```abnf
license-id            = <short form license identifier from https://spdx.org/spdx-specification-21-web-version#h.luq9dgcle9mo>

license-exception-id  = <short form license exception identifier from https://spdx.org/spdx-specification-21-web-version#h.ruv3yl8g6czd>

simple-expression = license-id / license-id”+”

compound-expression =  1*1(simple-expression /
                simple-expression "WITH" license-exception-id /
                compound-expression "AND" compound-expression /
                compound-expression "OR" compound-expression ) /
                "(" compound-expression ")" )

license-expression =  1*1(simple-expression / compound-expression / UNLICENSED)
```

> [!NOTE]
> <span data-ttu-id="a5194-282">Solo se puede especificar una de estos elementos cada vez: `PackageLicenseExpression`, `PackageLicenseFile` o `PackageLicenseUrl`.</span><span class="sxs-lookup"><span data-stu-id="a5194-282">Only one of `PackageLicenseExpression`, `PackageLicenseFile` and `PackageLicenseUrl` can be specified at a time.</span></span>

### <a name="packagelicensefile"></a><span data-ttu-id="a5194-283">PackageLicenseFile</span><span class="sxs-lookup"><span data-stu-id="a5194-283">PackageLicenseFile</span></span>

<span data-ttu-id="a5194-284">Ruta de acceso a un archivo de licencia dentro del paquete si usa una licencia que no tiene asignado un identificador SPDX, o se trata de una licencia personalizada (en caso contrario, se prefiere `PackageLicenseExpression`)</span><span class="sxs-lookup"><span data-stu-id="a5194-284">Path to a license file within the package if you are using a license that hasn’t been assigned an SPDX identifier, or it is a custom license (Otherwise `PackageLicenseExpression` is preferred)</span></span>

<span data-ttu-id="a5194-285">Reemplaza `PackageLicenseUrl`, no se puede combinar con `PackageLicenseExpression` y requiere Visual Studio versión 15.9.4 y el SDK de .NET 2.1.502, 2.2.101 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="a5194-285">Replaces `PackageLicenseUrl`, can't be combined with `PackageLicenseExpression`, and requires Visual Studio version 15.9.4 and .NET SDK 2.1.502 or 2.2.101 or newer.</span></span>

<span data-ttu-id="a5194-286">Deberá asegurarse de que el archivo de licencia está empaquetado; para ello, agréguelo explícitamente al proyecto. Ejemplo de uso:</span><span class="sxs-lookup"><span data-stu-id="a5194-286">You will need to ensure the license file is packed by adding it explicitly to the project, example usage:</span></span>

```xml
<PropertyGroup>
  <PackageLicenseFile>LICENSE.txt</PackageLicenseFile>
</PropertyGroup>
<ItemGroup>
  <None Include="licenses\LICENSE.txt" Pack="true" PackagePath="$(PackageLicenseFile)"/>
</ItemGroup>
```

### <a name="packagelicenseurl"></a><span data-ttu-id="a5194-287">PackageLicenseUrl</span><span class="sxs-lookup"><span data-stu-id="a5194-287">PackageLicenseUrl</span></span>

<span data-ttu-id="a5194-288">Una dirección URL a la licencia que se aplica al paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-288">A URL to the license that is applicable to the package.</span></span> <span data-ttu-id="a5194-289">(_en desuso desde Visual Studio 15.9.4, SDK de .NET 2.1.502 y 2.2.101_)</span><span class="sxs-lookup"><span data-stu-id="a5194-289">(_deprecated since Visual Studio 15.9.4, .NET SDK 2.1.502 and 2.2.101_)</span></span>

### <a name="packageiconurl"></a><span data-ttu-id="a5194-290">PackageIconUrl</span><span class="sxs-lookup"><span data-stu-id="a5194-290">PackageIconUrl</span></span>

<span data-ttu-id="a5194-291">Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.</span><span class="sxs-lookup"><span data-stu-id="a5194-291">A URL for a 64x64 image with transparent background to use as the icon for the package in UI display.</span></span>

### <a name="packagereleasenotes"></a><span data-ttu-id="a5194-292">PackageReleaseNotes</span><span class="sxs-lookup"><span data-stu-id="a5194-292">PackageReleaseNotes</span></span>

<span data-ttu-id="a5194-293">Notas de la versión para el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-293">Release notes for the package.</span></span>

### <a name="packagetags"></a><span data-ttu-id="a5194-294">PackageTags</span><span class="sxs-lookup"><span data-stu-id="a5194-294">PackageTags</span></span>

<span data-ttu-id="a5194-295">Una lista de etiquetas delimitada por punto y coma que designa el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-295">A semicolon-delimited list of tags that designates the package.</span></span>

### <a name="packageoutputpath"></a><span data-ttu-id="a5194-296">PackageOutputPath</span><span class="sxs-lookup"><span data-stu-id="a5194-296">PackageOutputPath</span></span>

<span data-ttu-id="a5194-297">Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado.</span><span class="sxs-lookup"><span data-stu-id="a5194-297">Determines the output path in which the packed package will be dropped.</span></span> <span data-ttu-id="a5194-298">El valor predeterminado es `$(OutputPath)`.</span><span class="sxs-lookup"><span data-stu-id="a5194-298">Default is `$(OutputPath)`.</span></span>

### <a name="includesymbols"></a><span data-ttu-id="a5194-299">IncludeSymbols</span><span class="sxs-lookup"><span data-stu-id="a5194-299">IncludeSymbols</span></span>
<span data-ttu-id="a5194-300">Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto.</span><span class="sxs-lookup"><span data-stu-id="a5194-300">This Boolean value indicates whether the package should create an additional symbols package when the project is packed.</span></span> <span data-ttu-id="a5194-301">El formato del paquete de símbolos se controla mediante la propiedad `SymbolPackageFormat`.</span><span class="sxs-lookup"><span data-stu-id="a5194-301">The symbols package's format is controlled by the `SymbolPackageFormat` property.</span></span>

### <a name="symbolpackageformat"></a><span data-ttu-id="a5194-302">SymbolPackageFormat</span><span class="sxs-lookup"><span data-stu-id="a5194-302">SymbolPackageFormat</span></span>
<span data-ttu-id="a5194-303">Especifica el formato del paquete de símbolos.</span><span class="sxs-lookup"><span data-stu-id="a5194-303">Specifies the format of the symbols package.</span></span> <span data-ttu-id="a5194-304">Si es "symbols.nupkg", se crea un paquete de símbolos heredado con una extensión *.symbols.nupkg* que contiene archivos PDB, DLL y otros archivos de salida.</span><span class="sxs-lookup"><span data-stu-id="a5194-304">If "symbols.nupkg", a legacy symbols package will be created with a *.symbols.nupkg* extension containing PDBs, DLLs, and other output files.</span></span> <span data-ttu-id="a5194-305">Si es "snupkg", se crea un paquete de símbolos snupkg que contiene los archivos PDB portátiles.</span><span class="sxs-lookup"><span data-stu-id="a5194-305">If "snupkg", a snupkg symbol package will be created containing the portable PDBs.</span></span> <span data-ttu-id="a5194-306">El valor predeterminado es "symbols.nupkg".</span><span class="sxs-lookup"><span data-stu-id="a5194-306">Default is "symbols.nupkg".</span></span>

### <a name="includesource"></a><span data-ttu-id="a5194-307">IncludeSource</span><span class="sxs-lookup"><span data-stu-id="a5194-307">IncludeSource</span></span>

<span data-ttu-id="a5194-308">Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen.</span><span class="sxs-lookup"><span data-stu-id="a5194-308">This Boolean value indicates whether the pack process should create a source package.</span></span> <span data-ttu-id="a5194-309">El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="a5194-309">The source package contains the library's source code as well as PDB files.</span></span> <span data-ttu-id="a5194-310">Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="a5194-310">Source files are put under the `src/ProjectName` directory in the resulting package file.</span></span>

### <a name="istool"></a><span data-ttu-id="a5194-311">IsTool</span><span class="sxs-lookup"><span data-stu-id="a5194-311">IsTool</span></span>

<span data-ttu-id="a5194-312">Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*.</span><span class="sxs-lookup"><span data-stu-id="a5194-312">Specifies whether all output files are copied to the *tools* folder instead of the *lib* folder.</span></span> <span data-ttu-id="a5194-313">Esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.</span><span class="sxs-lookup"><span data-stu-id="a5194-313">This is different from a `DotNetCliTool`, which is specified by setting the `PackageType` in the *.csproj* file.</span></span>

### <a name="repositoryurl"></a><span data-ttu-id="a5194-314">RepositoryUrl</span><span class="sxs-lookup"><span data-stu-id="a5194-314">RepositoryUrl</span></span>

<span data-ttu-id="a5194-315">Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando.</span><span class="sxs-lookup"><span data-stu-id="a5194-315">Specifies the URL for the repository where the source code for the package resides and/or from which it's being built.</span></span>

### <a name="repositorytype"></a><span data-ttu-id="a5194-316">RepositoryType</span><span class="sxs-lookup"><span data-stu-id="a5194-316">RepositoryType</span></span>

<span data-ttu-id="a5194-317">Especifica el tipo del repositorio.</span><span class="sxs-lookup"><span data-stu-id="a5194-317">Specifies the type of the repository.</span></span> <span data-ttu-id="a5194-318">El valor predeterminado es “git”.</span><span class="sxs-lookup"><span data-stu-id="a5194-318">Default is "git".</span></span>

### <a name="repositorybranch"></a><span data-ttu-id="a5194-319">RepositoryBranch</span><span class="sxs-lookup"><span data-stu-id="a5194-319">RepositoryBranch</span></span>
<span data-ttu-id="a5194-320">Especifica el nombre de la rama de origen en el repositorio.</span><span class="sxs-lookup"><span data-stu-id="a5194-320">Specifies the name of the source branch in the repository.</span></span> <span data-ttu-id="a5194-321">Cuando el proyecto se empaqueta en un paquete NuGet, se agrega a los metadatos del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-321">When the project is packaged in a NuGet package, it's added to the package metadata.</span></span>

### <a name="repositorycommit"></a><span data-ttu-id="a5194-322">RepositoryCommit</span><span class="sxs-lookup"><span data-stu-id="a5194-322">RepositoryCommit</span></span>
<span data-ttu-id="a5194-323">Confirmación o conjunto de cambios opcionales de repositorio para indicar en qué origen se ha compilado el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-323">Optional repository commit or changeset to indicate which source the package was built against.</span></span> <span data-ttu-id="a5194-324">`RepositoryUrl` también se debe especificar para que esta propiedad se incluya.</span><span class="sxs-lookup"><span data-stu-id="a5194-324">`RepositoryUrl` must also be specified for this property to be included.</span></span> <span data-ttu-id="a5194-325">Cuando el proyecto se empaqueta en un paquete NuGet, esta confirmación o conjunto de cambios se agrega a los metadatos del paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-325">When the project is packaged in a NuGet package, this commit or changeset is added to the package metadata.</span></span>

### <a name="nopackageanalysis"></a><span data-ttu-id="a5194-326">NoPackageAnalysis</span><span class="sxs-lookup"><span data-stu-id="a5194-326">NoPackageAnalysis</span></span>

<span data-ttu-id="a5194-327">Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.</span><span class="sxs-lookup"><span data-stu-id="a5194-327">Specifies that pack should not run package analysis after building the package.</span></span>

### <a name="minclientversion"></a><span data-ttu-id="a5194-328">MinClientVersion</span><span class="sxs-lookup"><span data-stu-id="a5194-328">MinClientVersion</span></span>

<span data-ttu-id="a5194-329">Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="a5194-329">Specifies the minimum version of the NuGet client that can install this package, enforced by nuget.exe and the Visual Studio Package Manager.</span></span>

### <a name="includebuildoutput"></a><span data-ttu-id="a5194-330">IncludeBuildOutput</span><span class="sxs-lookup"><span data-stu-id="a5194-330">IncludeBuildOutput</span></span>

<span data-ttu-id="a5194-331">Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.</span><span class="sxs-lookup"><span data-stu-id="a5194-331">This Boolean value specifies whether the build output assemblies should be packed into the *.nupkg* file or not.</span></span>

### <a name="includecontentinpack"></a><span data-ttu-id="a5194-332">IncludeContentInPack</span><span class="sxs-lookup"><span data-stu-id="a5194-332">IncludeContentInPack</span></span>

<span data-ttu-id="a5194-333">Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante.</span><span class="sxs-lookup"><span data-stu-id="a5194-333">This Boolean value specifies whether any items that have a type of `Content` will be included in the resulting package automatically.</span></span> <span data-ttu-id="a5194-334">De manera predeterminada, es `true`.</span><span class="sxs-lookup"><span data-stu-id="a5194-334">The default is `true`.</span></span>

### <a name="buildoutputtargetfolder"></a><span data-ttu-id="a5194-335">BuildOutputTargetFolder</span><span class="sxs-lookup"><span data-stu-id="a5194-335">BuildOutputTargetFolder</span></span>

<span data-ttu-id="a5194-336">Especifica la carpeta en la que se colocarán los ensamblados de salida.</span><span class="sxs-lookup"><span data-stu-id="a5194-336">Specifies the folder where to place the output assemblies.</span></span> <span data-ttu-id="a5194-337">Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.</span><span class="sxs-lookup"><span data-stu-id="a5194-337">The output assemblies (and other output files) are copied into their respective framework folders.</span></span>

### <a name="contenttargetfolders"></a><span data-ttu-id="a5194-338">ContentTargetFolders</span><span class="sxs-lookup"><span data-stu-id="a5194-338">ContentTargetFolders</span></span>

<span data-ttu-id="a5194-339">Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos.</span><span class="sxs-lookup"><span data-stu-id="a5194-339">This property specifies the default location of where all the content files should go if `PackagePath` is not specified for them.</span></span> <span data-ttu-id="a5194-340">El valor predeterminado es “content;contentFiles”.</span><span class="sxs-lookup"><span data-stu-id="a5194-340">The default value is "content;contentFiles".</span></span>

### <a name="nuspecfile"></a><span data-ttu-id="a5194-341">NuspecFile</span><span class="sxs-lookup"><span data-stu-id="a5194-341">NuspecFile</span></span>

<span data-ttu-id="a5194-342">Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado.</span><span class="sxs-lookup"><span data-stu-id="a5194-342">Relative or absolute path to the *.nuspec* file being used for packing.</span></span>

> [!NOTE]
> <span data-ttu-id="a5194-343">Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos.</span><span class="sxs-lookup"><span data-stu-id="a5194-343">If the *.nuspec* file is specified, it's used **exclusively** for packaging information and any information in the projects is not used.</span></span>

### <a name="nuspecbasepath"></a><span data-ttu-id="a5194-344">NuspecBasePath</span><span class="sxs-lookup"><span data-stu-id="a5194-344">NuspecBasePath</span></span>

<span data-ttu-id="a5194-345">Ruta de acceso base para el archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="a5194-345">Base path for the *.nuspec* file.</span></span>

### <a name="nuspecproperties"></a><span data-ttu-id="a5194-346">NuspecProperties</span><span class="sxs-lookup"><span data-stu-id="a5194-346">NuspecProperties</span></span>

<span data-ttu-id="a5194-347">Lista separada por punto y coma de pares clave=valor.</span><span class="sxs-lookup"><span data-stu-id="a5194-347">Semicolon separated list of key=value pairs.</span></span>

## <a name="assemblyinfo-properties"></a><span data-ttu-id="a5194-348">Propiedades de AssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="a5194-348">AssemblyInfo properties</span></span>

<span data-ttu-id="a5194-349">Los [atributos de ensamblado](../../standard/assembly/set-attributes.md) que solían estar presentes en un archivo *AssemblyInfo* ahora se generan automáticamente a partir de las propiedades.</span><span class="sxs-lookup"><span data-stu-id="a5194-349">[Assembly attributes](../../standard/assembly/set-attributes.md) that were typically present in an *AssemblyInfo* file are now automatically generated from properties.</span></span>

### <a name="properties-per-attribute"></a><span data-ttu-id="a5194-350">Propiedades por atributo</span><span class="sxs-lookup"><span data-stu-id="a5194-350">Properties per attribute</span></span>

<span data-ttu-id="a5194-351">Como se muestra en la tabla siguiente, cada atributo tiene una propiedad que controla el contenido y otra que deshabilita su generación:</span><span class="sxs-lookup"><span data-stu-id="a5194-351">As shown in the following table, each attribute has a property that controls its content and another that disables its generation:</span></span>

| <span data-ttu-id="a5194-352">Atributo</span><span class="sxs-lookup"><span data-stu-id="a5194-352">Attribute</span></span>                                                      | <span data-ttu-id="a5194-353">Propiedad.</span><span class="sxs-lookup"><span data-stu-id="a5194-353">Property</span></span>               | <span data-ttu-id="a5194-354">Propiedad que se va a deshabilitar</span><span class="sxs-lookup"><span data-stu-id="a5194-354">Property to disable</span></span>                             |
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

<span data-ttu-id="a5194-355">Notas:</span><span class="sxs-lookup"><span data-stu-id="a5194-355">Notes:</span></span>

- <span data-ttu-id="a5194-356">El comportamiento predeterminado de `AssemblyVersion` y `FileVersion` consiste en adoptar el valor de `$(Version)` sin sufijo.</span><span class="sxs-lookup"><span data-stu-id="a5194-356">`AssemblyVersion` and `FileVersion` default is to take the value of `$(Version)` without suffix.</span></span> <span data-ttu-id="a5194-357">Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="a5194-357">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="a5194-358">El valor predeterminado de `InformationalVersion` es el de `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="a5194-358">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="a5194-359">`InformationalVersion` tiene `$(SourceRevisionId)` anexado si la propiedad está presente.</span><span class="sxs-lookup"><span data-stu-id="a5194-359">`InformationalVersion` has `$(SourceRevisionId)` appended if the property is present.</span></span> <span data-ttu-id="a5194-360">Puede deshabilitarse mediante `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="a5194-360">It can be disabled using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="a5194-361">Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.</span><span class="sxs-lookup"><span data-stu-id="a5194-361">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="a5194-362">`Configuration` se comparte con todos los procesos de compilación y se establece mediante el parámetro `--configuration` de los comandos `dotnet`.</span><span class="sxs-lookup"><span data-stu-id="a5194-362">`Configuration` is shared with all the build process and set via the `--configuration` parameter of `dotnet` commands.</span></span>

### <a name="generateassemblyinfo"></a><span data-ttu-id="a5194-363">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="a5194-363">GenerateAssemblyInfo</span></span>

<span data-ttu-id="a5194-364">Un valor booleano que habilita o deshabilita toda la generación de AssemblyInfo.</span><span class="sxs-lookup"><span data-stu-id="a5194-364">A Boolean that enable or disable all the AssemblyInfo generation.</span></span> <span data-ttu-id="a5194-365">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="a5194-365">The default value is `true`.</span></span>

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="a5194-366">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="a5194-366">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="a5194-367">La ruta de acceso del archivo de información del ensamblado generado.</span><span class="sxs-lookup"><span data-stu-id="a5194-367">The path of the generated assembly info file.</span></span> <span data-ttu-id="a5194-368">De forma predeterminada, se trata de un archivo del directorio `$(IntermediateOutputPath)` (obj).</span><span class="sxs-lookup"><span data-stu-id="a5194-368">Default to a file in the `$(IntermediateOutputPath)` (obj) directory.</span></span>
