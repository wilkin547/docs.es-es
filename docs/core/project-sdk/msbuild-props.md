---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: e7deb8c32fd01452524122e41f758ab037020ee4
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970712"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="397fe-103">Referencia de MSBuild para proyectos del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="397fe-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="397fe-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="397fe-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="397fe-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="397fe-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="397fe-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="397fe-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="397fe-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="397fe-107">Framework properties</span></span>

- [<span data-ttu-id="397fe-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="397fe-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="397fe-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="397fe-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="397fe-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="397fe-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="397fe-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="397fe-111">TargetFramework</span></span>

<span data-ttu-id="397fe-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="397fe-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="397fe-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="397fe-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="397fe-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="397fe-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="397fe-115">TargetFrameworks</span></span>

<span data-ttu-id="397fe-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="397fe-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="397fe-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="397fe-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="397fe-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="397fe-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="397fe-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="397fe-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="397fe-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="397fe-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="397fe-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="397fe-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="397fe-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="397fe-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="397fe-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="397fe-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="397fe-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="397fe-125">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="397fe-125">Package properties</span></span>

<span data-ttu-id="397fe-126">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="397fe-127">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="397fe-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="397fe-128">Publicación de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="397fe-128">Publish properties and items</span></span>

- [<span data-ttu-id="397fe-129">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="397fe-129">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="397fe-130">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="397fe-130">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="397fe-131">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="397fe-131">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="397fe-132">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="397fe-132">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="397fe-133">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="397fe-133">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="397fe-134">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="397fe-134">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="397fe-135">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="397fe-135">UseAppHost</span></span>](#useapphost)

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="397fe-136">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="397fe-136">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="397fe-137">La propiedad `AppendTargetFrameworkToOutputPath` controla si el [moniker de la plataforma de destino (TFM)](../../standard/frameworks.md) se anexa a la ruta de salida (definida por [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span><span class="sxs-lookup"><span data-stu-id="397fe-137">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="397fe-138">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-138">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="397fe-139">El hecho de establecer `AppendTargetFrameworkToOutputPath` en `false` impide que el TFM se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-139">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="397fe-140">Sin embargo, sin el TFM en la ruta de salida, es posible que varios artefactos de compilación se sobrescriban entre sí.</span><span class="sxs-lookup"><span data-stu-id="397fe-140">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="397fe-141">Por ejemplo, en el caso de una aplicación de .NET 5.0, la ruta de salida cambia de `bin\Debug\net5.0` a `bin\Debug` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="397fe-141">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="397fe-142">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="397fe-142">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="397fe-143">La propiedad `AppendRuntimeIdentifierToOutputPath` controla si el [id. del entorno de ejecución (RID)](../rid-catalog.md) se anexa a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-143">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="397fe-144">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-144">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="397fe-145">El hecho de establecer `AppendRuntimeIdentifierToOutputPath` en `false` impide que el RID se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-145">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="397fe-146">Por ejemplo, en el caso de una aplicación de .NET 5.0 y un RID de `win10-x64`, la ruta de salida cambia de `bin\Debug\net5.0\win10-x64` a `bin\Debug\net5.0` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="397fe-146">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="397fe-147">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="397fe-147">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="397fe-148">La propiedad `CopyLocalLockFileAssemblies` es útil para los proyectos de complementos que tienen dependencias de otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="397fe-148">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="397fe-149">Si establece esta propiedad en `true`, todas las dependencias de paquetes NuGet se copian en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="397fe-149">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="397fe-150">Esto significa que puede usar la salida de `dotnet build` para ejecutar el complemento en cualquier equipo.</span><span class="sxs-lookup"><span data-stu-id="397fe-150">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="397fe-151">Como alternativa, puede usar `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="397fe-151">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="397fe-152">Para obtener más información, vea [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-152">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="397fe-153">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="397fe-153">RuntimeIdentifier</span></span>

<span data-ttu-id="397fe-154">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-154">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="397fe-155">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="397fe-155">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="397fe-156">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="397fe-156">RuntimeIdentifiers</span></span>

<span data-ttu-id="397fe-157">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-157">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="397fe-158">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="397fe-158">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="397fe-159">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="397fe-159">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="397fe-160">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="397fe-160">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="397fe-161">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="397fe-161">TrimmerRootAssembly</span></span>

<span data-ttu-id="397fe-162">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="397fe-162">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="397fe-163">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="397fe-163">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="397fe-164">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="397fe-164">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="397fe-165">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="397fe-165">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="397fe-166">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="397fe-166">UseAppHost</span></span>

<span data-ttu-id="397fe-167">La propiedad `UseAppHost` controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="397fe-167">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="397fe-168">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="397fe-168">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="397fe-169">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="397fe-169">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="397fe-170">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="397fe-170">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="397fe-171">Para más información sobre la implementación, consulte [Implementación de aplicaciones .NET](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-171">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="397fe-172">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="397fe-172">Compile properties</span></span>

- [<span data-ttu-id="397fe-173">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="397fe-173">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="397fe-174">LangVersion</span><span class="sxs-lookup"><span data-stu-id="397fe-174">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="397fe-175">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="397fe-175">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="397fe-176">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="397fe-176">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="397fe-177">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="397fe-177">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="397fe-178">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="397fe-178">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="397fe-179">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="397fe-179">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="397fe-180">De forma predeterminada, en un nuevo proyecto de .NET, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-180">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="397fe-181">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="397fe-181">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="397fe-182">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-182">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="397fe-183">LangVersion</span><span class="sxs-lookup"><span data-stu-id="397fe-183">LangVersion</span></span>

<span data-ttu-id="397fe-184">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="397fe-184">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="397fe-185">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="397fe-185">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="397fe-186">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="397fe-186">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="397fe-187">Propiedades de inclusión de elementos predeterminados</span><span class="sxs-lookup"><span data-stu-id="397fe-187">Default item inclusion properties</span></span>

- [<span data-ttu-id="397fe-188">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="397fe-188">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="397fe-189">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="397fe-189">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="397fe-190">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="397fe-190">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="397fe-191">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="397fe-191">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="397fe-192">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="397fe-192">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="397fe-193">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="397fe-193">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="397fe-194">Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="397fe-194">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="397fe-195">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="397fe-195">DefaultItemExcludes</span></span>

<span data-ttu-id="397fe-196">Use la propiedad `DefaultItemExcludes` para definir patrones globales para archivos y carpetas que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="397fe-196">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="397fe-197">De forma predeterminada, las carpetas *./bin* y *./obj* se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="397fe-197">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="397fe-198">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="397fe-198">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="397fe-199">Use la propiedad `DefaultExcludesInProjectFolder` para definir patrones globales para archivos y carpetas de la carpeta del proyecto que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="397fe-199">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="397fe-200">De forma predeterminada, las carpetas que empiezan por un punto (`.`), como *.git* y *.vs*, se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="397fe-200">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="397fe-201">Esta propiedad es muy similar a otra, `DefaultItemExcludes`, salvo por el hecho de que esta solo tiene en cuenta los archivos y las carpetas de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-201">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="397fe-202">En el caso de que un patrón global pretenda, de forma no intencionada, relacionar elementos de fuera de la carpeta del proyecto con una ruta de acceso relativa, use la propiedad `DefaultExcludesInProjectFolder`, en lugar de `DefaultItemExcludes`.</span><span class="sxs-lookup"><span data-stu-id="397fe-202">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="397fe-203">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="397fe-203">EnableDefaultItems</span></span>

<span data-ttu-id="397fe-204">La propiedad `EnableDefaultItems` controla si los elementos de compilación, los elementos de los recursos incrustados y los elementos `None` se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="397fe-204">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="397fe-205">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-205">The default value is `true`.</span></span> <span data-ttu-id="397fe-206">Establezca la propiedad `EnableDefaultItems` en `false` para deshabilitar toda inclusión de archivos implícita.</span><span class="sxs-lookup"><span data-stu-id="397fe-206">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="397fe-207">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="397fe-207">EnableDefaultCompileItems</span></span>

<span data-ttu-id="397fe-208">La propiedad `EnableDefaultCompileItems` controla si los elementos de compilación se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="397fe-208">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="397fe-209">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-209">The default value is `true`.</span></span> <span data-ttu-id="397fe-210">Establezca la propiedad `EnableDefaultCompileItems` en `false` para deshabilitar la inclusión implícita de los archivos \*.cs, así como la de otras extensiones de nombres de archivos.</span><span class="sxs-lookup"><span data-stu-id="397fe-210">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="397fe-211">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="397fe-211">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="397fe-212">La propiedad `EnableDefaultEmbeddedResourceItems` controla si los elementos de los recursos incrustados se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="397fe-212">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="397fe-213">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-213">The default value is `true`.</span></span> <span data-ttu-id="397fe-214">Establezca la propiedad `EnableDefaultEmbeddedResourceItems` en `false` para deshabilitar la inclusión implícita de los archivos de los recursos incrustados.</span><span class="sxs-lookup"><span data-stu-id="397fe-214">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="397fe-215">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="397fe-215">EnableDefaultNoneItems</span></span>

<span data-ttu-id="397fe-216">La propiedad `EnableDefaultNoneItems` controla si los elementos `None` (archivos que no tienen ningún rol en el proceso de compilación) se incluyen implícitamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-216">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="397fe-217">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-217">The default value is `true`.</span></span> <span data-ttu-id="397fe-218">Establezca la propiedad `EnableDefaultNoneItems` en `false` para deshabilitar la inclusión implícita de elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="397fe-218">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="397fe-219">Propiedades de análisis de código</span><span class="sxs-lookup"><span data-stu-id="397fe-219">Code analysis properties</span></span>

- [<span data-ttu-id="397fe-220">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="397fe-220">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="397fe-221">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="397fe-221">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="397fe-222">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="397fe-222">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="397fe-223">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="397fe-223">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="397fe-224">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="397fe-224">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="397fe-225">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="397fe-225">AnalysisLevel</span></span>

<span data-ttu-id="397fe-226">La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="397fe-226">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="397fe-227">Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="397fe-227">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="397fe-228">El valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="397fe-228">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="397fe-229">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="397fe-229">The following table shows the available options.</span></span>

| <span data-ttu-id="397fe-230">Value</span><span class="sxs-lookup"><span data-stu-id="397fe-230">Value</span></span> | <span data-ttu-id="397fe-231">Significado</span><span class="sxs-lookup"><span data-stu-id="397fe-231">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="397fe-232">Se usan los analizadores de código que se han publicado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="397fe-232">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="397fe-233">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="397fe-233">This is the default.</span></span> |
| `preview` | <span data-ttu-id="397fe-234">Se usan los analizadores de código más recientes, incluso si están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="397fe-234">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="397fe-235">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="397fe-235">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="397fe-236">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="397fe-236">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="397fe-237">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="397fe-237">AnalysisMode</span></span>

<span data-ttu-id="397fe-238">A partir de .NET 5.0, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-238">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="397fe-239">De forma predeterminada, solo [algunas reglas están habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="397fe-239">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="397fe-240">La propiedad `AnalysisMode` le permite personalizar el conjunto de reglas que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="397fe-240">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="397fe-241">Puede cambiar a un modo de análisis más agresivo (exclusión) o a uno más conservador (inclusión).</span><span class="sxs-lookup"><span data-stu-id="397fe-241">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="397fe-242">Por ejemplo, si quiere habilitar todas las reglas de forma predeterminada como advertencias de compilación, establezca el valor en `AllEnabledByDefault`.</span><span class="sxs-lookup"><span data-stu-id="397fe-242">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="397fe-243">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="397fe-243">The following table shows the available options.</span></span>

| <span data-ttu-id="397fe-244">Value</span><span class="sxs-lookup"><span data-stu-id="397fe-244">Value</span></span> | <span data-ttu-id="397fe-245">Significado</span><span class="sxs-lookup"><span data-stu-id="397fe-245">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="397fe-246">Modo predeterminado, en el que ciertas reglas están habilitadas como advertencias de compilación, otras están habilitadas como sugerencias del IDE de Visual Studio y el resto están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="397fe-246">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="397fe-247">Modo agresivo o de exclusión, en el que todas las reglas están habilitadas de forma predeterminada como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="397fe-247">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="397fe-248">Puede [excluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.</span><span class="sxs-lookup"><span data-stu-id="397fe-248">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="397fe-249">Modo conservador o de inclusión, en el que todas las reglas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="397fe-249">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="397fe-250">Puede [incluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="397fe-250">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="397fe-251">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="397fe-251">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="397fe-252">La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de calidad del código (CAxxxx) se deben tratar como advertencias e interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="397fe-252">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="397fe-253">Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) también se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="397fe-253">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="397fe-254">Si no quiere que las advertencias de análisis de calidad del código se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-254">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="397fe-255">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="397fe-255">EnableNETAnalyzers</span></span>

<span data-ttu-id="397fe-256">De forma predeterminada, el [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="397fe-256">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="397fe-257">Puede habilitar el análisis de código de .NET para los proyectos que tienen como destino versiones anteriores de .NET estableciendo la propiedad `EnableNETAnalyzers` en `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-257">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="397fe-258">Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="397fe-258">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="397fe-259">Otra forma de habilitar el análisis de código de .NET en proyectos que tienen como destino versiones de .NET anteriores a .NET 5.0 es establecer la propiedad [AnalysisLevel](#analysislevel) en `latest`.</span><span class="sxs-lookup"><span data-stu-id="397fe-259">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="397fe-260">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="397fe-260">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="397fe-261">En la actualidad, esta característica es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.</span><span class="sxs-lookup"><span data-stu-id="397fe-261">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="397fe-262">El [análisis del estilo del código de .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) está deshabilitado de forma predeterminada en la compilación para todos los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="397fe-262">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="397fe-263">Puede habilitar el análisis del estilo del código para los proyectos de .NET estableciendo la propiedad `EnforceCodeStyleInBuild` en `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-263">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="397fe-264">Todas las reglas de estilo del código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) como advertencias o errores se ejecutarán en la compilación y notificarán infracciones.</span><span class="sxs-lookup"><span data-stu-id="397fe-264">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="397fe-265">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="397fe-265">Run-time configuration properties</span></span>

<span data-ttu-id="397fe-266">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="397fe-266">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="397fe-267">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-267">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="397fe-268">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-268">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="397fe-269">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="397fe-269">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="397fe-270">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-270">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="397fe-271">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-271">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="397fe-272">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="397fe-272">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="397fe-273">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="397fe-273">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="397fe-274">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="397fe-274">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="397fe-275">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="397fe-275">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="397fe-276">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="397fe-276">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="397fe-277">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-277">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="397fe-278">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-278">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="397fe-279">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="397fe-279">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="397fe-280">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="397fe-280">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="397fe-281">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="397fe-281">InvariantGlobalization</span></span>

<span data-ttu-id="397fe-282">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="397fe-282">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="397fe-283">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="397fe-283">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="397fe-284">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="397fe-284">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="397fe-285">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-285">RetainVMGarbageCollection</span></span>

<span data-ttu-id="397fe-286">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="397fe-286">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="397fe-287">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="397fe-287">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="397fe-288">Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="397fe-288">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="397fe-289">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="397fe-289">ServerGarbageCollection</span></span>

<span data-ttu-id="397fe-290">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-290">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="397fe-291">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="397fe-291">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="397fe-292">Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="397fe-292">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="397fe-293">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="397fe-293">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="397fe-294">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="397fe-294">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="397fe-295">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="397fe-295">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="397fe-296">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="397fe-296">ThreadPoolMinThreads</span></span>

<span data-ttu-id="397fe-297">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="397fe-297">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="397fe-298">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="397fe-298">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="397fe-299">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="397fe-299">TieredCompilation</span></span>

<span data-ttu-id="397fe-300">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="397fe-300">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="397fe-301">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="397fe-301">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="397fe-302">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="397fe-302">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="397fe-303">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="397fe-303">TieredCompilationQuickJit</span></span>

<span data-ttu-id="397fe-304">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="397fe-304">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="397fe-305">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="397fe-305">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="397fe-306">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="397fe-306">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="397fe-307">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="397fe-307">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="397fe-308">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="397fe-308">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="397fe-309">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="397fe-309">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="397fe-310">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="397fe-310">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="397fe-311">Referencia de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="397fe-311">Reference properties and items</span></span>

- [<span data-ttu-id="397fe-312">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="397fe-312">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="397fe-313">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="397fe-313">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="397fe-314">PackageReference</span><span class="sxs-lookup"><span data-stu-id="397fe-314">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="397fe-315">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="397fe-315">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="397fe-316">Referencia</span><span class="sxs-lookup"><span data-stu-id="397fe-316">Reference</span></span>](#reference)
- [<span data-ttu-id="397fe-317">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="397fe-317">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="397fe-318">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="397fe-318">AssetTargetFallback</span></span>

<span data-ttu-id="397fe-319">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="397fe-319">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="397fe-320">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="397fe-320">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="397fe-321">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="397fe-321">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="397fe-322">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="397fe-322">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="397fe-323">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="397fe-323">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="397fe-324">La propiedad `DisableImplicitFrameworkReferences` controla los elementos `FrameworkReference` implícitos cuando el destino es .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="397fe-324">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="397fe-325">Cuando el destino es .NET Core 2.1 o .NET Standard 2.0 y versiones anteriores, controla los elementos [PackageReference](#packagereference) implícitos en los paquetes de un metapaquete.</span><span class="sxs-lookup"><span data-stu-id="397fe-325">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="397fe-326">(Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes). Esta propiedad también controla las referencias implícitas como `System` y `System.Core` cuando el destino es .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="397fe-326">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="397fe-327">Establezca esta propiedad en `true` para deshabilitar los elementos `FrameworkReference` o [PackageReference](#packagereference) implícitos.</span><span class="sxs-lookup"><span data-stu-id="397fe-327">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="397fe-328">Si establece esta propiedad en `true`, puede agregar referencias explícitas solo a las plataformas o paquetes que necesite.</span><span class="sxs-lookup"><span data-stu-id="397fe-328">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="397fe-329">PackageReference</span><span class="sxs-lookup"><span data-stu-id="397fe-329">PackageReference</span></span>

<span data-ttu-id="397fe-330">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="397fe-330">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="397fe-331">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="397fe-331">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="397fe-332">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="397fe-332">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="397fe-333">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="397fe-333">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="397fe-334">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-334">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="397fe-335">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="397fe-335">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="397fe-336">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="397fe-336">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="397fe-337">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="397fe-337">ProjectReference</span></span>

<span data-ttu-id="397fe-338">El elemento `ProjectReference` define una referencia a otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-338">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="397fe-339">El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="397fe-339">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="397fe-340">El atributo `Include` especifica la ruta de acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-340">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="397fe-341">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-341">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="397fe-342">El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.</span><span class="sxs-lookup"><span data-stu-id="397fe-342">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="397fe-343">Referencia</span><span class="sxs-lookup"><span data-stu-id="397fe-343">Reference</span></span>

<span data-ttu-id="397fe-344">El elemento `Reference` define una referencia a un archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="397fe-344">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="397fe-345">El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="397fe-345">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="397fe-346">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="397fe-346">Restore-related properties</span></span>

<span data-ttu-id="397fe-347">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="397fe-347">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="397fe-348">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="397fe-348">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="397fe-349">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="397fe-349">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="397fe-350">Propiedades de Run</span><span class="sxs-lookup"><span data-stu-id="397fe-350">Run properties</span></span>

<span data-ttu-id="397fe-351">Las siguientes propiedades se usan para iniciar una aplicación con el comando [`dotnet run`](../tools/dotnet-run.md):</span><span class="sxs-lookup"><span data-stu-id="397fe-351">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="397fe-352">RunArguments</span><span class="sxs-lookup"><span data-stu-id="397fe-352">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="397fe-353">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="397fe-353">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="397fe-354">RunArguments</span><span class="sxs-lookup"><span data-stu-id="397fe-354">RunArguments</span></span>

<span data-ttu-id="397fe-355">La propiedad `RunArguments` define los argumentos que se pasan a la aplicación cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="397fe-355">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="397fe-356">Puede especificar los argumentos adicionales que se pasarán a la aplicación mediante la opción [`--` para `dotnet run`](../tools/dotnet-run.md#options).</span><span class="sxs-lookup"><span data-stu-id="397fe-356">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="397fe-357">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="397fe-357">RunWorkingDirectory</span></span>

<span data-ttu-id="397fe-358">La propiedad `RunWorkingDirectory` define el directorio de trabajo en el que se iniciará el proceso.</span><span class="sxs-lookup"><span data-stu-id="397fe-358">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="397fe-359">Puede ser una ruta de acceso absoluta o relativa al directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="397fe-359">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="397fe-360">Si no se especifica un directorio, se usa `OutDir` como directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="397fe-360">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a><span data-ttu-id="397fe-361">Propiedades de hospedaje</span><span class="sxs-lookup"><span data-stu-id="397fe-361">Hosting properties</span></span>

- [<span data-ttu-id="397fe-362">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="397fe-362">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="397fe-363">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="397fe-363">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="397fe-364">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="397fe-364">EnableComHosting</span></span>

<span data-ttu-id="397fe-365">La propiedad `EnableComHosting` indica que un ensamblado proporciona un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="397fe-365">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="397fe-366">Al establecer `EnableComHosting` en `true` también implica que [EnableDynamicLoading](#enabledynamicloading) es `true`.</span><span class="sxs-lookup"><span data-stu-id="397fe-366">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="397fe-367">Para obtener más información, vea [Exposición de componentes de .NET en COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-367">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="397fe-368">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="397fe-368">EnableDynamicLoading</span></span>

<span data-ttu-id="397fe-369">La propiedad `EnableDynamicLoading` indica que un ensamblado es un componente cargado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="397fe-369">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="397fe-370">El componente podría ser una [biblioteca de COM](/windows/win32/com/the-component-object-model) o una biblioteca que no es de COM que se puede [usar desde un host nativo](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="397fe-370">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="397fe-371">Establecer esta propiedad en `true` tiene los efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="397fe-371">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="397fe-372">Se genera un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="397fe-372">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="397fe-373">La [puesta al día](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) se establece en `LatestMinor`.</span><span class="sxs-lookup"><span data-stu-id="397fe-373">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="397fe-374">Las referencias de NuGet se copian localmente.</span><span class="sxs-lookup"><span data-stu-id="397fe-374">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="397fe-375">Vea también</span><span class="sxs-lookup"><span data-stu-id="397fe-375">See also</span></span>

- [<span data-ttu-id="397fe-376">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="397fe-376">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="397fe-377">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="397fe-377">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="397fe-378">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="397fe-378">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="397fe-379">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="397fe-379">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="397fe-380">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="397fe-380">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
