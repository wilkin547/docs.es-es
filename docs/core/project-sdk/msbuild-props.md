---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 18f2be734fa10e2fd4977166ab4334332b120a91
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604767"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="b0e49-103">Referencia de MSBuild para proyectos del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="b0e49-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="b0e49-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="b0e49-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e49-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="b0e49-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="b0e49-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="b0e49-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="b0e49-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="b0e49-107">Framework properties</span></span>

- [<span data-ttu-id="b0e49-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="b0e49-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="b0e49-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="b0e49-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="b0e49-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="b0e49-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="b0e49-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="b0e49-111">TargetFramework</span></span>

<span data-ttu-id="b0e49-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="b0e49-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b0e49-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="b0e49-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="b0e49-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="b0e49-115">TargetFrameworks</span></span>

<span data-ttu-id="b0e49-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="b0e49-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="b0e49-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b0e49-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="b0e49-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="b0e49-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="b0e49-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="b0e49-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="b0e49-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="b0e49-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="b0e49-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="b0e49-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="b0e49-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="b0e49-125">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="b0e49-125">Package properties</span></span>

<span data-ttu-id="b0e49-126">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="b0e49-127">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="b0e49-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-items-and-metadata"></a><span data-ttu-id="b0e49-128">Propiedades, elementos y metadatos de publicación</span><span class="sxs-lookup"><span data-stu-id="b0e49-128">Publish properties, items, and metadata</span></span>

- [<span data-ttu-id="b0e49-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="b0e49-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="b0e49-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="b0e49-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="b0e49-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="b0e49-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="b0e49-132">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="b0e49-132">CopyToPublishDirectory</span></span>](#copytopublishdirectory)
- [<span data-ttu-id="b0e49-133">LinkBase</span><span class="sxs-lookup"><span data-stu-id="b0e49-133">LinkBase</span></span>](#linkbase)
- [<span data-ttu-id="b0e49-134">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="b0e49-134">PreserveCompilationContext</span></span>](#preservecompilationcontext)
- [<span data-ttu-id="b0e49-135">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="b0e49-135">PreserveCompilationReferences</span></span>](#preservecompilationreferences)
- [<span data-ttu-id="b0e49-136">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b0e49-136">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="b0e49-137">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="b0e49-137">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="b0e49-138">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="b0e49-138">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="b0e49-139">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="b0e49-139">UseAppHost</span></span>](#useapphost)

### <a name="copytopublishdirectory"></a><span data-ttu-id="b0e49-140">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="b0e49-140">CopyToPublishDirectory</span></span>

<span data-ttu-id="b0e49-141">Los metadatos de `CopyToPublishDirectory` relativos a un elemento de MSBuild controlan cuándo se copia el elemento en el directorio de publicación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-141">The `CopyToPublishDirectory` metadata on an MSBuild item controls when the item is copied to the publish directory.</span></span> <span data-ttu-id="b0e49-142">Los valores permitidos son `PreserveNewest`, que solo copia el elemento si ha cambiado; `Always`, que siempre lo copia; y `Never`, que nunca lo hace.</span><span class="sxs-lookup"><span data-stu-id="b0e49-142">Allowable values are `PreserveNewest`, which only copies the item if it has changed, `Always`, which always copies the item, and `Never`, which never copies the item.</span></span> <span data-ttu-id="b0e49-143">Desde el punto de vista del rendimiento, `PreserveNewest` es preferible porque permite una compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="b0e49-143">From a performance standpoint, `PreserveNewest` is preferable because it enables an incremental build.</span></span>

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a><span data-ttu-id="b0e49-144">LinkBase</span><span class="sxs-lookup"><span data-stu-id="b0e49-144">LinkBase</span></span>

<span data-ttu-id="b0e49-145">En el caso de un elemento situado fuera del directorio del proyecto y sus subdirectorios, el destino de publicación usa los [metadatos de Link](/visualstudio/msbuild/common-msbuild-item-metadata) del elemento para determinar dónde se debe copiar este.</span><span class="sxs-lookup"><span data-stu-id="b0e49-145">For an item that's outside of the project directory and its subdirectories, the publish target uses the item's [Link metadata](/visualstudio/msbuild/common-msbuild-item-metadata) to determine where to copy the item to.</span></span> <span data-ttu-id="b0e49-146">`Link` también determina cómo se muestran los elementos situados fuera del árbol del proyecto en la ventana Explorador de soluciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="b0e49-146">`Link` also determines how items outside of the project tree are displayed in the Solution Explorer window of Visual Studio.</span></span>

<span data-ttu-id="b0e49-147">Si no se especifica `Link` para un elemento situado fuera del cono del proyecto, este tiene `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)` como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b0e49-147">If `Link` is not specified for an item that's outside of the project cone, it defaults to `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)`.</span></span> <span data-ttu-id="b0e49-148">`LinkBase` permite especificar una carpeta base razonable para los elementos situados fuera del cono del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-148">`LinkBase` lets you specify a sensible base folder for items outside of the project cone.</span></span> <span data-ttu-id="b0e49-149">La jerarquía de carpetas de la carpeta base se conserva por medio de `RecursiveDir`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-149">The folder hierarchy under the base folder is preserved via `RecursiveDir`.</span></span> <span data-ttu-id="b0e49-150">Si no se especifica `LinkBase`, se omite de la ruta a `Link`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-150">If `LinkBase` is not specified, it's omitted from the `Link` path.</span></span>

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

<span data-ttu-id="b0e49-151">En la imagen siguiente, se ilustra cómo se muestra globalmente un archivo incluido en el elemento anterior `Include` en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="b0e49-151">The following image shows how a file that's included via the previous item `Include` glob displays in Solution Explorer.</span></span>

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="Elemento con metadatos de LinkBase en el Explorador de soluciones.":::

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="b0e49-153">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="b0e49-153">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="b0e49-154">La propiedad `AppendTargetFrameworkToOutputPath` controla si el [moniker de la plataforma de destino (TFM)](../../standard/frameworks.md) se anexa a la ruta de salida (definida por [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span><span class="sxs-lookup"><span data-stu-id="b0e49-154">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="b0e49-155">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-155">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="b0e49-156">El hecho de establecer `AppendTargetFrameworkToOutputPath` en `false` impide que el TFM se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-156">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="b0e49-157">Sin embargo, sin el TFM en la ruta de salida, es posible que varios artefactos de compilación se sobrescriban entre sí.</span><span class="sxs-lookup"><span data-stu-id="b0e49-157">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="b0e49-158">Por ejemplo, en el caso de una aplicación de .NET 5.0, la ruta de salida cambia de `bin\Debug\net5.0` a `bin\Debug` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0e49-158">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="b0e49-159">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="b0e49-159">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="b0e49-160">La propiedad `AppendRuntimeIdentifierToOutputPath` controla si el [id. del entorno de ejecución (RID)](../rid-catalog.md) se anexa a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-160">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="b0e49-161">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-161">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="b0e49-162">El hecho de establecer `AppendRuntimeIdentifierToOutputPath` en `false` impide que el RID se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-162">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="b0e49-163">Por ejemplo, en el caso de una aplicación de .NET 5.0 y un RID de `win10-x64`, la ruta de salida cambia de `bin\Debug\net5.0\win10-x64` a `bin\Debug\net5.0` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="b0e49-163">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="b0e49-164">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="b0e49-164">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="b0e49-165">La propiedad `CopyLocalLockFileAssemblies` es útil para los proyectos de complementos que tienen dependencias de otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="b0e49-165">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="b0e49-166">Si establece esta propiedad en `true`, todas las dependencias de paquetes NuGet se copian en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-166">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="b0e49-167">Esto significa que puede usar la salida de `dotnet build` para ejecutar el complemento en cualquier equipo.</span><span class="sxs-lookup"><span data-stu-id="b0e49-167">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="b0e49-168">Como alternativa, puede usar `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="b0e49-168">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="b0e49-169">Para obtener más información, vea [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-169">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="preservecompilationcontext"></a><span data-ttu-id="b0e49-170">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="b0e49-170">PreserveCompilationContext</span></span>

<span data-ttu-id="b0e49-171">La propiedad `PreserveCompilationContext` permite a una aplicación creada o publicada compilar más código en tiempo de ejecución con la misma configuración que se utilizó en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-171">The `PreserveCompilationContext` property allows a built or published application to compile more code at run time using the same settings that were used at build time.</span></span> <span data-ttu-id="b0e49-172">Los ensamblados a los que se hace referencia en el tiempo de compilación se copiarán en el subdirectorio *ref* del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-172">The assemblies referenced at build time will be copied into the *ref* subdirectory of the output directory.</span></span> <span data-ttu-id="b0e49-173">Los nombres de los ensamblados de referencia se almacenan en el archivo *.deps.json* de la aplicación junto con las opciones que se pasan al compilador.</span><span class="sxs-lookup"><span data-stu-id="b0e49-173">The names of the reference assemblies are stored in the application's *.deps.json* file along with the options passed to the compiler.</span></span> <span data-ttu-id="b0e49-174">Puede recuperar esta información mediante las propiedades <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> y <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="b0e49-174">You can retrieve this information using the <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> and <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType> properties.</span></span>

<span data-ttu-id="b0e49-175">Esta funcionalidad la usan principalmente MVC de ASP.NET Core y páginas Razor para admitir la compilación en tiempo de ejecución de archivos Razor.</span><span class="sxs-lookup"><span data-stu-id="b0e49-175">This functionality is mostly used internally by ASP.NET Core MVC and Razor pages to support run-time compilation of Razor files.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationContext>true</PreserveCompilationContext>
</PropertyGroup>
```

### <a name="preservecompilationreferences"></a><span data-ttu-id="b0e49-176">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="b0e49-176">PreserveCompilationReferences</span></span>

<span data-ttu-id="b0e49-177">La propiedad `PreserveCompilationReferences` es similar a la propiedad [PreserveCompilationContext](#preservecompilationcontext), salvo que solo copia los ensamblados a los que se hace referencia en el directorio de publicación, sin el archivo *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-177">The `PreserveCompilationReferences` property is similar to the [PreserveCompilationContext](#preservecompilationcontext) property, except that it only copies the referenced assemblies to the publish directory, and not the *.deps.json* file.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationReferences>true</PreserveCompilationReferences>
</PropertyGroup>
```

<span data-ttu-id="b0e49-178">Para obtener más información, consulte las [propiedades del SDK de Razor](/aspnet/core/razor-pages/sdk#properties).</span><span class="sxs-lookup"><span data-stu-id="b0e49-178">For more information, see [Razor SDK properties](/aspnet/core/razor-pages/sdk#properties).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="b0e49-179">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="b0e49-179">RuntimeIdentifier</span></span>

<span data-ttu-id="b0e49-180">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-180">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b0e49-181">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="b0e49-181">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="b0e49-182">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="b0e49-182">RuntimeIdentifiers</span></span>

<span data-ttu-id="b0e49-183">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-183">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="b0e49-184">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b0e49-184">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="b0e49-185">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="b0e49-185">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="b0e49-186">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b0e49-186">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="b0e49-187">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="b0e49-187">TrimmerRootAssembly</span></span>

<span data-ttu-id="b0e49-188">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b0e49-188">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="b0e49-189">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b0e49-189">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="b0e49-190">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="b0e49-190">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="b0e49-191">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-191">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="b0e49-192">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="b0e49-192">UseAppHost</span></span>

<span data-ttu-id="b0e49-193">La propiedad `UseAppHost` controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-193">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="b0e49-194">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="b0e49-194">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="b0e49-195">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0e49-195">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="b0e49-196">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="b0e49-196">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="b0e49-197">Para más información sobre la implementación, consulte [Implementación de aplicaciones .NET](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-197">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="b0e49-198">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="b0e49-198">Compile properties</span></span>

- [<span data-ttu-id="b0e49-199">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="b0e49-199">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="b0e49-200">LangVersion</span><span class="sxs-lookup"><span data-stu-id="b0e49-200">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="b0e49-201">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="b0e49-201">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="b0e49-202">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-202">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="b0e49-203">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-203">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="b0e49-204">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-204">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="b0e49-205">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-205">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="b0e49-206">De forma predeterminada, en un nuevo proyecto de .NET, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-206">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="b0e49-207">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-207">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="b0e49-208">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-208">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="b0e49-209">LangVersion</span><span class="sxs-lookup"><span data-stu-id="b0e49-209">LangVersion</span></span>

<span data-ttu-id="b0e49-210">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-210">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="b0e49-211">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-211">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="b0e49-212">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="b0e49-212">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="b0e49-213">Propiedades de inclusión de elementos predeterminados</span><span class="sxs-lookup"><span data-stu-id="b0e49-213">Default item inclusion properties</span></span>

- [<span data-ttu-id="b0e49-214">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="b0e49-214">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="b0e49-215">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="b0e49-215">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="b0e49-216">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-216">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="b0e49-217">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-217">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="b0e49-218">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-218">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="b0e49-219">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-219">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="b0e49-220">Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="b0e49-220">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="b0e49-221">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="b0e49-221">DefaultItemExcludes</span></span>

<span data-ttu-id="b0e49-222">Use la propiedad `DefaultItemExcludes` para definir patrones globales para archivos y carpetas que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-222">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="b0e49-223">De forma predeterminada, las carpetas *./bin* y *./obj* se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="b0e49-223">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="b0e49-224">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="b0e49-224">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="b0e49-225">Use la propiedad `DefaultExcludesInProjectFolder` para definir patrones globales para archivos y carpetas de la carpeta del proyecto que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-225">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="b0e49-226">De forma predeterminada, las carpetas que empiezan por un punto (`.`), como *.git* y *.vs*, se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="b0e49-226">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="b0e49-227">Esta propiedad es muy similar a otra, `DefaultItemExcludes`, salvo por el hecho de que esta solo tiene en cuenta los archivos y las carpetas de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-227">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="b0e49-228">En el caso de que un patrón global pretenda, de forma no intencionada, relacionar elementos de fuera de la carpeta del proyecto con una ruta de acceso relativa, use la propiedad `DefaultExcludesInProjectFolder`, en lugar de `DefaultItemExcludes`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-228">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="b0e49-229">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-229">EnableDefaultItems</span></span>

<span data-ttu-id="b0e49-230">La propiedad `EnableDefaultItems` controla si los elementos de compilación, los elementos de los recursos incrustados y los elementos `None` se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="b0e49-230">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="b0e49-231">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-231">The default value is `true`.</span></span> <span data-ttu-id="b0e49-232">Establezca la propiedad `EnableDefaultItems` en `false` para deshabilitar toda inclusión de archivos implícita.</span><span class="sxs-lookup"><span data-stu-id="b0e49-232">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="b0e49-233">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-233">EnableDefaultCompileItems</span></span>

<span data-ttu-id="b0e49-234">La propiedad `EnableDefaultCompileItems` controla si los elementos de compilación se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="b0e49-234">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="b0e49-235">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-235">The default value is `true`.</span></span> <span data-ttu-id="b0e49-236">Establezca la propiedad `EnableDefaultCompileItems` en `false` para deshabilitar la inclusión implícita de los archivos \*.cs, así como la de otras extensiones de nombres de archivos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-236">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="b0e49-237">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-237">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="b0e49-238">La propiedad `EnableDefaultEmbeddedResourceItems` controla si los elementos de los recursos incrustados se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="b0e49-238">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="b0e49-239">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-239">The default value is `true`.</span></span> <span data-ttu-id="b0e49-240">Establezca la propiedad `EnableDefaultEmbeddedResourceItems` en `false` para deshabilitar la inclusión implícita de los archivos de los recursos incrustados.</span><span class="sxs-lookup"><span data-stu-id="b0e49-240">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="b0e49-241">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="b0e49-241">EnableDefaultNoneItems</span></span>

<span data-ttu-id="b0e49-242">La propiedad `EnableDefaultNoneItems` controla si los elementos `None` (archivos que no tienen ningún rol en el proceso de compilación) se incluyen implícitamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-242">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="b0e49-243">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-243">The default value is `true`.</span></span> <span data-ttu-id="b0e49-244">Establezca la propiedad `EnableDefaultNoneItems` en `false` para deshabilitar la inclusión implícita de elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-244">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="b0e49-245">Propiedades de análisis de código</span><span class="sxs-lookup"><span data-stu-id="b0e49-245">Code analysis properties</span></span>

- [<span data-ttu-id="b0e49-246">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="b0e49-246">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="b0e49-247">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="b0e49-247">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="b0e49-248">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="b0e49-248">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="b0e49-249">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="b0e49-249">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="b0e49-250">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="b0e49-250">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="b0e49-251">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="b0e49-251">AnalysisLevel</span></span>

<span data-ttu-id="b0e49-252">La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="b0e49-252">The `AnalysisLevel` property lets you specify a code-analysis level.</span></span> <span data-ttu-id="b0e49-253">Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-253">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span>

<span data-ttu-id="b0e49-254">Valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="b0e49-254">Default value:</span></span>

- <span data-ttu-id="b0e49-255">Si el proyecto tiene como destino .NET 5.0 o posterior, o si ha agregado la propiedad [AnalysisMode](#analysismode), el valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-255">If your project targets .NET 5.0 or later, or if you've added the [AnalysisMode](#analysismode) property, the default value is `latest`.</span></span>
- <span data-ttu-id="b0e49-256">De lo contrario, se omite esta propiedad, a menos que se agregue explícitamente al archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-256">Otherwise, this property is omitted unless you explicitly add it to the project file.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="b0e49-257">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-257">The following table shows the available options.</span></span>

| <span data-ttu-id="b0e49-258">Value</span><span class="sxs-lookup"><span data-stu-id="b0e49-258">Value</span></span> | <span data-ttu-id="b0e49-259">Significado</span><span class="sxs-lookup"><span data-stu-id="b0e49-259">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="b0e49-260">Se usan los analizadores de código que se han publicado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="b0e49-260">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="b0e49-261">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="b0e49-261">This is the default.</span></span> |
| `preview` | <span data-ttu-id="b0e49-262">Se usan los analizadores de código más recientes, incluso si están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="b0e49-262">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="b0e49-263">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-263">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="b0e49-264">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-264">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

> [!NOTE]
> <span data-ttu-id="b0e49-265">Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.</span><span class="sxs-lookup"><span data-stu-id="b0e49-265">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="analysismode"></a><span data-ttu-id="b0e49-266">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="b0e49-266">AnalysisMode</span></span>

<span data-ttu-id="b0e49-267">A partir de .NET 5.0, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-267">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="b0e49-268">De forma predeterminada, solo [algunas reglas están habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-268">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="b0e49-269">La propiedad `AnalysisMode` le permite personalizar el conjunto de reglas que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b0e49-269">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="b0e49-270">Puede cambiar a un modo de análisis más agresivo (exclusión) o a uno más conservador (inclusión).</span><span class="sxs-lookup"><span data-stu-id="b0e49-270">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="b0e49-271">Por ejemplo, si quiere habilitar todas las reglas de forma predeterminada como advertencias de compilación, establezca el valor en `AllEnabledByDefault`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-271">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="b0e49-272">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-272">The following table shows the available options.</span></span>

| <span data-ttu-id="b0e49-273">Value</span><span class="sxs-lookup"><span data-stu-id="b0e49-273">Value</span></span> | <span data-ttu-id="b0e49-274">Significado</span><span class="sxs-lookup"><span data-stu-id="b0e49-274">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="b0e49-275">Modo predeterminado, en el que ciertas reglas están habilitadas como advertencias de compilación, otras están habilitadas como sugerencias del IDE de Visual Studio y el resto están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="b0e49-275">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="b0e49-276">Modo agresivo o de exclusión, en el que todas las reglas están habilitadas de forma predeterminada como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-276">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="b0e49-277">Puede [excluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.</span><span class="sxs-lookup"><span data-stu-id="b0e49-277">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="b0e49-278">Modo conservador o de inclusión, en el que todas las reglas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b0e49-278">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="b0e49-279">Puede [incluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="b0e49-279">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

> [!NOTE]
> <span data-ttu-id="b0e49-280">Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.</span><span class="sxs-lookup"><span data-stu-id="b0e49-280">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="b0e49-281">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="b0e49-281">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="b0e49-282">La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de calidad del código (CAxxxx) se deben tratar como advertencias e interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-282">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="b0e49-283">Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) también se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="b0e49-283">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="b0e49-284">Si no quiere que las advertencias de análisis de calidad del código se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-284">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="b0e49-285">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="b0e49-285">EnableNETAnalyzers</span></span>

<span data-ttu-id="b0e49-286">De forma predeterminada, el [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="b0e49-286">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="b0e49-287">Puede habilitar el análisis de código de .NET para los proyectos de estilo SDK que tienen como destino versiones anteriores de .NET si establece la propiedad `EnableNETAnalyzers` en `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-287">You can enable .NET code analysis for SDK-style projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="b0e49-288">Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-288">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="b0e49-289">Esta propiedad se aplica específicamente a los analizadores integrados en el SDK de .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="b0e49-289">This property applies specifically to the built-in analyzers in the .NET 5+ SDK.</span></span> <span data-ttu-id="b0e49-290">No se debe usar cuando se instala un paquete NuGet de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="b0e49-290">It should not be used when you install a NuGet code analysis package.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="b0e49-291">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="b0e49-291">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="b0e49-292">En la actualidad, esta característica es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.</span><span class="sxs-lookup"><span data-stu-id="b0e49-292">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="b0e49-293">El [análisis del estilo del código de .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) está deshabilitado de forma predeterminada en la compilación para todos los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="b0e49-293">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="b0e49-294">Puede habilitar el análisis del estilo del código para los proyectos de .NET estableciendo la propiedad `EnforceCodeStyleInBuild` en `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-294">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="b0e49-295">Todas las reglas de estilo del código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) como advertencias o errores se ejecutarán en la compilación y notificarán infracciones.</span><span class="sxs-lookup"><span data-stu-id="b0e49-295">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="b0e49-296">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="b0e49-296">Run-time configuration properties</span></span>

<span data-ttu-id="b0e49-297">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-297">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="b0e49-298">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-298">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="b0e49-299">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-299">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="b0e49-300">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="b0e49-300">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="b0e49-301">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-301">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="b0e49-302">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-302">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="b0e49-303">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b0e49-303">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="b0e49-304">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="b0e49-304">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="b0e49-305">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="b0e49-305">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="b0e49-306">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="b0e49-306">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="b0e49-307">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="b0e49-307">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="b0e49-308">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-308">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="b0e49-309">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-309">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="b0e49-310">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="b0e49-310">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="b0e49-311">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="b0e49-311">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="b0e49-312">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="b0e49-312">InvariantGlobalization</span></span>

<span data-ttu-id="b0e49-313">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="b0e49-313">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="b0e49-314">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="b0e49-314">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="b0e49-315">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="b0e49-315">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="b0e49-316">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-316">RetainVMGarbageCollection</span></span>

<span data-ttu-id="b0e49-317">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-317">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="b0e49-318">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="b0e49-318">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="b0e49-319">Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="b0e49-319">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="b0e49-320">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="b0e49-320">ServerGarbageCollection</span></span>

<span data-ttu-id="b0e49-321">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-321">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="b0e49-322">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="b0e49-322">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="b0e49-323">Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="b0e49-323">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="b0e49-324">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="b0e49-324">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="b0e49-325">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0e49-325">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="b0e49-326">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="b0e49-326">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="b0e49-327">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="b0e49-327">ThreadPoolMinThreads</span></span>

<span data-ttu-id="b0e49-328">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0e49-328">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="b0e49-329">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="b0e49-329">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="b0e49-330">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="b0e49-330">TieredCompilation</span></span>

<span data-ttu-id="b0e49-331">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="b0e49-331">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="b0e49-332">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-332">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="b0e49-333">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="b0e49-333">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="b0e49-334">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="b0e49-334">TieredCompilationQuickJit</span></span>

<span data-ttu-id="b0e49-335">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="b0e49-335">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="b0e49-336">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="b0e49-336">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="b0e49-337">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="b0e49-337">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="b0e49-338">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="b0e49-338">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="b0e49-339">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-339">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="b0e49-340">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="b0e49-340">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="b0e49-341">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="b0e49-341">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="b0e49-342">Referencia de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="b0e49-342">Reference properties and items</span></span>

- [<span data-ttu-id="b0e49-343">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b0e49-343">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="b0e49-344">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="b0e49-344">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="b0e49-345">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b0e49-345">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="b0e49-346">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="b0e49-346">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="b0e49-347">Referencia</span><span class="sxs-lookup"><span data-stu-id="b0e49-347">Reference</span></span>](#reference)
- [<span data-ttu-id="b0e49-348">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="b0e49-348">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="b0e49-349">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="b0e49-349">AssetTargetFallback</span></span>

<span data-ttu-id="b0e49-350">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="b0e49-350">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="b0e49-351">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-351">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="b0e49-352">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-352">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span> <span data-ttu-id="b0e49-353">Esta propiedad reemplaza la propiedad en desuso `PackageTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-353">This property replaces the deprecated property `PackageTargetFallback`.</span></span>

<span data-ttu-id="b0e49-354">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="b0e49-354">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="b0e49-355">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="b0e49-355">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="b0e49-356">La propiedad `DisableImplicitFrameworkReferences` controla los elementos `FrameworkReference` implícitos cuando el destino es .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b0e49-356">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="b0e49-357">Cuando el destino es .NET Core 2.1 o .NET Standard 2.0 y versiones anteriores, controla los elementos [PackageReference](#packagereference) implícitos en los paquetes de un metapaquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-357">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="b0e49-358">(Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes). Esta propiedad también controla las referencias implícitas como `System` y `System.Core` cuando el destino es .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="b0e49-358">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="b0e49-359">Establezca esta propiedad en `true` para deshabilitar los elementos `FrameworkReference` o [PackageReference](#packagereference) implícitos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-359">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="b0e49-360">Si establece esta propiedad en `true`, puede agregar referencias explícitas solo a las plataformas o paquetes que necesite.</span><span class="sxs-lookup"><span data-stu-id="b0e49-360">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="b0e49-361">PackageReference</span><span class="sxs-lookup"><span data-stu-id="b0e49-361">PackageReference</span></span>

<span data-ttu-id="b0e49-362">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="b0e49-362">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="b0e49-363">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-363">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="b0e49-364">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="b0e49-364">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="b0e49-365">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="b0e49-365">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="b0e49-366">También puede agregar [atributos de recurso](#asset-attributes) a una referencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-366">You can also add [asset attributes](#asset-attributes) to a package reference.</span></span>

<span data-ttu-id="b0e49-367">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="b0e49-367">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="b0e49-368">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="b0e49-368">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

#### <a name="asset-attributes"></a><span data-ttu-id="b0e49-369">Atributos de recurso</span><span class="sxs-lookup"><span data-stu-id="b0e49-369">Asset attributes</span></span>

<span data-ttu-id="b0e49-370">Los metadatos de `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` se pueden agregar a una referencia de paquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-370">The `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets` metadata can be added to a package reference.</span></span>

| <span data-ttu-id="b0e49-371">Atributo</span><span class="sxs-lookup"><span data-stu-id="b0e49-371">Attribute</span></span> | <span data-ttu-id="b0e49-372">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0e49-372">Description</span></span> |
| - | - |
| `IncludeAssets` | <span data-ttu-id="b0e49-373">Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="b0e49-373">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed.</span></span> <span data-ttu-id="b0e49-374">De forma predeterminada, se incluyen todos los recursos del paquete.</span><span class="sxs-lookup"><span data-stu-id="b0e49-374">By default, all package assets are included.</span></span> |
| `ExcludeAssets`| <span data-ttu-id="b0e49-375">Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` no se deben consumir.</span><span class="sxs-lookup"><span data-stu-id="b0e49-375">Specifies which assets belonging to the package specified by `<PackageReference>` should not be consumed.</span></span> |
| `PrivateAssets` | <span data-ttu-id="b0e49-376">Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` se deben consumir, pero no pasar al proyecto siguiente.</span><span class="sxs-lookup"><span data-stu-id="b0e49-376">Specifies which assets belonging to the package specified by `<PackageReference>` should be consumed but not flow to the next project.</span></span> <span data-ttu-id="b0e49-377">Cuando este atributo no está presente, los recursos `Analyzers`, `Build` y `ContentFiles` son privados de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="b0e49-377">The `Analyzers`, `Build`, and `ContentFiles` assets are private by default when this attribute is not present.</span></span> |

<span data-ttu-id="b0e49-378">Estos atributos pueden contener uno o varios de los siguientes elementos, separados por punto y coma (`;`), si aparece más de uno:</span><span class="sxs-lookup"><span data-stu-id="b0e49-378">These attributes can contain one or more of the following items, separated by a semicolon `;` if more than one is listed:</span></span>

- <span data-ttu-id="b0e49-379">`Compile`: el contenido de la carpeta *lib* está disponible para compilación.</span><span class="sxs-lookup"><span data-stu-id="b0e49-379">`Compile` – the contents of the *lib* folder are available to compile against.</span></span>
- <span data-ttu-id="b0e49-380">`Runtime`: el contenido de la carpeta *runtime* está distribuido.</span><span class="sxs-lookup"><span data-stu-id="b0e49-380">`Runtime` – the contents of the *runtime* folder are distributed.</span></span>
- <span data-ttu-id="b0e49-381">`ContentFiles`: se usa el contenido de la carpeta *contentfiles*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-381">`ContentFiles` – the contents of the *contentfiles* folder are used.</span></span>
- <span data-ttu-id="b0e49-382">`Build`: se usan los archivos props/targets de la carpeta *build*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-382">`Build` – the props/targets in the *build* folder are used.</span></span>
- <span data-ttu-id="b0e49-383">`Native`: el contenido de recursos nativos se copia en la carpeta *output* en runtime.</span><span class="sxs-lookup"><span data-stu-id="b0e49-383">`Native` – the contents from native assets are copied to the *output* folder for runtime.</span></span>
- <span data-ttu-id="b0e49-384">`Analyzers`: se usan los analizadores.</span><span class="sxs-lookup"><span data-stu-id="b0e49-384">`Analyzers` – the analyzers are used.</span></span>

<span data-ttu-id="b0e49-385">Como alternativa, el atributo puede contener:</span><span class="sxs-lookup"><span data-stu-id="b0e49-385">Alternatively, the attribute can contain:</span></span>

- <span data-ttu-id="b0e49-386">`None`: no se usa ninguno de los recursos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-386">`None` – none of the assets are used.</span></span>
- <span data-ttu-id="b0e49-387">`All`: se usan todos los recursos.</span><span class="sxs-lookup"><span data-stu-id="b0e49-387">`All` – all assets are used.</span></span>

### <a name="projectreference"></a><span data-ttu-id="b0e49-388">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="b0e49-388">ProjectReference</span></span>

<span data-ttu-id="b0e49-389">El elemento `ProjectReference` define una referencia a otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-389">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="b0e49-390">El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-390">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="b0e49-391">El atributo `Include` especifica la ruta de acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-391">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="b0e49-392">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-392">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="b0e49-393">El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-393">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="b0e49-394">Referencia</span><span class="sxs-lookup"><span data-stu-id="b0e49-394">Reference</span></span>

<span data-ttu-id="b0e49-395">El elemento `Reference` define una referencia a un archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b0e49-395">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="b0e49-396">El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="b0e49-396">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="b0e49-397">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="b0e49-397">Restore-related properties</span></span>

<span data-ttu-id="b0e49-398">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="b0e49-398">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="b0e49-399">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-399">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="b0e49-400">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="b0e49-400">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="b0e49-401">Propiedades de Run</span><span class="sxs-lookup"><span data-stu-id="b0e49-401">Run properties</span></span>

<span data-ttu-id="b0e49-402">Las siguientes propiedades se usan para iniciar una aplicación con el comando [`dotnet run`](../tools/dotnet-run.md):</span><span class="sxs-lookup"><span data-stu-id="b0e49-402">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="b0e49-403">RunArguments</span><span class="sxs-lookup"><span data-stu-id="b0e49-403">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="b0e49-404">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="b0e49-404">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="b0e49-405">RunArguments</span><span class="sxs-lookup"><span data-stu-id="b0e49-405">RunArguments</span></span>

<span data-ttu-id="b0e49-406">La propiedad `RunArguments` define los argumentos que se pasan a la aplicación cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="b0e49-406">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="b0e49-407">Puede especificar los argumentos adicionales que se pasarán a la aplicación mediante la opción [`--` para `dotnet run`](../tools/dotnet-run.md#options).</span><span class="sxs-lookup"><span data-stu-id="b0e49-407">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="b0e49-408">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="b0e49-408">RunWorkingDirectory</span></span>

<span data-ttu-id="b0e49-409">La propiedad `RunWorkingDirectory` define el directorio de trabajo en el que se iniciará el proceso.</span><span class="sxs-lookup"><span data-stu-id="b0e49-409">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="b0e49-410">Puede ser una ruta de acceso absoluta o relativa al directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="b0e49-410">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="b0e49-411">Si no se especifica un directorio, se usa `OutDir` como directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="b0e49-411">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="b0e49-412">Propiedades de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b0e49-412">Hosting properties</span></span>

- [<span data-ttu-id="b0e49-413">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="b0e49-413">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="b0e49-414">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="b0e49-414">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="b0e49-415">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="b0e49-415">EnableComHosting</span></span>

<span data-ttu-id="b0e49-416">La propiedad `EnableComHosting` indica que un ensamblado proporciona un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="b0e49-416">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="b0e49-417">Al establecer `EnableComHosting` en `true` también implica que [EnableDynamicLoading](#enabledynamicloading) es `true`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-417">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="b0e49-418">Para obtener más información, vea [Exposición de componentes de .NET en COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-418">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="b0e49-419">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="b0e49-419">EnableDynamicLoading</span></span>

<span data-ttu-id="b0e49-420">La propiedad `EnableDynamicLoading` indica que un ensamblado es un componente cargado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="b0e49-420">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="b0e49-421">El componente podría ser una [biblioteca de COM](/windows/win32/com/the-component-object-model) o una biblioteca que no es de COM que se puede [usar desde un host nativo](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="b0e49-421">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="b0e49-422">Establecer esta propiedad en `true` tiene los efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="b0e49-422">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="b0e49-423">Se genera un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="b0e49-423">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="b0e49-424">La [puesta al día](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) se establece en `LatestMinor`.</span><span class="sxs-lookup"><span data-stu-id="b0e49-424">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="b0e49-425">Las referencias de NuGet se copian localmente.</span><span class="sxs-lookup"><span data-stu-id="b0e49-425">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="b0e49-426">Vea también</span><span class="sxs-lookup"><span data-stu-id="b0e49-426">See also</span></span>

- [<span data-ttu-id="b0e49-427">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="b0e49-427">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="b0e49-428">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="b0e49-428">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="b0e49-429">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="b0e49-429">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="b0e49-430">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="b0e49-430">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="b0e49-431">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="b0e49-431">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
