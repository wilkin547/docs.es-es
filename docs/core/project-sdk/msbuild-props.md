---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 27944a6726f8d74a3b00c7c774faa8037c0f2f0e
ms.sourcegitcommit: 88fbb019b84c2d044d11fb4f6004aec07f2b25b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/05/2021
ms.locfileid: "97899631"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="49acb-103">Referencia de MSBuild para proyectos del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="49acb-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="49acb-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="49acb-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="49acb-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="49acb-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="49acb-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="49acb-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="49acb-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="49acb-107">Framework properties</span></span>

- [<span data-ttu-id="49acb-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="49acb-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="49acb-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="49acb-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="49acb-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="49acb-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="49acb-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="49acb-111">TargetFramework</span></span>

<span data-ttu-id="49acb-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49acb-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="49acb-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="49acb-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="49acb-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="49acb-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="49acb-115">TargetFrameworks</span></span>

<span data-ttu-id="49acb-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="49acb-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="49acb-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="49acb-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="49acb-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="49acb-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="49acb-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="49acb-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="49acb-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="49acb-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="49acb-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="49acb-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="49acb-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="49acb-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="49acb-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="49acb-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="49acb-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="49acb-125">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="49acb-125">Package properties</span></span>

<span data-ttu-id="49acb-126">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="49acb-127">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="49acb-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="49acb-128">Publicación de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="49acb-128">Publish properties and items</span></span>

- [<span data-ttu-id="49acb-129">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="49acb-129">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="49acb-130">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="49acb-130">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="49acb-131">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="49acb-131">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="49acb-132">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="49acb-132">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="49acb-133">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="49acb-133">UseAppHost</span></span>](#useapphost)

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="49acb-134">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="49acb-134">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="49acb-135">La propiedad `CopyLocalLockFileAssemblies` es útil para los proyectos de complementos que tienen dependencias de otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="49acb-135">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="49acb-136">Si establece esta propiedad en `true`, todas las dependencias de paquetes NuGet se copian en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="49acb-136">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="49acb-137">Esto significa que puede usar la salida de `dotnet build` para ejecutar el complemento en cualquier equipo.</span><span class="sxs-lookup"><span data-stu-id="49acb-137">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="49acb-138">Como alternativa, puede usar `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="49acb-138">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="49acb-139">Para obtener más información, vea [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-139">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="49acb-140">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="49acb-140">RuntimeIdentifier</span></span>

<span data-ttu-id="49acb-141">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-141">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="49acb-142">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="49acb-142">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="49acb-143">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="49acb-143">RuntimeIdentifiers</span></span>

<span data-ttu-id="49acb-144">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-144">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="49acb-145">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49acb-145">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="49acb-146">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="49acb-146">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="49acb-147">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49acb-147">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="49acb-148">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="49acb-148">TrimmerRootAssembly</span></span>

<span data-ttu-id="49acb-149">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49acb-149">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="49acb-150">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="49acb-150">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="49acb-151">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="49acb-151">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="49acb-152">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="49acb-152">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="49acb-153">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="49acb-153">UseAppHost</span></span>

<span data-ttu-id="49acb-154">La propiedad `UseAppHost` controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="49acb-154">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="49acb-155">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="49acb-155">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="49acb-156">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49acb-156">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="49acb-157">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="49acb-157">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="49acb-158">Para más información sobre la implementación, consulte [Implementación de aplicaciones .NET](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-158">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="49acb-159">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="49acb-159">Compile properties</span></span>

- [<span data-ttu-id="49acb-160">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="49acb-160">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="49acb-161">LangVersion</span><span class="sxs-lookup"><span data-stu-id="49acb-161">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="49acb-162">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="49acb-162">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="49acb-163">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="49acb-163">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="49acb-164">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="49acb-164">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="49acb-165">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="49acb-165">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="49acb-166">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="49acb-166">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="49acb-167">De forma predeterminada, en un nuevo proyecto de .NET, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="49acb-167">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="49acb-168">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="49acb-168">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="49acb-169">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-169">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="49acb-170">LangVersion</span><span class="sxs-lookup"><span data-stu-id="49acb-170">LangVersion</span></span>

<span data-ttu-id="49acb-171">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="49acb-171">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="49acb-172">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="49acb-172">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="49acb-173">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="49acb-173">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="49acb-174">Propiedades de análisis de código</span><span class="sxs-lookup"><span data-stu-id="49acb-174">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="49acb-175">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="49acb-175">AnalysisLevel</span></span>

<span data-ttu-id="49acb-176">La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="49acb-176">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="49acb-177">Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="49acb-177">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="49acb-178">El valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="49acb-178">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="49acb-179">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="49acb-179">The following table shows the available options.</span></span>

| <span data-ttu-id="49acb-180">Value</span><span class="sxs-lookup"><span data-stu-id="49acb-180">Value</span></span> | <span data-ttu-id="49acb-181">Significado</span><span class="sxs-lookup"><span data-stu-id="49acb-181">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="49acb-182">Se usan los analizadores de código que se han publicado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="49acb-182">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="49acb-183">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="49acb-183">This is the default.</span></span> |
| `preview` | <span data-ttu-id="49acb-184">Se usan los analizadores de código más recientes, incluso si están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="49acb-184">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="49acb-185">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="49acb-185">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="49acb-186">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="49acb-186">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="analysismode"></a><span data-ttu-id="49acb-187">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="49acb-187">AnalysisMode</span></span>

<span data-ttu-id="49acb-188">A partir de .NET 5.0, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-188">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="49acb-189">De forma predeterminada, solo [algunas reglas están habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="49acb-189">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="49acb-190">La propiedad `AnalysisMode` le permite personalizar el conjunto de reglas que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49acb-190">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="49acb-191">Puede cambiar a un modo de análisis más agresivo (exclusión) o a uno más conservador (inclusión).</span><span class="sxs-lookup"><span data-stu-id="49acb-191">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="49acb-192">Por ejemplo, si quiere habilitar todas las reglas de forma predeterminada como advertencias de compilación, establezca el valor en `AllEnabledByDefault`.</span><span class="sxs-lookup"><span data-stu-id="49acb-192">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="49acb-193">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="49acb-193">The following table shows the available options.</span></span>

| <span data-ttu-id="49acb-194">Value</span><span class="sxs-lookup"><span data-stu-id="49acb-194">Value</span></span> | <span data-ttu-id="49acb-195">Significado</span><span class="sxs-lookup"><span data-stu-id="49acb-195">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="49acb-196">Modo predeterminado, en el que ciertas reglas están habilitadas como advertencias de compilación, otras están habilitadas como sugerencias del IDE de Visual Studio y el resto están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="49acb-196">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="49acb-197">Modo agresivo o de exclusión, en el que todas las reglas están habilitadas de forma predeterminada como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="49acb-197">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="49acb-198">Puede [excluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.</span><span class="sxs-lookup"><span data-stu-id="49acb-198">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="49acb-199">Modo conservador o de inclusión, en el que todas las reglas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49acb-199">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="49acb-200">Puede [incluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="49acb-200">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="49acb-201">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="49acb-201">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="49acb-202">La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de calidad del código (CAxxxx) se deben tratar como advertencias e interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="49acb-202">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="49acb-203">Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) también se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="49acb-203">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="49acb-204">Si no quiere que las advertencias de análisis de calidad del código se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-204">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="49acb-205">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="49acb-205">EnableNETAnalyzers</span></span>

<span data-ttu-id="49acb-206">De forma predeterminada, el [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="49acb-206">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="49acb-207">Puede habilitar el análisis de código de .NET para los proyectos que tienen como destino versiones anteriores de .NET estableciendo la propiedad `EnableNETAnalyzers` en `true`.</span><span class="sxs-lookup"><span data-stu-id="49acb-207">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="49acb-208">Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="49acb-208">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="49acb-209">Otra forma de habilitar el análisis de código de .NET en proyectos que tienen como destino versiones de .NET anteriores a .NET 5.0 es establecer la propiedad [AnalysisLevel](#analysislevel) en `latest`.</span><span class="sxs-lookup"><span data-stu-id="49acb-209">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="49acb-210">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="49acb-210">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="49acb-211">En la actualidad, esta característica es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.</span><span class="sxs-lookup"><span data-stu-id="49acb-211">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="49acb-212">El [análisis del estilo del código de .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) está deshabilitado de forma predeterminada en la compilación para todos los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="49acb-212">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="49acb-213">Puede habilitar el análisis del estilo del código para los proyectos de .NET estableciendo la propiedad `EnforceCodeStyleInBuild` en `true`.</span><span class="sxs-lookup"><span data-stu-id="49acb-213">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="49acb-214">Todas las reglas de estilo del código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) como advertencias o errores se ejecutarán en la compilación y notificarán infracciones.</span><span class="sxs-lookup"><span data-stu-id="49acb-214">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="49acb-215">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="49acb-215">Run-time configuration properties</span></span>

<span data-ttu-id="49acb-216">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="49acb-216">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="49acb-217">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-217">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="49acb-218">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-218">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="49acb-219">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="49acb-219">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="49acb-220">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-220">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="49acb-221">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-221">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="49acb-222">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="49acb-222">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="49acb-223">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="49acb-223">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="49acb-224">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="49acb-224">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="49acb-225">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="49acb-225">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="49acb-226">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="49acb-226">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="49acb-227">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-227">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="49acb-228">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-228">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="49acb-229">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="49acb-229">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="49acb-230">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="49acb-230">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="49acb-231">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="49acb-231">InvariantGlobalization</span></span>

<span data-ttu-id="49acb-232">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="49acb-232">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="49acb-233">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="49acb-233">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="49acb-234">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="49acb-234">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="49acb-235">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-235">RetainVMGarbageCollection</span></span>

<span data-ttu-id="49acb-236">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="49acb-236">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="49acb-237">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="49acb-237">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="49acb-238">Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="49acb-238">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="49acb-239">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="49acb-239">ServerGarbageCollection</span></span>

<span data-ttu-id="49acb-240">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-240">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="49acb-241">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="49acb-241">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="49acb-242">Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="49acb-242">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="49acb-243">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="49acb-243">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="49acb-244">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49acb-244">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="49acb-245">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="49acb-245">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="49acb-246">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="49acb-246">ThreadPoolMinThreads</span></span>

<span data-ttu-id="49acb-247">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49acb-247">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="49acb-248">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="49acb-248">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="49acb-249">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="49acb-249">TieredCompilation</span></span>

<span data-ttu-id="49acb-250">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="49acb-250">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="49acb-251">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="49acb-251">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="49acb-252">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="49acb-252">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="49acb-253">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="49acb-253">TieredCompilationQuickJit</span></span>

<span data-ttu-id="49acb-254">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="49acb-254">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="49acb-255">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="49acb-255">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="49acb-256">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="49acb-256">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="49acb-257">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="49acb-257">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="49acb-258">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="49acb-258">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="49acb-259">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="49acb-259">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="49acb-260">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="49acb-260">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="49acb-261">Referencia de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="49acb-261">Reference properties and items</span></span>

- [<span data-ttu-id="49acb-262">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="49acb-262">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="49acb-263">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="49acb-263">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="49acb-264">PackageReference</span><span class="sxs-lookup"><span data-stu-id="49acb-264">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="49acb-265">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="49acb-265">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="49acb-266">Referencia</span><span class="sxs-lookup"><span data-stu-id="49acb-266">Reference</span></span>](#reference)
- [<span data-ttu-id="49acb-267">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="49acb-267">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="49acb-268">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="49acb-268">AssetTargetFallback</span></span>

<span data-ttu-id="49acb-269">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="49acb-269">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="49acb-270">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="49acb-270">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="49acb-271">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="49acb-271">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="49acb-272">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="49acb-272">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="49acb-273">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="49acb-273">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="49acb-274">La propiedad `DisableImplicitFrameworkReferences` controla los elementos `FrameworkReference` implícitos cuando el destino es .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="49acb-274">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="49acb-275">Cuando el destino es .NET Core 2.1 o .NET Standard 2.0 y versiones anteriores, controla los elementos [PackageReference](#packagereference) implícitos en los paquetes de un metapaquete.</span><span class="sxs-lookup"><span data-stu-id="49acb-275">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="49acb-276">(Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes). Esta propiedad también controla las referencias implícitas como `System` y `System.Core` cuando el destino es .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="49acb-276">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="49acb-277">Establezca esta propiedad en `true` para deshabilitar los elementos `FrameworkReference` o [PackageReference](#packagereference) implícitos.</span><span class="sxs-lookup"><span data-stu-id="49acb-277">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="49acb-278">Si establece esta propiedad en `true`, puede agregar referencias explícitas solo a las plataformas o paquetes que necesite.</span><span class="sxs-lookup"><span data-stu-id="49acb-278">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="49acb-279">PackageReference</span><span class="sxs-lookup"><span data-stu-id="49acb-279">PackageReference</span></span>

<span data-ttu-id="49acb-280">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="49acb-280">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="49acb-281">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="49acb-281">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="49acb-282">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="49acb-282">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="49acb-283">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="49acb-283">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="49acb-284">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-284">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="49acb-285">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="49acb-285">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="49acb-286">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="49acb-286">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="49acb-287">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="49acb-287">ProjectReference</span></span>

<span data-ttu-id="49acb-288">El elemento `ProjectReference` define una referencia a otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-288">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="49acb-289">El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="49acb-289">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="49acb-290">El atributo `Include` especifica la ruta de acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-290">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="49acb-291">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="49acb-291">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="49acb-292">El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.</span><span class="sxs-lookup"><span data-stu-id="49acb-292">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="49acb-293">Referencia</span><span class="sxs-lookup"><span data-stu-id="49acb-293">Reference</span></span>

<span data-ttu-id="49acb-294">El elemento `Reference` define una referencia a un archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49acb-294">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="49acb-295">El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="49acb-295">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="49acb-296">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="49acb-296">Restore-related properties</span></span>

<span data-ttu-id="49acb-297">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="49acb-297">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="49acb-298">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="49acb-298">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="49acb-299">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="49acb-299">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a><span data-ttu-id="49acb-300">Propiedades de Run</span><span class="sxs-lookup"><span data-stu-id="49acb-300">Run properties</span></span>

<span data-ttu-id="49acb-301">Las siguientes propiedades se usan para iniciar una aplicación con el comando [`dotnet run`](../tools/dotnet-run.md):</span><span class="sxs-lookup"><span data-stu-id="49acb-301">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="49acb-302">RunArguments</span><span class="sxs-lookup"><span data-stu-id="49acb-302">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="49acb-303">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="49acb-303">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="49acb-304">RunArguments</span><span class="sxs-lookup"><span data-stu-id="49acb-304">RunArguments</span></span>

<span data-ttu-id="49acb-305">La propiedad `RunArguments` define los argumentos que se pasan a la aplicación cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="49acb-305">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="49acb-306">Puede especificar los argumentos adicionales que se pasarán a la aplicación mediante la opción [`--` para `dotnet run`](../tools/dotnet-run.md#options).</span><span class="sxs-lookup"><span data-stu-id="49acb-306">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="49acb-307">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="49acb-307">RunWorkingDirectory</span></span>

<span data-ttu-id="49acb-308">La propiedad `RunWorkingDirectory` define el directorio de trabajo en el que se iniciará el proceso.</span><span class="sxs-lookup"><span data-stu-id="49acb-308">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="49acb-309">Si no se especifica un directorio, se usa `OutDir` como directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="49acb-309">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties-and-items"></a><span data-ttu-id="49acb-310">Propiedades y elementos de hospedaje</span><span class="sxs-lookup"><span data-stu-id="49acb-310">Hosting properties and items</span></span>

- [<span data-ttu-id="49acb-311">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="49acb-311">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="49acb-312">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="49acb-312">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="49acb-313">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="49acb-313">EnableComHosting</span></span>

<span data-ttu-id="49acb-314">La propiedad `EnableComHosting` indica que un ensamblado proporciona un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="49acb-314">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="49acb-315">Al establecer `EnableComHosting` en `true` también implica que [EnableDynamicLoading](#enabledynamicloading) es `true`.</span><span class="sxs-lookup"><span data-stu-id="49acb-315">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="49acb-316">Para obtener más información, vea [Exposición de componentes de .NET en COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-316">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="49acb-317">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="49acb-317">EnableDynamicLoading</span></span>

<span data-ttu-id="49acb-318">La propiedad `EnableDynamicLoading` indica que un ensamblado es un componente cargado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="49acb-318">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="49acb-319">El componente podría ser una [biblioteca de COM](/windows/win32/com/the-component-object-model) o una biblioteca que no es de COM que se puede [usar desde un host nativo](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="49acb-319">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="49acb-320">Establecer esta propiedad en `true` tiene los efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="49acb-320">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="49acb-321">Se genera un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="49acb-321">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="49acb-322">La [puesta al día](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) se establece en `LatestMinor`.</span><span class="sxs-lookup"><span data-stu-id="49acb-322">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="49acb-323">Las referencias de NuGet se copian localmente.</span><span class="sxs-lookup"><span data-stu-id="49acb-323">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="49acb-324">Vea también</span><span class="sxs-lookup"><span data-stu-id="49acb-324">See also</span></span>

- [<span data-ttu-id="49acb-325">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="49acb-325">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="49acb-326">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="49acb-326">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="49acb-327">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="49acb-327">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="49acb-328">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="49acb-328">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="49acb-329">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="49acb-329">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
