---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: 115c4f32e856dee64abe0c607b8ee595a65692e6
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/24/2020
ms.locfileid: "87164385"
---
# <a name="msbuild-reference-for-net-core-sdk-projects"></a><span data-ttu-id="3a6c2-103">Referencia de MSBuild para proyectos del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3a6c2-103">MSBuild reference for .NET Core SDK projects</span></span>

<span data-ttu-id="3a6c2-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="3a6c2-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="3a6c2-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="3a6c2-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="3a6c2-107">Framework properties</span></span>

- [<span data-ttu-id="3a6c2-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="3a6c2-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="3a6c2-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="3a6c2-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="3a6c2-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="3a6c2-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="3a6c2-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="3a6c2-111">TargetFramework</span></span>

<span data-ttu-id="3a6c2-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-112">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="3a6c2-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="3a6c2-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="3a6c2-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="3a6c2-115">TargetFrameworks</span></span>

<span data-ttu-id="3a6c2-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="3a6c2-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="3a6c2-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="3a6c2-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="3a6c2-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="3a6c2-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="3a6c2-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="3a6c2-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="3a6c2-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="3a6c2-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="3a6c2-125">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="3a6c2-125">Package properties</span></span>

<span data-ttu-id="3a6c2-126">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-126">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="3a6c2-127">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-127">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-and-items"></a><span data-ttu-id="3a6c2-128">Publicación de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="3a6c2-128">Publish properties and items</span></span>

- [<span data-ttu-id="3a6c2-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="3a6c2-129">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="3a6c2-130">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="3a6c2-130">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="3a6c2-131">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="3a6c2-131">TrimmerRootAssembly</span></span>](#trimmerrootassembly)
- [<span data-ttu-id="3a6c2-132">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="3a6c2-132">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="3a6c2-133">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="3a6c2-133">RuntimeIdentifier</span></span>

<span data-ttu-id="3a6c2-134">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-134">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="3a6c2-135">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-135">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="3a6c2-136">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="3a6c2-136">RuntimeIdentifiers</span></span>

<span data-ttu-id="3a6c2-137">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-137">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="3a6c2-138">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-138">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="3a6c2-139">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-139">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="3a6c2-140">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-140">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a><span data-ttu-id="3a6c2-141">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="3a6c2-141">TrimmerRootAssembly</span></span>

<span data-ttu-id="3a6c2-142">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-142">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="3a6c2-143">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-143">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="3a6c2-144">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-144">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="3a6c2-145">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-145">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a><span data-ttu-id="3a6c2-146">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="3a6c2-146">UseAppHost</span></span>

<span data-ttu-id="3a6c2-147">La propiedad `UseAppHost` se presentó en la versión 2.1.400 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-147">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="3a6c2-148">Controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-148">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="3a6c2-149">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-149">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="3a6c2-150">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-150">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="3a6c2-151">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-151">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="3a6c2-152">Para obtener más información sobre la implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-152">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="3a6c2-153">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="3a6c2-153">Compile properties</span></span>

- [<span data-ttu-id="3a6c2-154">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="3a6c2-154">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="3a6c2-155">LangVersion</span><span class="sxs-lookup"><span data-stu-id="3a6c2-155">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="3a6c2-156">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="3a6c2-156">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="3a6c2-157">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-157">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="3a6c2-158">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-158">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="3a6c2-159">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-159">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="3a6c2-160">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-160">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="3a6c2-161">De forma predeterminada, en un nuevo proyecto de .NET Core, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-161">By default, in a new .NET Core project, this property is set to `true`.</span></span> <span data-ttu-id="3a6c2-162">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-162">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="3a6c2-163">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-163">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="3a6c2-164">LangVersion</span><span class="sxs-lookup"><span data-stu-id="3a6c2-164">LangVersion</span></span>

<span data-ttu-id="3a6c2-165">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-165">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="3a6c2-166">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-166">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="3a6c2-167">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-167">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="3a6c2-168">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="3a6c2-168">Run-time configuration properties</span></span>

<span data-ttu-id="3a6c2-169">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-169">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="3a6c2-170">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración del tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-170">For information about other ways of configuring run-time behavior, see [.NET Core run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="3a6c2-171">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-171">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="3a6c2-172">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="3a6c2-172">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="3a6c2-173">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-173">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="3a6c2-174">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-174">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="3a6c2-175">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3a6c2-175">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="3a6c2-176">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="3a6c2-176">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="3a6c2-177">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="3a6c2-177">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="3a6c2-178">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="3a6c2-178">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="3a6c2-179">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="3a6c2-179">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="3a6c2-180">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-180">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="3a6c2-181">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-181">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="3a6c2-182">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-182">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="3a6c2-183">Para obtener más información, consulte [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-183">For more information, see [System.GC.Concurrent/COMPlus_gcConcurrent](../run-time-config/garbage-collector.md#systemgcconcurrentcomplus_gcconcurrent).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="3a6c2-184">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="3a6c2-184">InvariantGlobalization</span></span>

<span data-ttu-id="3a6c2-185">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-185">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="3a6c2-186">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-186">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="3a6c2-187">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-187">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="3a6c2-188">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-188">RetainVMGarbageCollection</span></span>

<span data-ttu-id="3a6c2-189">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-189">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="3a6c2-190">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-190">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="3a6c2-191">Para obtener más información, consulte [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-191">For more information, see [System.GC.RetainVM/COMPlus_GCRetainVM](../run-time-config/garbage-collector.md#systemgcretainvmcomplus_gcretainvm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="3a6c2-192">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="3a6c2-192">ServerGarbageCollection</span></span>

<span data-ttu-id="3a6c2-193">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-193">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="3a6c2-194">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-194">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="3a6c2-195">Para obtener más información, consulte [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-195">For more information, see [System.GC.Server/COMPlus_gcServer](../run-time-config/garbage-collector.md#systemgcservercomplus_gcserver).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="3a6c2-196">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="3a6c2-196">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="3a6c2-197">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-197">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="3a6c2-198">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-198">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="3a6c2-199">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="3a6c2-199">ThreadPoolMinThreads</span></span>

<span data-ttu-id="3a6c2-200">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-200">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="3a6c2-201">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-201">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="3a6c2-202">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="3a6c2-202">TieredCompilation</span></span>

<span data-ttu-id="3a6c2-203">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-203">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="3a6c2-204">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-204">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="3a6c2-205">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-205">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="3a6c2-206">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="3a6c2-206">TieredCompilationQuickJit</span></span>

<span data-ttu-id="3a6c2-207">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-207">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="3a6c2-208">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-208">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="3a6c2-209">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-209">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="3a6c2-210">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="3a6c2-210">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="3a6c2-211">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-211">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="3a6c2-212">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-212">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="3a6c2-213">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-213">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a><span data-ttu-id="3a6c2-214">Referencia de propiedades y elementos</span><span class="sxs-lookup"><span data-stu-id="3a6c2-214">Reference properties and items</span></span>

- [<span data-ttu-id="3a6c2-215">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="3a6c2-215">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="3a6c2-216">PackageReference</span><span class="sxs-lookup"><span data-stu-id="3a6c2-216">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="3a6c2-217">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="3a6c2-217">ProjectReference</span></span>](#projectreference)
- [<span data-ttu-id="3a6c2-218">Referencia</span><span class="sxs-lookup"><span data-stu-id="3a6c2-218">Reference</span></span>](#reference)
- [<span data-ttu-id="3a6c2-219">Restaurar las propiedades</span><span class="sxs-lookup"><span data-stu-id="3a6c2-219">Restore properties</span></span>](#restore-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="3a6c2-220">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="3a6c2-220">AssetTargetFallback</span></span>

<span data-ttu-id="3a6c2-221">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-221">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="3a6c2-222">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-222">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="3a6c2-223">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-223">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="3a6c2-224">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-224">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="packagereference"></a><span data-ttu-id="3a6c2-225">PackageReference</span><span class="sxs-lookup"><span data-stu-id="3a6c2-225">PackageReference</span></span>

<span data-ttu-id="3a6c2-226">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-226">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="3a6c2-227">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-227">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="3a6c2-228">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-228">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="3a6c2-229">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-229">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span> <span data-ttu-id="3a6c2-230">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-230">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="3a6c2-231">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-231">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="3a6c2-232">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-232">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="projectreference"></a><span data-ttu-id="3a6c2-233">ProjectReference</span><span class="sxs-lookup"><span data-stu-id="3a6c2-233">ProjectReference</span></span>

<span data-ttu-id="3a6c2-234">El elemento `ProjectReference` define una referencia a otro proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-234">The `ProjectReference` item defines a reference to another project.</span></span> <span data-ttu-id="3a6c2-235">El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-235">The referenced project is added as a NuGet package dependency, that is, it's treated the same as a `PackageReference`.</span></span>

<span data-ttu-id="3a6c2-236">El atributo `Include` especifica la ruta de acceso al proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-236">The `Include` attribute specifies the path to the project.</span></span> <span data-ttu-id="3a6c2-237">También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-237">You can also add the following metadata to a project reference: `IncludeAssets`, `ExcludeAssets`, and `PrivateAssets`.</span></span>

<span data-ttu-id="3a6c2-238">El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-238">The project file snippet in the following example references a project named `Project2`.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a><span data-ttu-id="3a6c2-239">Referencia</span><span class="sxs-lookup"><span data-stu-id="3a6c2-239">Reference</span></span>

<span data-ttu-id="3a6c2-240">El elemento `Reference` define una referencia a un archivo de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-240">The `Reference` item defines a reference to an assembly file.</span></span>

<span data-ttu-id="3a6c2-241">El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-241">The `Include` attribute specifies the name of the file, and the `HintPath` metadata specifies the path to the assembly.</span></span>

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-properties"></a><span data-ttu-id="3a6c2-242">Restaurar las propiedades</span><span class="sxs-lookup"><span data-stu-id="3a6c2-242">Restore properties</span></span>

<span data-ttu-id="3a6c2-243">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-243">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="3a6c2-244">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="3a6c2-244">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="3a6c2-245">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="3a6c2-245">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="see-also"></a><span data-ttu-id="3a6c2-246">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a6c2-246">See also</span></span>

- [<span data-ttu-id="3a6c2-247">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="3a6c2-247">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="3a6c2-248">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="3a6c2-248">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="3a6c2-249">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="3a6c2-249">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="3a6c2-250">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="3a6c2-250">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="3a6c2-251">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="3a6c2-251">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
