---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 39cbd18121d2b8659b2f5270f39624798f4ebbdc
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810530"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="76af3-103">Referencia de MSBuild para proyectos del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="76af3-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="76af3-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="76af3-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="76af3-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="76af3-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="76af3-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="76af3-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="76af3-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="76af3-107">Framework properties</span></span>

- [<span data-ttu-id="76af3-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="76af3-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="76af3-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="76af3-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="76af3-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="76af3-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="76af3-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="76af3-111">TargetFramework</span></span>

<span data-ttu-id="76af3-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76af3-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="76af3-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="76af3-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="76af3-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="76af3-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="76af3-115">TargetFrameworks</span></span>

<span data-ttu-id="76af3-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="76af3-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="76af3-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="76af3-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="76af3-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="76af3-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="76af3-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="76af3-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="76af3-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="76af3-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="76af3-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="76af3-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="76af3-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="76af3-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="76af3-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="76af3-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="76af3-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="76af3-125">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="76af3-125">Package properties</span></span>

<span data-ttu-id="76af3-126">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="76af3-127">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="76af3-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="76af3-128">Publicación de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="76af3-128">Publish properties and items</span></span>

- [<span data-ttu-id="76af3-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="76af3-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="76af3-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="76af3-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="76af3-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="76af3-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="76af3-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="76af3-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="76af3-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="76af3-133">RuntimeIdentifier</span></span>

<span data-ttu-id="76af3-134">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="76af3-135">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="76af3-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="76af3-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="76af3-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="76af3-137">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="76af3-138">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76af3-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="76af3-139">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="76af3-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="76af3-140">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76af3-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="76af3-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="76af3-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="76af3-142">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76af3-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="76af3-143">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="76af3-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="76af3-144">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="76af3-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="76af3-145">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="76af3-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="76af3-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="76af3-146">UseAppHost</span></span>

<span data-ttu-id="76af3-147">La propiedad `UseAppHost` se presentó en la versión 2.1.400 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="76af3-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="76af3-148">Controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="76af3-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="76af3-149">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="76af3-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="76af3-150">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76af3-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="76af3-151">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="76af3-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="76af3-152">Para obtener más información sobre la implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="76af3-153">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="76af3-153">Compile properties</span></span>

- [<span data-ttu-id="76af3-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="76af3-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="76af3-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="76af3-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="76af3-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="76af3-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="76af3-157">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="76af3-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="76af3-158">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="76af3-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="76af3-159">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="76af3-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="76af3-160">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="76af3-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="76af3-161">De forma predeterminada, en un nuevo proyecto de .NET Core, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="76af3-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="76af3-162">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="76af3-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="76af3-163">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="76af3-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="76af3-164">LangVersion</span></span>

<span data-ttu-id="76af3-165">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="76af3-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="76af3-166">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="76af3-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="76af3-167">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="76af3-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="code-analysis-properties"></a><span data-ttu-id="76af3-168">Propiedades de análisis de código</span><span class="sxs-lookup"><span data-stu-id="76af3-168">Code analysis properties</span></span>

### <a name="analysislevel"></a><span data-ttu-id="76af3-169">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="76af3-169">AnalysisLevel</span></span>

<span data-ttu-id="76af3-170">La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="76af3-170">The `AnalysisLevel` property lets you specify a code analysis level.</span></span> <span data-ttu-id="76af3-171">Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="76af3-171">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span> <span data-ttu-id="76af3-172">El valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="76af3-172">The default value is `latest`.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="76af3-173">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="76af3-173">The following table shows the available options.</span></span>

| <span data-ttu-id="76af3-174">Value</span><span class="sxs-lookup"><span data-stu-id="76af3-174">Value</span></span> | <span data-ttu-id="76af3-175">Significado</span><span class="sxs-lookup"><span data-stu-id="76af3-175">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="76af3-176">Se usan los analizadores de código que se han publicado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="76af3-176">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="76af3-177">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="76af3-177">This is the default.</span></span> |
| `preview` | <span data-ttu-id="76af3-178">Se usan los analizadores de código más recientes, incluso si están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="76af3-178">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="76af3-179">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="76af3-179">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="76af3-180">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="76af3-180">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="76af3-181">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="76af3-181">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="76af3-182">La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de código se deben tratar como advertencias e interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="76af3-182">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code analysis warnings should be treated as warnings and break the build.</span></span> <span data-ttu-id="76af3-183">Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de código de .NET](../../fundamentals/productivity/code-analysis.md) también se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="76af3-183">If you use the `-warnaserror` flag when you build your projects, [.NET code analysis](../../fundamentals/productivity/code-analysis.md) warnings are also treated as errors.</span></span> <span data-ttu-id="76af3-184">Si solo quiere que las advertencias del compilador se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-184">If you only want compiler warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="76af3-185">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="76af3-185">EnableNETAnalyzers</span></span>

<span data-ttu-id="76af3-186">De forma predeterminada, el [análisis de código de .NET](../../fundamentals/productivity/code-analysis.md) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="76af3-186">[.NET Code analysis](../../fundamentals/productivity/code-analysis.md) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="76af3-187">Puede habilitar el análisis de código de .NET para los proyectos que tienen como destino versiones anteriores de .NET estableciendo la propiedad `EnableNETAnalyzers` en "true".</span><span class="sxs-lookup"><span data-stu-id="76af3-187">You can enable .NET code analysis for projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to true.</span></span> <span data-ttu-id="76af3-188">Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="76af3-188">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="76af3-189">Otra forma de habilitar el análisis de código de .NET en proyectos que tienen como destino versiones de .NET anteriores a .NET 5.0 es establecer la propiedad [AnalysisLevel](#analysislevel) en `latest`.</span><span class="sxs-lookup"><span data-stu-id="76af3-189">Another way to enable .NET code analysis on projects that target .NET versions prior to .NET 5.0 is to set the [AnalysisLevel](#analysislevel) property to `latest`.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="76af3-190">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="76af3-190">Run-time configuration properties</span></span>

<span data-ttu-id="76af3-191">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="76af3-191">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="76af3-192">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración del tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-192">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="76af3-193">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-193">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="76af3-194">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="76af3-194">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="76af3-195">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-195">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="76af3-196">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-196">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="76af3-197">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="76af3-197">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="76af3-198">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="76af3-198">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="76af3-199">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="76af3-199">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="76af3-200">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="76af3-200">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="76af3-201">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="76af3-201">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="76af3-202">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-202">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="76af3-203">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-203">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="76af3-204">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="76af3-204">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="76af3-205">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="76af3-205">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="76af3-206">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="76af3-206">InvariantGlobalization</span></span>

<span data-ttu-id="76af3-207">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="76af3-207">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="76af3-208">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="76af3-208">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="76af3-209">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="76af3-209">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="76af3-210">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-210">RetainVMGarbageCollection</span></span>

<span data-ttu-id="76af3-211">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="76af3-211">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="76af3-212">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="76af3-212">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="76af3-213">Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="76af3-213">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="76af3-214">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="76af3-214">ServerGarbageCollection</span></span>

<span data-ttu-id="76af3-215">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="76af3-215">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="76af3-216">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="76af3-216">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="76af3-217">Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="76af3-217">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="76af3-218">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="76af3-218">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="76af3-219">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76af3-219">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="76af3-220">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="76af3-220">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="76af3-221">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="76af3-221">ThreadPoolMinThreads</span></span>

<span data-ttu-id="76af3-222">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="76af3-222">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="76af3-223">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="76af3-223">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="76af3-224">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="76af3-224">TieredCompilation</span></span>

<span data-ttu-id="76af3-225">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="76af3-225">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="76af3-226">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="76af3-226">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="76af3-227">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="76af3-227">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="76af3-228">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="76af3-228">TieredCompilationQuickJit</span></span>

<span data-ttu-id="76af3-229">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="76af3-229">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="76af3-230">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="76af3-230">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="76af3-231">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="76af3-231">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="76af3-232">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="76af3-232">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="76af3-233">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="76af3-233">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="76af3-234">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="76af3-234">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="76af3-235">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="76af3-235">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="76af3-236">Referencia de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="76af3-236">Reference properties and items</span></span>

- [<span data-ttu-id="76af3-237">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="76af3-237">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="76af3-238">PackageReference</span><span class="sxs-lookup"><span data-stu-id="76af3-238">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="76af3-239">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="76af3-239">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="76af3-240">Referencia</span><span class="sxs-lookup"><span data-stu-id="76af3-240">Reference</span></span>](#reference)
- [<span data-ttu-id="76af3-241">Restaurar las propiedades</span><span class="sxs-lookup"><span data-stu-id="76af3-241">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="76af3-242">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="76af3-242">AssetTargetFallback</span></span>

<span data-ttu-id="76af3-243">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="76af3-243">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="76af3-244">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="76af3-244">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="76af3-245">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="76af3-245">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="76af3-246">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="76af3-246">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="76af3-247">PackageReference</span><span class="sxs-lookup"><span data-stu-id="76af3-247">PackageReference</span></span>

<span data-ttu-id="76af3-248">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="76af3-248">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="76af3-249">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="76af3-249">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="76af3-250">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="76af3-250">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="76af3-251">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="76af3-251">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="76af3-252">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-252">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="76af3-253">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="76af3-253">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="76af3-254">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="76af3-254">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="76af3-255">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="76af3-255">ProjectReference</span></span>

<span data-ttu-id="76af3-256">El elemento `ProjectReference` define una referencia a otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-256">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="76af3-257">El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="76af3-257">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="76af3-258">El atributo `Include` especifica la ruta de acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-258">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="76af3-259">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="76af3-259">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="76af3-260">El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.</span><span class="sxs-lookup"><span data-stu-id="76af3-260">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="76af3-261">Referencia</span><span class="sxs-lookup"><span data-stu-id="76af3-261">Reference</span></span>

<span data-ttu-id="76af3-262">El elemento `Reference` define una referencia a un archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76af3-262">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="76af3-263">El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="76af3-263">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="76af3-264">Restaurar las propiedades</span><span class="sxs-lookup"><span data-stu-id="76af3-264">Restore properties</span></span>

<span data-ttu-id="76af3-265">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="76af3-265">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="76af3-266">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="76af3-266">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="76af3-267">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="76af3-267">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="76af3-268">Vea también</span><span class="sxs-lookup"><span data-stu-id="76af3-268">See also</span></span>

- [<span data-ttu-id="76af3-269">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="76af3-269">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="76af3-270">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="76af3-270">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="76af3-271">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="76af3-271">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="76af3-272">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="76af3-272">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="76af3-273">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="76af3-273">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
