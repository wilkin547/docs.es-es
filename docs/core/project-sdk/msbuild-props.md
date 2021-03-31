---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: effcb704056f553b2986ee4a61f73c0dc58af599
ms.sourcegitcommit: 05d0087dfca85aac9ca2960f86c5efd218bf833f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2021
ms.locfileid: "105636771"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a><span data-ttu-id="55be6-103">Referencia de MSBuild para proyectos del SDK de .NET</span><span class="sxs-lookup"><span data-stu-id="55be6-103">MSBuild reference for .NET SDK projects</span></span>

<span data-ttu-id="55be6-104">Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="55be6-104">This page is a reference for the MSBuild properties and items that you can use to configure .NET projects.</span></span>

> [!NOTE]
> <span data-ttu-id="55be6-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET.</span><span class="sxs-lookup"><span data-stu-id="55be6-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET SDK.</span></span> <span data-ttu-id="55be6-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="55be6-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="55be6-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="55be6-107">Framework properties</span></span>

<span data-ttu-id="55be6-108">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-108">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-109">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="55be6-109">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="55be6-110">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="55be6-110">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="55be6-111">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="55be6-111">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="55be6-112">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="55be6-112">TargetFramework</span></span>

<span data-ttu-id="55be6-113">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55be6-113">The `TargetFramework` property specifies the target framework version for the app.</span></span> <span data-ttu-id="55be6-114">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="55be6-114">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

<span data-ttu-id="55be6-115">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-115">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="55be6-116">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="55be6-116">TargetFrameworks</span></span>

<span data-ttu-id="55be6-117">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="55be6-117">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="55be6-118">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="55be6-118">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-frameworks).</span></span>

> [!NOTE]
> <span data-ttu-id="55be6-119">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="55be6-119">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

<span data-ttu-id="55be6-120">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-120">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="55be6-121">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="55be6-121">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="55be6-122">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="55be6-122">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="55be6-123">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="55be6-123">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="55be6-124">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete.</span><span class="sxs-lookup"><span data-stu-id="55be6-124">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the metapackage version.</span></span> <span data-ttu-id="55be6-125">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="55be6-125">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="assembly-info-generation-properties"></a><span data-ttu-id="55be6-126">Propiedades de generación de información de ensamblados</span><span class="sxs-lookup"><span data-stu-id="55be6-126">Assembly info generation properties</span></span>

- [<span data-ttu-id="55be6-127">GenerateAssemblyCompanyAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-127">GenerateAssemblyCompanyAttribute</span></span>](#generateassemblycompanyattribute)
- [<span data-ttu-id="55be6-128">GenerateAssemblyConfigurationAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-128">GenerateAssemblyConfigurationAttribute</span></span>](#generateassemblyconfigurationattribute)
- [<span data-ttu-id="55be6-129">GenerateAssemblyCopyrightAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-129">GenerateAssemblyCopyrightAttribute</span></span>](#generateassemblycopyrightattribute)
- [<span data-ttu-id="55be6-130">GenerateAssemblyDescriptionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-130">GenerateAssemblyDescriptionAttribute</span></span>](#generateassemblydescriptionattribute)
- [<span data-ttu-id="55be6-131">GenerateAssemblyFileVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-131">GenerateAssemblyFileVersionAttribute</span></span>](#generateassemblyfileversionattribute)
- [<span data-ttu-id="55be6-132">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="55be6-132">GenerateAssemblyInfo</span></span>](#generateassemblyinfo)
- [<span data-ttu-id="55be6-133">GenerateAssemblyInformationalVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-133">GenerateAssemblyInformationalVersionAttribute</span></span>](#generateassemblyinformationalversionattribute)
- [<span data-ttu-id="55be6-134">GenerateAssemblyProductAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-134">GenerateAssemblyProductAttribute</span></span>](#generateassemblyproductattribute)
- [<span data-ttu-id="55be6-135">GenerateAssemblyTitleAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-135">GenerateAssemblyTitleAttribute</span></span>](#generateassemblytitleattribute)
- [<span data-ttu-id="55be6-136">GenerateAssemblyVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-136">GenerateAssemblyVersionAttribute</span></span>](#generateassemblyversionattribute)
- [<span data-ttu-id="55be6-137">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="55be6-137">GeneratedAssemblyInfoFile</span></span>](#generatedassemblyinfofile)
- [<span data-ttu-id="55be6-138">GenerateNeutralResourcesLanguageAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-138">GenerateNeutralResourcesLanguageAttribute</span></span>](#generateneutralresourceslanguageattribute)

### <a name="generateassemblycompanyattribute"></a><span data-ttu-id="55be6-139">GenerateAssemblyCompanyAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-139">GenerateAssemblyCompanyAttribute</span></span>

<span data-ttu-id="55be6-140">Esta propiedad controla si la propiedad `Company` genera o no el elemento <xref:System.Reflection.AssemblyCompanyAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-140">This property controls whether or not the `Company` property generates the <xref:System.Reflection.AssemblyCompanyAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-141">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-141">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyCompanyAttribute>false</GenerateAssemblyCompanyAttribute>
</PropertyGroup>
```

### <a name="generateassemblyconfigurationattribute"></a><span data-ttu-id="55be6-142">GenerateAssemblyConfigurationAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-142">GenerateAssemblyConfigurationAttribute</span></span>

<span data-ttu-id="55be6-143">Esta propiedad controla si la propiedad `Configuration` genera o no el elemento <xref:System.Reflection.AssemblyConfigurationAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-143">This property controls whether or not the `Configuration` property generates the <xref:System.Reflection.AssemblyConfigurationAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-144">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-144">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyConfigurationAttribute>false</GenerateAssemblyConfigurationAttribute>
</PropertyGroup>
```

### <a name="generateassemblycopyrightattribute"></a><span data-ttu-id="55be6-145">GenerateAssemblyCopyrightAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-145">GenerateAssemblyCopyrightAttribute</span></span>

<span data-ttu-id="55be6-146">Esta propiedad controla si la propiedad `Copyright` genera o no el elemento <xref:System.Reflection.AssemblyCopyrightAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-146">This property controls whether or not the `Copyright` property generates the <xref:System.Reflection.AssemblyCopyrightAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-147">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-147">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyCopyrightAttribute>false</GenerateAssemblyCopyrightAttribute>
</PropertyGroup>
```

### <a name="generateassemblydescriptionattribute"></a><span data-ttu-id="55be6-148">GenerateAssemblyDescriptionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-148">GenerateAssemblyDescriptionAttribute</span></span>

<span data-ttu-id="55be6-149">Esta propiedad controla si la propiedad `Description` genera o no el elemento <xref:System.Reflection.AssemblyDescriptionAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-149">This property controls whether or not the `Description` property generates the <xref:System.Reflection.AssemblyDescriptionAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-150">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-150">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyDescriptionAttribute>false</GenerateAssemblyDescriptionAttribute>
</PropertyGroup>
```

### <a name="generateassemblyfileversionattribute"></a><span data-ttu-id="55be6-151">GenerateAssemblyFileVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-151">GenerateAssemblyFileVersionAttribute</span></span>

<span data-ttu-id="55be6-152">Esta propiedad controla si la propiedad `FileVersion` genera o no el elemento <xref:System.Reflection.AssemblyFileVersionAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-152">This property controls whether or not the `FileVersion` property generates the <xref:System.Reflection.AssemblyFileVersionAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-153">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-153">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyFileVersionAttribute>false</GenerateAssemblyFileVersionAttribute>
</PropertyGroup>
```

### <a name="generateassemblyinfo"></a><span data-ttu-id="55be6-154">GenerateAssemblyInfo</span><span class="sxs-lookup"><span data-stu-id="55be6-154">GenerateAssemblyInfo</span></span>

<span data-ttu-id="55be6-155">Controla la generación del atributo `AssemblyInfo` del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-155">Controls `AssemblyInfo` attribute generation for the project.</span></span> <span data-ttu-id="55be6-156">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-156">The default value is `true`.</span></span> <span data-ttu-id="55be6-157">Use `false` para deshabilitar la generación del archivo:</span><span class="sxs-lookup"><span data-stu-id="55be6-157">Use `false` to disable generation of the file:</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyInfo>false</GenerateAssemblyInfo>
</PropertyGroup>
```

<span data-ttu-id="55be6-158">El valor de configuración [GeneratedAssemblyInfoFile](#generatedassemblyinfofile) controla el nombre del archivo generado.</span><span class="sxs-lookup"><span data-stu-id="55be6-158">The [GeneratedAssemblyInfoFile](#generatedassemblyinfofile) setting controls the name of the generated file.</span></span>

<span data-ttu-id="55be6-159">Si el valor `GenerateAssemblyInfo` es `true`, las propiedades del proyecto se transforman en atributos `AssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="55be6-159">When the `GenerateAssemblyInfo` value is `true`, project properties are transformed into `AssemblyInfo` attributes.</span></span> <span data-ttu-id="55be6-160">En la tabla siguiente se enumeran las propiedades del proyecto que generan los atributos y las que pueden deshabilitar la generación:</span><span class="sxs-lookup"><span data-stu-id="55be6-160">The following table lists the project properties that generate the attributes, and the properties that can disable that generation:</span></span>

| <span data-ttu-id="55be6-161">Propiedad</span><span class="sxs-lookup"><span data-stu-id="55be6-161">Property</span></span>               | <span data-ttu-id="55be6-162">Atributo</span><span class="sxs-lookup"><span data-stu-id="55be6-162">Attribute</span></span>                                                      | <span data-ttu-id="55be6-163">Propiedad que se va a deshabilitar</span><span class="sxs-lookup"><span data-stu-id="55be6-163">Property to disable</span></span>                                                                               |
|------------------------|----------------------------------------------------------------|---------------------------------------------------------------------------------------------------|
| `Company`              | <xref:System.Reflection.AssemblyCompanyAttribute>              | [`GenerateAssemblyCompanyAttribute`](#generateassemblycompanyattribute)                           |
| `Configuration`        | <xref:System.Reflection.AssemblyConfigurationAttribute>        | [`GenerateAssemblyConfigurationAttribute`](#generateassemblyconfigurationattribute)               |
| `Copyright`            | <xref:System.Reflection.AssemblyCopyrightAttribute>            | [`GenerateAssemblyCopyrightAttribute`](#generateassemblycopyrightattribute)                       |
| `Description`          | <xref:System.Reflection.AssemblyDescriptionAttribute>          | [`GenerateAssemblyDescriptionAttribute`](#generateassemblydescriptionattribute)                   |
| `FileVersion`          | <xref:System.Reflection.AssemblyFileVersionAttribute>          | [`GenerateAssemblyFileVersionAttribute`](#generateassemblyfileversionattribute)                   |
| `InformationalVersion` | <xref:System.Reflection.AssemblyInformationalVersionAttribute> | [`GenerateAssemblyInformationalVersionAttribute`](#generateassemblyinformationalversionattribute) |
| `Product`              | <xref:System.Reflection.AssemblyProductAttribute>              | [`GenerateAssemblyProductAttribute`](#generateassemblyproductattribute)                           |
| `AssemblyTitle`        | <xref:System.Reflection.AssemblyTitleAttribute>                | [`GenerateAssemblyTitleAttribute`](#generateassemblytitleattribute)                               |
| `AssemblyVersion`      | <xref:System.Reflection.AssemblyVersionAttribute>              | [`GenerateAssemblyVersionAttribute`](#generateassemblyversionattribute)                           |
| `NeutralLanguage`      | <xref:System.Resources.NeutralResourcesLanguageAttribute>      | [`GenerateNeutralResourcesLanguageAttribute`](#generateneutralresourceslanguageattribute)         |

<span data-ttu-id="55be6-164">Notas sobre dichos valores de configuración:</span><span class="sxs-lookup"><span data-stu-id="55be6-164">Notes about these settings:</span></span>

- <span data-ttu-id="55be6-165">`AssemblyVersion` y `FileVersion` tienen como valor predeterminado el valor de `$(Version)` sin el sufijo.</span><span class="sxs-lookup"><span data-stu-id="55be6-165">`AssemblyVersion` and `FileVersion` default to the value of `$(Version)` without the suffix.</span></span> <span data-ttu-id="55be6-166">Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.</span><span class="sxs-lookup"><span data-stu-id="55be6-166">For example, if `$(Version)` is `1.2.3-beta.4`, then the value would be `1.2.3`.</span></span>
- <span data-ttu-id="55be6-167">El valor predeterminado de `InformationalVersion` es el de `$(Version)`.</span><span class="sxs-lookup"><span data-stu-id="55be6-167">`InformationalVersion` defaults to the value of `$(Version)`.</span></span>
- <span data-ttu-id="55be6-168">Si la propiedad `$(SourceRevisionId)` está presente, se anexa a `InformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="55be6-168">If the `$(SourceRevisionId)` property is present, it's appended to `InformationalVersion`.</span></span> <span data-ttu-id="55be6-169">Puede deshabilitar este comportamiento mediante `IncludeSourceRevisionInInformationalVersion`.</span><span class="sxs-lookup"><span data-stu-id="55be6-169">You can disable this behavior using `IncludeSourceRevisionInInformationalVersion`.</span></span>
- <span data-ttu-id="55be6-170">Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.</span><span class="sxs-lookup"><span data-stu-id="55be6-170">`Copyright` and `Description` properties are also used for NuGet metadata.</span></span>
- <span data-ttu-id="55be6-171">`Configuration`, que tiene `Debug` como valor predeterminado, se comparte con todos los destinos de MSBuild.</span><span class="sxs-lookup"><span data-stu-id="55be6-171">`Configuration`, which defaults to `Debug`, is shared with all MSBuild targets.</span></span> <span data-ttu-id="55be6-172">Se puede establecer con la opción `--configuration` de los comandos `dotnet`; por ejemplo, [dotnet pack](../tools/dotnet-pack.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-172">You can set it via the `--configuration` option of `dotnet` commands, for example, [dotnet pack](../tools/dotnet-pack.md).</span></span>
- <span data-ttu-id="55be6-173">Algunas de las propiedades se usan al crear un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="55be6-173">Some of the properties are used when creating a NuGet package.</span></span> <span data-ttu-id="55be6-174">Para obtener más información, consulte [Propiedades del paquete](#package-properties).</span><span class="sxs-lookup"><span data-stu-id="55be6-174">For more information, see [Package properties](#package-properties).</span></span>

#### <a name="migrating-from-net-framework"></a><span data-ttu-id="55be6-175">Migración de .NET Framework</span><span class="sxs-lookup"><span data-stu-id="55be6-175">Migrating from .NET Framework</span></span>

<span data-ttu-id="55be6-176">Las plantillas de proyectos de .NET Framework crean un archivo de código con estos atributos de información de ensamblado definidos.</span><span class="sxs-lookup"><span data-stu-id="55be6-176">.NET Framework project templates create a code file with these assembly info attributes set.</span></span> <span data-ttu-id="55be6-177">Normalmente, el archivo se encuentra en *.\Properties\AssemblyInfo.cs* o *.\Properties\AssemblyInfo.vb*.</span><span class="sxs-lookup"><span data-stu-id="55be6-177">The file is typically located at *.\Properties\AssemblyInfo.cs* or *.\Properties\AssemblyInfo.vb*.</span></span> <span data-ttu-id="55be6-178">Los proyectos de estilo SDK generan este archivo para el usuario de acuerdo con la configuración del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-178">SDK-style projects generate this file for you based on the project settings.</span></span> <span data-ttu-id="55be6-179">**No es posible tener ambas cosas.**</span><span class="sxs-lookup"><span data-stu-id="55be6-179">**You can't have both.**</span></span> <span data-ttu-id="55be6-180">Al portar el código de .NET 5 (y .NET Core 3.1) o versiones posteriores, siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="55be6-180">When porting your code to .NET 5 (and .NET Core 3.1) or later, do one of the following:</span></span>

- <span data-ttu-id="55be6-181">Deshabilite la generación del archivo de código temporal que contiene los tributos de información de ensamblado. Para ello, establezca `GenerateAssemblyInfo` en `false`.</span><span class="sxs-lookup"><span data-stu-id="55be6-181">Disable the generation of the temporary code file that contains the assembly info attributes by setting `GenerateAssemblyInfo` to `false`.</span></span> <span data-ttu-id="55be6-182">Esto le permite conservar el archivo *AssemblyInfo*.</span><span class="sxs-lookup"><span data-stu-id="55be6-182">This enables you to keep your *AssemblyInfo* file.</span></span>
- <span data-ttu-id="55be6-183">Migre la configuración del archivo `AssemblyInfo` al archivo del proyecto y elimine el archivo `AssemblyInfo`.</span><span class="sxs-lookup"><span data-stu-id="55be6-183">Migrate the settings in the `AssemblyInfo` file to the project file, and delete the `AssemblyInfo` file.</span></span>

### <a name="generateassemblyinformationalversionattribute"></a><span data-ttu-id="55be6-184">GenerateAssemblyInformationalVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-184">GenerateAssemblyInformationalVersionAttribute</span></span>

<span data-ttu-id="55be6-185">Esta propiedad controla si la propiedad `InformationalVersion` genera o no el elemento <xref:System.Reflection.AssemblyInformationalVersionAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-185">This property controls whether or not the `InformationalVersion` property generates the <xref:System.Reflection.AssemblyInformationalVersionAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-186">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-186">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyInformationalVersionAttribute>false</GenerateAssemblyInformationalVersionAttribute>
</PropertyGroup>
```

### <a name="generateassemblyproductattribute"></a><span data-ttu-id="55be6-187">GenerateAssemblyProductAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-187">GenerateAssemblyProductAttribute</span></span>

<span data-ttu-id="55be6-188">Esta propiedad controla si la propiedad `Product` genera o no el elemento <xref:System.Reflection.AssemblyProductAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-188">This property controls whether or not the `Product` property generates the <xref:System.Reflection.AssemblyProductAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-189">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-189">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyProductAttribute>false</GenerateAssemblyProductAttribute>
</PropertyGroup>
```

### <a name="generateassemblytitleattribute"></a><span data-ttu-id="55be6-190">GenerateAssemblyTitleAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-190">GenerateAssemblyTitleAttribute</span></span>

<span data-ttu-id="55be6-191">Esta propiedad controla si la propiedad `AssemblyTitle` genera o no el elemento <xref:System.Reflection.AssemblyTitleAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-191">This property controls whether or not the `AssemblyTitle` property generates the <xref:System.Reflection.AssemblyTitleAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-192">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-192">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyTitleAttribute>false</GenerateAssemblyTitleAttribute>
</PropertyGroup>
```

### <a name="generateassemblyversionattribute"></a><span data-ttu-id="55be6-193">GenerateAssemblyVersionAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-193">GenerateAssemblyVersionAttribute</span></span>

<span data-ttu-id="55be6-194">Esta propiedad controla si la propiedad `AssemblyVersion` genera o no el elemento <xref:System.Reflection.AssemblyVersionAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-194">This property controls whether or not the `AssemblyVersion` property generates the <xref:System.Reflection.AssemblyVersionAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-195">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-195">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateAssemblyVersionAttribute>false</GenerateAssemblyVersionAttribute>
</PropertyGroup>
```

### <a name="generatedassemblyinfofile"></a><span data-ttu-id="55be6-196">GeneratedAssemblyInfoFile</span><span class="sxs-lookup"><span data-stu-id="55be6-196">GeneratedAssemblyInfoFile</span></span>

<span data-ttu-id="55be6-197">Esta propiedad define la ruta de acceso relativa o completa del archivo de información de ensamblado generado.</span><span class="sxs-lookup"><span data-stu-id="55be6-197">The property defines the relative or absolute path of the generated assembly info file.</span></span> <span data-ttu-id="55be6-198">Tiene un archivo denominado *[nombre-proyecto].AssemblyInfo.[cs|vb]* en el directorio `$(IntermediateOutputPath)` (normalmente, *obj*) como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="55be6-198">Defaults to a file named *[project-name].AssemblyInfo.[cs|vb]* in the `$(IntermediateOutputPath)` (usually the *obj*) directory.</span></span>

```xml
<PropertyGroup>
  <GeneratedAssemblyInfoFile>assemblyinfo.cs</GeneratedAssemblyInfoFile>
</PropertyGroup>
```

### <a name="generateneutralresourceslanguageattribute"></a><span data-ttu-id="55be6-199">GenerateNeutralResourcesLanguageAttribute</span><span class="sxs-lookup"><span data-stu-id="55be6-199">GenerateNeutralResourcesLanguageAttribute</span></span>

<span data-ttu-id="55be6-200">Esta propiedad controla si la propiedad `NeutralLanguage` genera o no el elemento <xref:System.Resources.NeutralResourcesLanguageAttribute> del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-200">This property controls whether or not the `NeutralLanguage` property generates the <xref:System.Resources.NeutralResourcesLanguageAttribute> for the assembly.</span></span> <span data-ttu-id="55be6-201">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-201">The default value is `true`.</span></span>

```xml
<PropertyGroup>
  <GenerateNeutralResourcesLanguageAttribute>false</GenerateNeutralResourcesLanguageAttribute>
</PropertyGroup>
```

## <a name="package-properties"></a><span data-ttu-id="55be6-202">Propiedades del paquete</span><span class="sxs-lookup"><span data-stu-id="55be6-202">Package properties</span></span>

<span data-ttu-id="55be6-203">Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-203">You can specify properties such as `PackageId`, `PackageVersion`, `PackageIcon`, `Title`, and `Description` to describe the package that gets created from your project.</span></span> <span data-ttu-id="55be6-204">Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).</span><span class="sxs-lookup"><span data-stu-id="55be6-204">For information about these and other properties, see [pack target](/nuget/reference/msbuild-targets#pack-target).</span></span>

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-related-properties"></a><span data-ttu-id="55be6-205">Propiedades relacionadas con la publicación</span><span class="sxs-lookup"><span data-stu-id="55be6-205">Publish-related properties</span></span>

<span data-ttu-id="55be6-206">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-206">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-207">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="55be6-207">AppendRuntimeIdentifierToOutputPath</span></span>](#appendruntimeidentifiertooutputpath)
- [<span data-ttu-id="55be6-208">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="55be6-208">AppendTargetFrameworkToOutputPath</span></span>](#appendtargetframeworktooutputpath)
- [<span data-ttu-id="55be6-209">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="55be6-209">CopyLocalLockFileAssemblies</span></span>](#copylocallockfileassemblies)
- [<span data-ttu-id="55be6-210">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="55be6-210">PreserveCompilationContext</span></span>](#preservecompilationcontext)
- [<span data-ttu-id="55be6-211">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="55be6-211">PreserveCompilationReferences</span></span>](#preservecompilationreferences)
- [<span data-ttu-id="55be6-212">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="55be6-212">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="55be6-213">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="55be6-213">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="55be6-214">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="55be6-214">UseAppHost</span></span>](#useapphost)

### <a name="appendtargetframeworktooutputpath"></a><span data-ttu-id="55be6-215">AppendTargetFrameworkToOutputPath</span><span class="sxs-lookup"><span data-stu-id="55be6-215">AppendTargetFrameworkToOutputPath</span></span>

<span data-ttu-id="55be6-216">La propiedad `AppendTargetFrameworkToOutputPath` controla si el [moniker de la plataforma de destino (TFM)](../../standard/frameworks.md) se anexa a la ruta de salida (definida por [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span><span class="sxs-lookup"><span data-stu-id="55be6-216">The `AppendTargetFrameworkToOutputPath` property controls whether the [target framework moniker (TFM)](../../standard/frameworks.md) is appended to the output path (which is defined by [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)).</span></span> <span data-ttu-id="55be6-217">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-217">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="55be6-218">El hecho de establecer `AppendTargetFrameworkToOutputPath` en `false` impide que el TFM se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-218">Setting `AppendTargetFrameworkToOutputPath` to `false` prevents the TFM from being appended to the output path.</span></span> <span data-ttu-id="55be6-219">Sin embargo, sin el TFM en la ruta de salida, es posible que varios artefactos de compilación se sobrescriban entre sí.</span><span class="sxs-lookup"><span data-stu-id="55be6-219">However, without the TFM in the output path, multiple build artifacts may overwrite each other.</span></span>

<span data-ttu-id="55be6-220">Por ejemplo, en el caso de una aplicación de .NET 5.0, la ruta de salida cambia de `bin\Debug\net5.0` a `bin\Debug` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="55be6-220">For example, for a .NET 5.0 app, the output path changes from `bin\Debug\net5.0` to `bin\Debug` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a><span data-ttu-id="55be6-221">AppendRuntimeIdentifierToOutputPath</span><span class="sxs-lookup"><span data-stu-id="55be6-221">AppendRuntimeIdentifierToOutputPath</span></span>

<span data-ttu-id="55be6-222">La propiedad `AppendRuntimeIdentifierToOutputPath` controla si el [id. del entorno de ejecución (RID)](../rid-catalog.md) se anexa a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-222">The `AppendRuntimeIdentifierToOutputPath` property controls whether the [runtime identifier (RID)](../rid-catalog.md) is appended to the output path.</span></span> <span data-ttu-id="55be6-223">El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-223">The .NET SDK automatically appends the target framework and, if present, the runtime identifier to the output path.</span></span> <span data-ttu-id="55be6-224">El hecho de establecer `AppendRuntimeIdentifierToOutputPath` en `false` impide que el RID se anexe a la ruta de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-224">Setting `AppendRuntimeIdentifierToOutputPath` to `false` prevents the RID from being appended to the output path.</span></span>

<span data-ttu-id="55be6-225">Por ejemplo, en el caso de una aplicación de .NET 5.0 y un RID de `win10-x64`, la ruta de salida cambia de `bin\Debug\net5.0\win10-x64` a `bin\Debug\net5.0` con la opción de configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="55be6-225">For example, for a .NET 5.0 app and an RID of `win10-x64`, the output path changes from `bin\Debug\net5.0\win10-x64` to `bin\Debug\net5.0` with the following setting:</span></span>

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a><span data-ttu-id="55be6-226">CopyLocalLockFileAssemblies</span><span class="sxs-lookup"><span data-stu-id="55be6-226">CopyLocalLockFileAssemblies</span></span>

<span data-ttu-id="55be6-227">La propiedad `CopyLocalLockFileAssemblies` es útil para los proyectos de complementos que tienen dependencias de otras bibliotecas.</span><span class="sxs-lookup"><span data-stu-id="55be6-227">The `CopyLocalLockFileAssemblies` property is useful for plugin projects that have dependencies on other libraries.</span></span> <span data-ttu-id="55be6-228">Si establece esta propiedad en `true`, todas las dependencias de paquetes NuGet se copian en el directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-228">If you set this property to `true`, any NuGet package dependencies are copied to the output directory.</span></span> <span data-ttu-id="55be6-229">Esto significa que puede usar la salida de `dotnet build` para ejecutar el complemento en cualquier equipo.</span><span class="sxs-lookup"><span data-stu-id="55be6-229">That means you can use the output of `dotnet build` to run your plugin on any machine.</span></span>

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="55be6-230">Como alternativa, puede usar `dotnet publish` para publicar la biblioteca de clases.</span><span class="sxs-lookup"><span data-stu-id="55be6-230">Alternatively, you can use `dotnet publish` to publish the class library.</span></span> <span data-ttu-id="55be6-231">Para obtener más información, vea [dotnet publish](../tools/dotnet-publish.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-231">For more information, see [dotnet publish](../tools/dotnet-publish.md).</span></span>

### <a name="preservecompilationcontext"></a><span data-ttu-id="55be6-232">PreserveCompilationContext</span><span class="sxs-lookup"><span data-stu-id="55be6-232">PreserveCompilationContext</span></span>

<span data-ttu-id="55be6-233">La propiedad `PreserveCompilationContext` permite a una aplicación creada o publicada compilar más código en tiempo de ejecución con la misma configuración que se utilizó en el momento de la creación.</span><span class="sxs-lookup"><span data-stu-id="55be6-233">The `PreserveCompilationContext` property allows a built or published application to compile more code at run time using the same settings that were used at build time.</span></span> <span data-ttu-id="55be6-234">Los ensamblados a los que se hace referencia en el tiempo de compilación se copiarán en el subdirectorio *ref* del directorio de salida.</span><span class="sxs-lookup"><span data-stu-id="55be6-234">The assemblies referenced at build time will be copied into the *ref* subdirectory of the output directory.</span></span> <span data-ttu-id="55be6-235">Los nombres de los ensamblados de referencia se almacenan en el archivo *.deps.json* de la aplicación junto con las opciones que se pasan al compilador.</span><span class="sxs-lookup"><span data-stu-id="55be6-235">The names of the reference assemblies are stored in the application's *.deps.json* file along with the options passed to the compiler.</span></span> <span data-ttu-id="55be6-236">Puede recuperar esta información mediante las propiedades <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> y <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="55be6-236">You can retrieve this information using the <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> and <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType> properties.</span></span>

<span data-ttu-id="55be6-237">Esta funcionalidad la usan principalmente MVC de ASP.NET Core y páginas Razor para admitir la compilación en tiempo de ejecución de archivos Razor.</span><span class="sxs-lookup"><span data-stu-id="55be6-237">This functionality is mostly used internally by ASP.NET Core MVC and Razor pages to support run-time compilation of Razor files.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationContext>true</PreserveCompilationContext>
</PropertyGroup>
```

### <a name="preservecompilationreferences"></a><span data-ttu-id="55be6-238">PreserveCompilationReferences</span><span class="sxs-lookup"><span data-stu-id="55be6-238">PreserveCompilationReferences</span></span>

<span data-ttu-id="55be6-239">La propiedad `PreserveCompilationReferences` es similar a la propiedad [PreserveCompilationContext](#preservecompilationcontext), salvo que solo copia los ensamblados a los que se hace referencia en el directorio de publicación, sin el archivo *.deps.json*.</span><span class="sxs-lookup"><span data-stu-id="55be6-239">The `PreserveCompilationReferences` property is similar to the [PreserveCompilationContext](#preservecompilationcontext) property, except that it only copies the referenced assemblies to the publish directory, and not the *.deps.json* file.</span></span>

```xml
<PropertyGroup>
  <PreserveCompilationReferences>true</PreserveCompilationReferences>
</PropertyGroup>
```

<span data-ttu-id="55be6-240">Para obtener más información, consulte las [propiedades del SDK de Razor](/aspnet/core/razor-pages/sdk#properties).</span><span class="sxs-lookup"><span data-stu-id="55be6-240">For more information, see [Razor SDK properties](/aspnet/core/razor-pages/sdk#properties).</span></span>

### <a name="runtimeidentifier"></a><span data-ttu-id="55be6-241">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="55be6-241">RuntimeIdentifier</span></span>

<span data-ttu-id="55be6-242">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-242">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="55be6-243">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="55be6-243">The RID enables publishing a self-contained deployment.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="55be6-244">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="55be6-244">RuntimeIdentifiers</span></span>

<span data-ttu-id="55be6-245">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-245">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="55be6-246">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="55be6-246">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="55be6-247">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="55be6-247">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="55be6-248">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="55be6-248">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="useapphost"></a><span data-ttu-id="55be6-249">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="55be6-249">UseAppHost</span></span>

<span data-ttu-id="55be6-250">La propiedad `UseAppHost` controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="55be6-250">The `UseAppHost` property controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="55be6-251">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="55be6-251">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="55be6-252">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="55be6-252">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="55be6-253">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="55be6-253">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

<span data-ttu-id="55be6-254">Para más información sobre la implementación, consulte [Implementación de aplicaciones .NET](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-254">For more information about deployment, see [.NET application deployment](../deploying/index.md).</span></span>

## <a name="compilation-related-properties"></a><span data-ttu-id="55be6-255">Propiedades relacionadas con la compilación</span><span class="sxs-lookup"><span data-stu-id="55be6-255">Compilation-related properties</span></span>

<span data-ttu-id="55be6-256">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-256">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-257">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="55be6-257">EmbeddedResourceUseDependentUponConvention</span></span>](#embeddedresourceusedependentuponconvention)
- [<span data-ttu-id="55be6-258">LangVersion</span><span class="sxs-lookup"><span data-stu-id="55be6-258">LangVersion</span></span>](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a><span data-ttu-id="55be6-259">EmbeddedResourceUseDependentUponConvention</span><span class="sxs-lookup"><span data-stu-id="55be6-259">EmbeddedResourceUseDependentUponConvention</span></span>

<span data-ttu-id="55be6-260">La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos.</span><span class="sxs-lookup"><span data-stu-id="55be6-260">The `EmbeddedResourceUseDependentUponConvention` property defines whether resource manifest file names are generated from type information in source files that are colocated with resource files.</span></span> <span data-ttu-id="55be6-261">Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*.</span><span class="sxs-lookup"><span data-stu-id="55be6-261">For example, if *Form1.resx* is in the same folder as *Form1.cs*, and `EmbeddedResourceUseDependentUponConvention` is set to `true`, the generated *.resources* file takes its name from the first type that's defined in *Form1.cs*.</span></span> <span data-ttu-id="55be6-262">Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.</span><span class="sxs-lookup"><span data-stu-id="55be6-262">For example, if `MyNamespace.Form1` is the first type defined in *Form1.cs*, the generated file name is *MyNamespace.Form1.resources*.</span></span>

> [!NOTE]
> <span data-ttu-id="55be6-263">Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.</span><span class="sxs-lookup"><span data-stu-id="55be6-263">If `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for an `EmbeddedResource` item, the generated manifest file name for that resource file is based on that metadata instead.</span></span>

<span data-ttu-id="55be6-264">De forma predeterminada, en un nuevo proyecto de .NET, esta propiedad se establece en `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-264">By default, in a new .NET project, this property is set to `true`.</span></span> <span data-ttu-id="55be6-265">Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*.</span><span class="sxs-lookup"><span data-stu-id="55be6-265">If set to `false`, and no `LogicalName`, `ManifestResourceName`, or `DependentUpon` metadata is specified for the `EmbeddedResource` item in the project file, the resource manifest file name is based off the root namespace for the project and the relative file path to the *.resx* file.</span></span> <span data-ttu-id="55be6-266">Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-266">For more information, see [How resource manifest files are named](../resources/manifest-file-names.md).</span></span>

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a><span data-ttu-id="55be6-267">LangVersion</span><span class="sxs-lookup"><span data-stu-id="55be6-267">LangVersion</span></span>

<span data-ttu-id="55be6-268">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="55be6-268">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="55be6-269">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="55be6-269">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="55be6-270">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="55be6-270">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="default-item-inclusion-properties"></a><span data-ttu-id="55be6-271">Propiedades de inclusión de elementos predeterminados</span><span class="sxs-lookup"><span data-stu-id="55be6-271">Default item inclusion properties</span></span>

<span data-ttu-id="55be6-272">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-272">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-273">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="55be6-273">DefaultExcludesInProjectFolder</span></span>](#defaultexcludesinprojectfolder)
- [<span data-ttu-id="55be6-274">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="55be6-274">DefaultItemExcludes</span></span>](#defaultitemexcludes)
- [<span data-ttu-id="55be6-275">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="55be6-275">EnableDefaultCompileItems</span></span>](#enabledefaultcompileitems)
- [<span data-ttu-id="55be6-276">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="55be6-276">EnableDefaultEmbeddedResourceItems</span></span>](#enabledefaultembeddedresourceitems)
- [<span data-ttu-id="55be6-277">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="55be6-277">EnableDefaultItems</span></span>](#enabledefaultitems)
- [<span data-ttu-id="55be6-278">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="55be6-278">EnableDefaultNoneItems</span></span>](#enabledefaultnoneitems)

<span data-ttu-id="55be6-279">Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).</span><span class="sxs-lookup"><span data-stu-id="55be6-279">For more information, see [Default includes and excludes](overview.md#default-includes-and-excludes).</span></span>

### <a name="defaultitemexcludes"></a><span data-ttu-id="55be6-280">DefaultItemExcludes</span><span class="sxs-lookup"><span data-stu-id="55be6-280">DefaultItemExcludes</span></span>

<span data-ttu-id="55be6-281">Use la propiedad `DefaultItemExcludes` para definir patrones globales para archivos y carpetas que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="55be6-281">Use the `DefaultItemExcludes` property to define glob patterns for files and folders that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="55be6-282">De forma predeterminada, las carpetas *./bin* y *./obj* se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="55be6-282">By default, the *./bin* and *./obj* folders are excluded from the glob patterns.</span></span>

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a><span data-ttu-id="55be6-283">DefaultExcludesInProjectFolder</span><span class="sxs-lookup"><span data-stu-id="55be6-283">DefaultExcludesInProjectFolder</span></span>

<span data-ttu-id="55be6-284">Use la propiedad `DefaultExcludesInProjectFolder` para definir patrones globales para archivos y carpetas de la carpeta del proyecto que deban excluirse de los patrones globales de inclusión, exclusión y eliminación.</span><span class="sxs-lookup"><span data-stu-id="55be6-284">Use the `DefaultExcludesInProjectFolder` property to define glob patterns for files and folders in the project folder that should be excluded from the include, exclude, and remove globs.</span></span> <span data-ttu-id="55be6-285">De forma predeterminada, las carpetas que empiezan por un punto (`.`), como *.git* y *.vs*, se excluyen de los patrones globales.</span><span class="sxs-lookup"><span data-stu-id="55be6-285">By default, folders that start with a period (`.`), such as *.git* and *.vs*, are excluded from the glob patterns.</span></span>

<span data-ttu-id="55be6-286">Esta propiedad es muy similar a otra, `DefaultItemExcludes`, salvo por el hecho de que esta solo tiene en cuenta los archivos y las carpetas de la carpeta del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-286">This property is very similar to the `DefaultItemExcludes` property, except that it only considers files and folders in the project folder.</span></span> <span data-ttu-id="55be6-287">En el caso de que un patrón global pretenda, de forma no intencionada, relacionar elementos de fuera de la carpeta del proyecto con una ruta de acceso relativa, use la propiedad `DefaultExcludesInProjectFolder`, en lugar de `DefaultItemExcludes`.</span><span class="sxs-lookup"><span data-stu-id="55be6-287">When a glob pattern would unintentionally match items outside the project folder with a relative path, use the `DefaultExcludesInProjectFolder` property instead of the `DefaultItemExcludes` property.</span></span>

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a><span data-ttu-id="55be6-288">EnableDefaultItems</span><span class="sxs-lookup"><span data-stu-id="55be6-288">EnableDefaultItems</span></span>

<span data-ttu-id="55be6-289">La propiedad `EnableDefaultItems` controla si los elementos de compilación, los elementos de los recursos incrustados y los elementos `None` se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="55be6-289">The `EnableDefaultItems` property controls whether compile items, embedded resource items, and `None` items are implicitly included in the project.</span></span> <span data-ttu-id="55be6-290">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-290">The default value is `true`.</span></span> <span data-ttu-id="55be6-291">Establezca la propiedad `EnableDefaultItems` en `false` para deshabilitar toda inclusión de archivos implícita.</span><span class="sxs-lookup"><span data-stu-id="55be6-291">Set the `EnableDefaultItems` property to `false` to disable all implicit file inclusion.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a><span data-ttu-id="55be6-292">EnableDefaultCompileItems</span><span class="sxs-lookup"><span data-stu-id="55be6-292">EnableDefaultCompileItems</span></span>

<span data-ttu-id="55be6-293">La propiedad `EnableDefaultCompileItems` controla si los elementos de compilación se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="55be6-293">The `EnableDefaultCompileItems` property controls whether compile items are implicitly included in the project.</span></span> <span data-ttu-id="55be6-294">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-294">The default value is `true`.</span></span> <span data-ttu-id="55be6-295">Establezca la propiedad `EnableDefaultCompileItems` en `false` para deshabilitar la inclusión implícita de los archivos \*.cs, así como la de otras extensiones de nombres de archivos.</span><span class="sxs-lookup"><span data-stu-id="55be6-295">Set the `EnableDefaultCompileItems` property to `false` to disable implicit inclusion of \*.cs and other language-extension files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a><span data-ttu-id="55be6-296">EnableDefaultEmbeddedResourceItems</span><span class="sxs-lookup"><span data-stu-id="55be6-296">EnableDefaultEmbeddedResourceItems</span></span>

<span data-ttu-id="55be6-297">La propiedad `EnableDefaultEmbeddedResourceItems` controla si los elementos de los recursos incrustados se incluyen en el proyecto de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="55be6-297">The `EnableDefaultEmbeddedResourceItems` property controls whether embedded resource items are implicitly included in the project.</span></span> <span data-ttu-id="55be6-298">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-298">The default value is `true`.</span></span> <span data-ttu-id="55be6-299">Establezca la propiedad `EnableDefaultEmbeddedResourceItems` en `false` para deshabilitar la inclusión implícita de los archivos de los recursos incrustados.</span><span class="sxs-lookup"><span data-stu-id="55be6-299">Set the `EnableDefaultEmbeddedResourceItems` property to `false` to disable implicit inclusion of embedded resource files.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a><span data-ttu-id="55be6-300">EnableDefaultNoneItems</span><span class="sxs-lookup"><span data-stu-id="55be6-300">EnableDefaultNoneItems</span></span>

<span data-ttu-id="55be6-301">La propiedad `EnableDefaultNoneItems` controla si los elementos `None` (archivos que no tienen ningún rol en el proceso de compilación) se incluyen implícitamente en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-301">The `EnableDefaultNoneItems` property controls whether `None` items (files that have no role in the build process) are implicitly included in the project.</span></span> <span data-ttu-id="55be6-302">El valor predeterminado es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-302">The default value is `true`.</span></span> <span data-ttu-id="55be6-303">Establezca la propiedad `EnableDefaultNoneItems` en `false` para deshabilitar la inclusión implícita de elementos `None`.</span><span class="sxs-lookup"><span data-stu-id="55be6-303">Set the `EnableDefaultNoneItems` property to `false` to disable implicit inclusion of `None` items.</span></span>

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a><span data-ttu-id="55be6-304">Propiedades de análisis de código</span><span class="sxs-lookup"><span data-stu-id="55be6-304">Code analysis properties</span></span>

<span data-ttu-id="55be6-305">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-305">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-306">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="55be6-306">AnalysisLevel</span></span>](#analysislevel)
- [<span data-ttu-id="55be6-307">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="55be6-307">AnalysisMode</span></span>](#analysismode)
- [<span data-ttu-id="55be6-308">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="55be6-308">CodeAnalysisTreatWarningsAsErrors</span></span>](#codeanalysistreatwarningsaserrors)
- [<span data-ttu-id="55be6-309">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="55be6-309">EnableNETAnalyzers</span></span>](#enablenetanalyzers)
- [<span data-ttu-id="55be6-310">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="55be6-310">EnforceCodeStyleInBuild</span></span>](#enforcecodestyleinbuild)

### <a name="analysislevel"></a><span data-ttu-id="55be6-311">AnalysisLevel</span><span class="sxs-lookup"><span data-stu-id="55be6-311">AnalysisLevel</span></span>

<span data-ttu-id="55be6-312">La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="55be6-312">The `AnalysisLevel` property lets you specify a code-analysis level.</span></span> <span data-ttu-id="55be6-313">Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="55be6-313">For example, if you want access to preview code analyzers, set `AnalysisLevel` to `preview`.</span></span>

<span data-ttu-id="55be6-314">Valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="55be6-314">Default value:</span></span>

- <span data-ttu-id="55be6-315">Si el proyecto tiene como destino .NET 5.0 o posterior, o si ha agregado la propiedad [AnalysisMode](#analysismode), el valor predeterminado es `latest`.</span><span class="sxs-lookup"><span data-stu-id="55be6-315">If your project targets .NET 5.0 or later, or if you've added the [AnalysisMode](#analysismode) property, the default value is `latest`.</span></span>
- <span data-ttu-id="55be6-316">De lo contrario, se omite esta propiedad, a menos que se agregue explícitamente al archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-316">Otherwise, this property is omitted unless you explicitly add it to the project file.</span></span>

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

<span data-ttu-id="55be6-317">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="55be6-317">The following table shows the available options.</span></span>

| <span data-ttu-id="55be6-318">Value</span><span class="sxs-lookup"><span data-stu-id="55be6-318">Value</span></span> | <span data-ttu-id="55be6-319">Significado</span><span class="sxs-lookup"><span data-stu-id="55be6-319">Meaning</span></span> |
|-|-|
| `latest` | <span data-ttu-id="55be6-320">Se usan los analizadores de código que se han publicado más recientemente.</span><span class="sxs-lookup"><span data-stu-id="55be6-320">The latest code analyzers that have been released are used.</span></span> <span data-ttu-id="55be6-321">Este es el valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="55be6-321">This is the default.</span></span> |
| `preview` | <span data-ttu-id="55be6-322">Se usan los analizadores de código más recientes, incluso si están en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="55be6-322">The latest code analyzers are used, even if they are in preview.</span></span> |
| `5.0` | <span data-ttu-id="55be6-323">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="55be6-323">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |
| `5` | <span data-ttu-id="55be6-324">Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles.</span><span class="sxs-lookup"><span data-stu-id="55be6-324">The set of rules that was enabled for the .NET 5.0 release is used, even if newer rules are available.</span></span> |

> [!NOTE]
> <span data-ttu-id="55be6-325">Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.</span><span class="sxs-lookup"><span data-stu-id="55be6-325">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="analysismode"></a><span data-ttu-id="55be6-326">AnalysisMode</span><span class="sxs-lookup"><span data-stu-id="55be6-326">AnalysisMode</span></span>

<span data-ttu-id="55be6-327">A partir de .NET 5.0, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](../../fundamentals/code-analysis/quality-rules/index.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-327">Starting with .NET 5.0, the .NET SDK ships with all of the ["CA" code quality rules](../../fundamentals/code-analysis/quality-rules/index.md).</span></span> <span data-ttu-id="55be6-328">De forma predeterminada, solo [algunas reglas están habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="55be6-328">By default, only [some rules are enabled](../../fundamentals/code-analysis/overview.md#enabled-rules) as build warnings.</span></span> <span data-ttu-id="55be6-329">La propiedad `AnalysisMode` le permite personalizar el conjunto de reglas que están habilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="55be6-329">The `AnalysisMode` property lets you customize the set of rules that are enabled by default.</span></span> <span data-ttu-id="55be6-330">Puede cambiar a un modo de análisis más agresivo (exclusión) o a uno más conservador (inclusión).</span><span class="sxs-lookup"><span data-stu-id="55be6-330">You can either switch to a more aggressive (opt-out) analysis mode or a more conservative (opt-in) analysis mode.</span></span> <span data-ttu-id="55be6-331">Por ejemplo, si quiere habilitar todas las reglas de forma predeterminada como advertencias de compilación, establezca el valor en `AllEnabledByDefault`.</span><span class="sxs-lookup"><span data-stu-id="55be6-331">For example, if you want to enable all rules by default as build warnings, set the value to `AllEnabledByDefault`.</span></span>

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

<span data-ttu-id="55be6-332">En la siguiente tabla se muestran las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="55be6-332">The following table shows the available options.</span></span>

| <span data-ttu-id="55be6-333">Value</span><span class="sxs-lookup"><span data-stu-id="55be6-333">Value</span></span> | <span data-ttu-id="55be6-334">Significado</span><span class="sxs-lookup"><span data-stu-id="55be6-334">Meaning</span></span> |
|-|-|
| `Default` | <span data-ttu-id="55be6-335">Modo predeterminado, en el que ciertas reglas están habilitadas como advertencias de compilación, otras están habilitadas como sugerencias del IDE de Visual Studio y el resto están deshabilitadas.</span><span class="sxs-lookup"><span data-stu-id="55be6-335">Default mode, where certain rules are enabled as build warnings, certain rules are enabled as Visual Studio IDE suggestions, and the remainder are disabled.</span></span> |
| `AllEnabledByDefault` | <span data-ttu-id="55be6-336">Modo agresivo o de exclusión, en el que todas las reglas están habilitadas de forma predeterminada como advertencias de compilación.</span><span class="sxs-lookup"><span data-stu-id="55be6-336">Aggressive or opt-out mode, where all rules are enabled by default as build warnings.</span></span> <span data-ttu-id="55be6-337">Puede [excluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas.</span><span class="sxs-lookup"><span data-stu-id="55be6-337">You can selectively [opt out](../../fundamentals/code-analysis/configuration-options.md) of individual rules to disable them.</span></span> |
| `AllDisabledByDefault` | <span data-ttu-id="55be6-338">Modo conservador o de inclusión, en el que todas las reglas están deshabilitadas de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="55be6-338">Conservative or opt-in mode, where all rules are disabled by default.</span></span> <span data-ttu-id="55be6-339">Puede [incluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para habilitarlas.</span><span class="sxs-lookup"><span data-stu-id="55be6-339">You can selectively [opt into](../../fundamentals/code-analysis/configuration-options.md) individual rules to enable them.</span></span> |

> [!NOTE]
> <span data-ttu-id="55be6-340">Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.</span><span class="sxs-lookup"><span data-stu-id="55be6-340">This property has no effect on code analysis in projects that don't reference a [project SDK](overview.md), for example, legacy .NET Framework projects that reference the Microsoft.CodeAnalysis.NetAnalyzers NuGet package.</span></span>

### <a name="codeanalysistreatwarningsaserrors"></a><span data-ttu-id="55be6-341">CodeAnalysisTreatWarningsAsErrors</span><span class="sxs-lookup"><span data-stu-id="55be6-341">CodeAnalysisTreatWarningsAsErrors</span></span>

<span data-ttu-id="55be6-342">La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de calidad del código (CAxxxx) se deben tratar como advertencias e interrumpir la compilación.</span><span class="sxs-lookup"><span data-stu-id="55be6-342">The `CodeAnalysisTreatWarningsAsErrors` property lets you configure whether code quality analysis warnings (CAxxxx) should be treated as warnings and break the build.</span></span> <span data-ttu-id="55be6-343">Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) también se tratan como errores.</span><span class="sxs-lookup"><span data-stu-id="55be6-343">If you use the `-warnaserror` flag when you build your projects, [.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) warnings are also treated as errors.</span></span> <span data-ttu-id="55be6-344">Si no quiere que las advertencias de análisis de calidad del código se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-344">If you do not want code quality analysis warnings to be treated as errors, you can set the `CodeAnalysisTreatWarningsAsErrors` MSBuild property to `false` in your project file.</span></span>

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a><span data-ttu-id="55be6-345">EnableNETAnalyzers</span><span class="sxs-lookup"><span data-stu-id="55be6-345">EnableNETAnalyzers</span></span>

<span data-ttu-id="55be6-346">De forma predeterminada, el [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior.</span><span class="sxs-lookup"><span data-stu-id="55be6-346">[.NET code quality analysis](../../fundamentals/code-analysis/overview.md#code-quality-analysis) is enabled, by default, for projects that target .NET 5.0 or later.</span></span> <span data-ttu-id="55be6-347">Puede habilitar el análisis de código de .NET para los proyectos de estilo SDK que tienen como destino versiones anteriores de .NET si establece la propiedad `EnableNETAnalyzers` en `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-347">You can enable .NET code analysis for SDK-style projects that target earlier versions of .NET by setting the `EnableNETAnalyzers` property to `true`.</span></span> <span data-ttu-id="55be6-348">Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.</span><span class="sxs-lookup"><span data-stu-id="55be6-348">To disable code analysis in any project, set this property to `false`.</span></span>

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

> [!NOTE]
> <span data-ttu-id="55be6-349">Esta propiedad se aplica específicamente a los analizadores integrados en el SDK de .NET 5+.</span><span class="sxs-lookup"><span data-stu-id="55be6-349">This property applies specifically to the built-in analyzers in the .NET 5+ SDK.</span></span> <span data-ttu-id="55be6-350">No se debe usar cuando se instala un paquete NuGet de análisis de código.</span><span class="sxs-lookup"><span data-stu-id="55be6-350">It should not be used when you install a NuGet code analysis package.</span></span>

### <a name="enforcecodestyleinbuild"></a><span data-ttu-id="55be6-351">EnforceCodeStyleInBuild</span><span class="sxs-lookup"><span data-stu-id="55be6-351">EnforceCodeStyleInBuild</span></span>

> [!NOTE]
> <span data-ttu-id="55be6-352">En la actualidad, esta característica es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.</span><span class="sxs-lookup"><span data-stu-id="55be6-352">This feature is currently experimental and may change between the .NET 5 and .NET 6 releases.</span></span>

<span data-ttu-id="55be6-353">El [análisis del estilo del código de .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) está deshabilitado de forma predeterminada en la compilación para todos los proyectos de .NET.</span><span class="sxs-lookup"><span data-stu-id="55be6-353">[.NET code style analysis](../../fundamentals/code-analysis/overview.md#code-style-analysis) is disabled, by default, on build for all .NET projects.</span></span> <span data-ttu-id="55be6-354">Puede habilitar el análisis del estilo del código para los proyectos de .NET estableciendo la propiedad `EnforceCodeStyleInBuild` en `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-354">You can enable code style analysis for .NET projects by setting the `EnforceCodeStyleInBuild` property to `true`.</span></span>

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

<span data-ttu-id="55be6-355">Todas las reglas de estilo del código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) como advertencias o errores se ejecutarán en la compilación y notificarán infracciones.</span><span class="sxs-lookup"><span data-stu-id="55be6-355">All code style rules that are [configured](../../fundamentals/code-analysis/overview.md#code-style-analysis) to be warnings or errors will execute on build and report violations.</span></span>

## <a name="run-time-configuration-properties"></a><span data-ttu-id="55be6-356">Propiedades de configuración del tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="55be6-356">Run-time configuration properties</span></span>

<span data-ttu-id="55be6-357">Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="55be6-357">You can configure some run-time behaviors by specifying MSBuild properties in the project file of the app.</span></span> <span data-ttu-id="55be6-358">Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-358">For information about other ways of configuring run-time behavior, see [Run-time configuration settings](../run-time-config/index.md).</span></span>

- [<span data-ttu-id="55be6-359">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-359">ConcurrentGarbageCollection</span></span>](#concurrentgarbagecollection)
- [<span data-ttu-id="55be6-360">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="55be6-360">InvariantGlobalization</span></span>](#invariantglobalization)
- [<span data-ttu-id="55be6-361">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-361">RetainVMGarbageCollection</span></span>](#retainvmgarbagecollection)
- [<span data-ttu-id="55be6-362">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-362">ServerGarbageCollection</span></span>](#servergarbagecollection)
- [<span data-ttu-id="55be6-363">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="55be6-363">ThreadPoolMaxThreads</span></span>](#threadpoolmaxthreads)
- [<span data-ttu-id="55be6-364">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="55be6-364">ThreadPoolMinThreads</span></span>](#threadpoolminthreads)
- [<span data-ttu-id="55be6-365">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="55be6-365">TieredCompilation</span></span>](#tieredcompilation)
- [<span data-ttu-id="55be6-366">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="55be6-366">TieredCompilationQuickJit</span></span>](#tieredcompilationquickjit)
- [<span data-ttu-id="55be6-367">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="55be6-367">TieredCompilationQuickJitForLoops</span></span>](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a><span data-ttu-id="55be6-368">ConcurrentGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-368">ConcurrentGarbageCollection</span></span>

<span data-ttu-id="55be6-369">La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-369">The `ConcurrentGarbageCollection` property configures whether [background (concurrent) garbage collection](../../standard/garbage-collection/background-gc.md) is enabled.</span></span> <span data-ttu-id="55be6-370">Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="55be6-370">Set the value to `false` to disable background garbage collection.</span></span> <span data-ttu-id="55be6-371">Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).</span><span class="sxs-lookup"><span data-stu-id="55be6-371">For more information, see [Background GC](../run-time-config/garbage-collector.md#background-gc).</span></span>

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a><span data-ttu-id="55be6-372">InvariantGlobalization</span><span class="sxs-lookup"><span data-stu-id="55be6-372">InvariantGlobalization</span></span>

<span data-ttu-id="55be6-373">La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="55be6-373">The `InvariantGlobalization` property configures whether the app runs in *globalization-invariant* mode, which means it doesn't have access to culture-specific data.</span></span> <span data-ttu-id="55be6-374">Establezca el valor en `true` para ejecutar en el modo invariable de globalización.</span><span class="sxs-lookup"><span data-stu-id="55be6-374">Set the value to `true` to run in globalization-invariant mode.</span></span> <span data-ttu-id="55be6-375">Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).</span><span class="sxs-lookup"><span data-stu-id="55be6-375">For more information, see [Invariant mode](../run-time-config/globalization.md#invariant-mode).</span></span>

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a><span data-ttu-id="55be6-376">RetainVMGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-376">RetainVMGarbageCollection</span></span>

<span data-ttu-id="55be6-377">La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos.</span><span class="sxs-lookup"><span data-stu-id="55be6-377">The `RetainVMGarbageCollection` property configures the garbage collector to put deleted memory segments on a standby list for future use or release them.</span></span> <span data-ttu-id="55be6-378">Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera.</span><span class="sxs-lookup"><span data-stu-id="55be6-378">Setting the value to `true` tells the garbage collector to put the segments on a standby list.</span></span> <span data-ttu-id="55be6-379">Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).</span><span class="sxs-lookup"><span data-stu-id="55be6-379">For more information, see [Retain VM](../run-time-config/garbage-collector.md#retain-vm).</span></span>

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a><span data-ttu-id="55be6-380">ServerGarbageCollection</span><span class="sxs-lookup"><span data-stu-id="55be6-380">ServerGarbageCollection</span></span>

<span data-ttu-id="55be6-381">La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-381">The `ServerGarbageCollection` property configures whether the application uses [workstation garbage collection or server garbage collection](../../standard/garbage-collection/workstation-server-gc.md).</span></span> <span data-ttu-id="55be6-382">Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor.</span><span class="sxs-lookup"><span data-stu-id="55be6-382">Set the value to `true` to use server garbage collection.</span></span> <span data-ttu-id="55be6-383">Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).</span><span class="sxs-lookup"><span data-stu-id="55be6-383">For more information, see [Workstation vs. server](../run-time-config/garbage-collector.md#workstation-vs-server).</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a><span data-ttu-id="55be6-384">ThreadPoolMaxThreads</span><span class="sxs-lookup"><span data-stu-id="55be6-384">ThreadPoolMaxThreads</span></span>

<span data-ttu-id="55be6-385">La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="55be6-385">The `ThreadPoolMaxThreads` property configures the maximum number of threads for the worker thread pool.</span></span> <span data-ttu-id="55be6-386">Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).</span><span class="sxs-lookup"><span data-stu-id="55be6-386">For more information, see [Maximum threads](../run-time-config/threading.md#maximum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a><span data-ttu-id="55be6-387">ThreadPoolMinThreads</span><span class="sxs-lookup"><span data-stu-id="55be6-387">ThreadPoolMinThreads</span></span>

<span data-ttu-id="55be6-388">La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="55be6-388">The `ThreadPoolMinThreads` property configures the minimum number of threads for the worker thread pool.</span></span> <span data-ttu-id="55be6-389">Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).</span><span class="sxs-lookup"><span data-stu-id="55be6-389">For more information, see [Minimum threads](../run-time-config/threading.md#minimum-threads).</span></span>

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a><span data-ttu-id="55be6-390">TieredCompilation</span><span class="sxs-lookup"><span data-stu-id="55be6-390">TieredCompilation</span></span>

<span data-ttu-id="55be6-391">La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="55be6-391">The `TieredCompilation` property configures whether the just-in-time (JIT) compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span> <span data-ttu-id="55be6-392">Establezca el valor en `false` para deshabilitar la compilación en niveles.</span><span class="sxs-lookup"><span data-stu-id="55be6-392">Set the value to `false` to disable tiered compilation.</span></span> <span data-ttu-id="55be6-393">Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).</span><span class="sxs-lookup"><span data-stu-id="55be6-393">For more information, see [Tiered compilation](../run-time-config/compilation.md#tiered-compilation).</span></span>

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a><span data-ttu-id="55be6-394">TieredCompilationQuickJit</span><span class="sxs-lookup"><span data-stu-id="55be6-394">TieredCompilationQuickJit</span></span>

<span data-ttu-id="55be6-395">La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="55be6-395">The `TieredCompilationQuickJit` property configures whether the JIT compiler uses quick JIT.</span></span> <span data-ttu-id="55be6-396">Establezca el valor en `false` para deshabilitar JIT rápido.</span><span class="sxs-lookup"><span data-stu-id="55be6-396">Set the value to `false` to disable quick JIT.</span></span> <span data-ttu-id="55be6-397">Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).</span><span class="sxs-lookup"><span data-stu-id="55be6-397">For more information, see [Quick JIT](../run-time-config/compilation.md#quick-jit).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a><span data-ttu-id="55be6-398">TieredCompilationQuickJitForLoops</span><span class="sxs-lookup"><span data-stu-id="55be6-398">TieredCompilationQuickJitForLoops</span></span>

<span data-ttu-id="55be6-399">La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="55be6-399">The `TieredCompilationQuickJitForLoops` property configures whether the JIT compiler uses quick JIT on methods that contain loops.</span></span> <span data-ttu-id="55be6-400">Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles.</span><span class="sxs-lookup"><span data-stu-id="55be6-400">Set the value to `true` to enable quick JIT on methods that contain loops.</span></span> <span data-ttu-id="55be6-401">Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).</span><span class="sxs-lookup"><span data-stu-id="55be6-401">For more information, see [Quick JIT for loops](../run-time-config/compilation.md#quick-jit-for-loops).</span></span>

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties"></a><span data-ttu-id="55be6-402">Propiedades de referencia</span><span class="sxs-lookup"><span data-stu-id="55be6-402">Reference properties</span></span>

<span data-ttu-id="55be6-403">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-403">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-404">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="55be6-404">AssetTargetFallback</span></span>](#assettargetfallback)
- [<span data-ttu-id="55be6-405">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="55be6-405">DisableImplicitFrameworkReferences</span></span>](#disableimplicitframeworkreferences)
- [<span data-ttu-id="55be6-406">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="55be6-406">Restore-related properties</span></span>](#restore-related-properties)

### <a name="assettargetfallback"></a><span data-ttu-id="55be6-407">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="55be6-407">AssetTargetFallback</span></span>

<span data-ttu-id="55be6-408">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet.</span><span class="sxs-lookup"><span data-stu-id="55be6-408">The `AssetTargetFallback` property lets you specify additional compatible framework versions for project references and NuGet packages.</span></span> <span data-ttu-id="55be6-409">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="55be6-409">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="55be6-410">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="55be6-410">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span> <span data-ttu-id="55be6-411">Esta propiedad reemplaza la propiedad en desuso `PackageTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="55be6-411">This property replaces the deprecated property `PackageTargetFallback`.</span></span>

<span data-ttu-id="55be6-412">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-frameworks).</span><span class="sxs-lookup"><span data-stu-id="55be6-412">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-frameworks).</span></span>

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a><span data-ttu-id="55be6-413">DisableImplicitFrameworkReferences</span><span class="sxs-lookup"><span data-stu-id="55be6-413">DisableImplicitFrameworkReferences</span></span>

<span data-ttu-id="55be6-414">La propiedad `DisableImplicitFrameworkReferences` controla los elementos `FrameworkReference` implícitos cuando el destino es .NET Core 3.0 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="55be6-414">The `DisableImplicitFrameworkReferences` property controls implicit `FrameworkReference` items when targeting .NET Core 3.0 and later versions.</span></span> <span data-ttu-id="55be6-415">Cuando el destino es .NET Core 2.1 o .NET Standard 2.0 y versiones anteriores, controla los elementos [PackageReference](#packagereference) implícitos en los paquetes de un metapaquete.</span><span class="sxs-lookup"><span data-stu-id="55be6-415">When targeting .NET Core 2.1 or .NET Standard 2.0 and earlier versions, it controls implicit [PackageReference](#packagereference) items to packages in a metapackage.</span></span> <span data-ttu-id="55be6-416">(Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes). Esta propiedad también controla las referencias implícitas como `System` y `System.Core` cuando el destino es .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="55be6-416">(A metapackage is a framework-based package that consist only of dependencies on other packages.) This property also controls implicit references such as `System` and `System.Core` when targeting .NET Framework.</span></span>

<span data-ttu-id="55be6-417">Establezca esta propiedad en `true` para deshabilitar los elementos `FrameworkReference` o [PackageReference](#packagereference) implícitos.</span><span class="sxs-lookup"><span data-stu-id="55be6-417">Set this property to `true` to disable implicit `FrameworkReference` or [PackageReference](#packagereference) items.</span></span> <span data-ttu-id="55be6-418">Si establece esta propiedad en `true`, puede agregar referencias explícitas solo a las plataformas o paquetes que necesite.</span><span class="sxs-lookup"><span data-stu-id="55be6-418">If you set this property to `true`, you can add explicit references to just the frameworks or packages you need.</span></span>

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="restore-related-properties"></a><span data-ttu-id="55be6-419">Propiedades relacionadas con la restauración</span><span class="sxs-lookup"><span data-stu-id="55be6-419">Restore-related properties</span></span>

<span data-ttu-id="55be6-420">La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias.</span><span class="sxs-lookup"><span data-stu-id="55be6-420">Restoring a referenced package installs all of its direct dependencies and all the dependencies of those dependencies.</span></span> <span data-ttu-id="55be6-421">Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`.</span><span class="sxs-lookup"><span data-stu-id="55be6-421">You can customize package restoration by specifying properties such as `RestorePackagesPath` and `RestoreIgnoreFailedSources`.</span></span> <span data-ttu-id="55be6-422">Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).</span><span class="sxs-lookup"><span data-stu-id="55be6-422">For more information about these and other properties, see [restore target](/nuget/reference/msbuild-targets#restore-target).</span></span>

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-related-properties"></a><span data-ttu-id="55be6-423">Propiedades relacionadas con la ejecución</span><span class="sxs-lookup"><span data-stu-id="55be6-423">Run-related properties</span></span>

<span data-ttu-id="55be6-424">Las siguientes propiedades se usan para iniciar una aplicación con el comando [`dotnet run`](../tools/dotnet-run.md):</span><span class="sxs-lookup"><span data-stu-id="55be6-424">The following properties are used for launching an app with the [`dotnet run`](../tools/dotnet-run.md) command:</span></span>

- [<span data-ttu-id="55be6-425">RunArguments</span><span class="sxs-lookup"><span data-stu-id="55be6-425">RunArguments</span></span>](#runarguments)
- [<span data-ttu-id="55be6-426">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="55be6-426">RunWorkingDirectory</span></span>](#runworkingdirectory)

### <a name="runarguments"></a><span data-ttu-id="55be6-427">RunArguments</span><span class="sxs-lookup"><span data-stu-id="55be6-427">RunArguments</span></span>

<span data-ttu-id="55be6-428">La propiedad `RunArguments` define los argumentos que se pasan a la aplicación cuando se ejecuta.</span><span class="sxs-lookup"><span data-stu-id="55be6-428">The `RunArguments` property defines the arguments that are passed to the app when it is run.</span></span>

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> <span data-ttu-id="55be6-429">Puede especificar los argumentos adicionales que se pasarán a la aplicación mediante la opción [`--` para `dotnet run`](../tools/dotnet-run.md#options).</span><span class="sxs-lookup"><span data-stu-id="55be6-429">You can specify additional arguments to be passed to the app by using the [`--` option for `dotnet run`](../tools/dotnet-run.md#options).</span></span>

### <a name="runworkingdirectory"></a><span data-ttu-id="55be6-430">RunWorkingDirectory</span><span class="sxs-lookup"><span data-stu-id="55be6-430">RunWorkingDirectory</span></span>

<span data-ttu-id="55be6-431">La propiedad `RunWorkingDirectory` define el directorio de trabajo en el que se iniciará el proceso.</span><span class="sxs-lookup"><span data-stu-id="55be6-431">The `RunWorkingDirectory` property defines the working directory for the application process to be started in.</span></span> <span data-ttu-id="55be6-432">Puede ser una ruta de acceso absoluta o relativa al directorio del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-432">It can be an absolute path or a path that's relative to the project directory.</span></span> <span data-ttu-id="55be6-433">Si no se especifica un directorio, se usa `OutDir` como directorio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="55be6-433">If you don't specify a directory, `OutDir` is used as the working directory.</span></span>

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-related-properties"></a><span data-ttu-id="55be6-434">Propiedades relacionadas con el hospedaje</span><span class="sxs-lookup"><span data-stu-id="55be6-434">Hosting-related properties</span></span>

<span data-ttu-id="55be6-435">En esta sección se documentan las siguientes propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="55be6-435">The following MSBuild properties are documented in this section:</span></span>

- [<span data-ttu-id="55be6-436">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="55be6-436">EnableComHosting</span></span>](#enablecomhosting)
- [<span data-ttu-id="55be6-437">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="55be6-437">EnableDynamicLoading</span></span>](#enabledynamicloading)

### <a name="enablecomhosting"></a><span data-ttu-id="55be6-438">EnableComHosting</span><span class="sxs-lookup"><span data-stu-id="55be6-438">EnableComHosting</span></span>

<span data-ttu-id="55be6-439">La propiedad `EnableComHosting` indica que un ensamblado proporciona un servidor COM.</span><span class="sxs-lookup"><span data-stu-id="55be6-439">The `EnableComHosting` property indicates that an assembly provides a COM server.</span></span> <span data-ttu-id="55be6-440">Al establecer `EnableComHosting` en `true` también implica que [EnableDynamicLoading](#enabledynamicloading) es `true`.</span><span class="sxs-lookup"><span data-stu-id="55be6-440">Setting the `EnableComHosting` to `true` also implies that [EnableDynamicLoading](#enabledynamicloading) is `true`.</span></span>

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

<span data-ttu-id="55be6-441">Para obtener más información, vea [Exposición de componentes de .NET en COM](../native-interop/expose-components-to-com.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-441">For more information, see [Expose .NET components to COM](../native-interop/expose-components-to-com.md).</span></span>

### <a name="enabledynamicloading"></a><span data-ttu-id="55be6-442">EnableDynamicLoading</span><span class="sxs-lookup"><span data-stu-id="55be6-442">EnableDynamicLoading</span></span>

<span data-ttu-id="55be6-443">La propiedad `EnableDynamicLoading` indica que un ensamblado es un componente cargado dinámicamente.</span><span class="sxs-lookup"><span data-stu-id="55be6-443">The `EnableDynamicLoading` property indicates that an assembly is a dynamically loaded component.</span></span> <span data-ttu-id="55be6-444">El componente podría ser una [biblioteca de COM](/windows/win32/com/the-component-object-model) o una biblioteca que no es de COM que se puede [usar desde un host nativo](../tutorials/netcore-hosting.md).</span><span class="sxs-lookup"><span data-stu-id="55be6-444">The component could be a [COM library](/windows/win32/com/the-component-object-model) or a non-COM library that can be [used from a native host](../tutorials/netcore-hosting.md).</span></span> <span data-ttu-id="55be6-445">Establecer esta propiedad en `true` tiene los efectos siguientes:</span><span class="sxs-lookup"><span data-stu-id="55be6-445">Setting this property to `true` has the following effects:</span></span>

- <span data-ttu-id="55be6-446">Se genera un archivo *runtimeconfig.json*.</span><span class="sxs-lookup"><span data-stu-id="55be6-446">A *.runtimeconfig.json* file is generated.</span></span>
- <span data-ttu-id="55be6-447">La [puesta al día](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) se establece en `LatestMinor`.</span><span class="sxs-lookup"><span data-stu-id="55be6-447">[Roll forward](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) is set to `LatestMinor`.</span></span>
- <span data-ttu-id="55be6-448">Las referencias de NuGet se copian localmente.</span><span class="sxs-lookup"><span data-stu-id="55be6-448">NuGet references are copied locally.</span></span>

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="items"></a><span data-ttu-id="55be6-449">Elementos</span><span class="sxs-lookup"><span data-stu-id="55be6-449">Items</span></span>

<span data-ttu-id="55be6-450">Los [elementos de MSBuild](/visualstudio/msbuild/msbuild-items) son entradas al sistema de compilación.</span><span class="sxs-lookup"><span data-stu-id="55be6-450">[MSBuild items](/visualstudio/msbuild/msbuild-items) are inputs into the build system.</span></span> <span data-ttu-id="55be6-451">Los elementos se especifican de acuerdo con su tipo, que es el nombre del elemento.</span><span class="sxs-lookup"><span data-stu-id="55be6-451">Items are specified according to their type, which is the element name.</span></span> <span data-ttu-id="55be6-452">Por ejemplo, `Compile` y `Reference` son dos [tipos de elementos comunes](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="55be6-452">For example, `Compile` and `Reference` are two [common item types](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="55be6-453">El SDK de .NET pone a disposición los siguientes tipos de elementos adicionales:</span><span class="sxs-lookup"><span data-stu-id="55be6-453">The following additional item types are made available by the .NET SDK:</span></span>

- [<span data-ttu-id="55be6-454">PackageReference</span><span class="sxs-lookup"><span data-stu-id="55be6-454">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="55be6-455">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="55be6-455">TrimmerRootAssembly</span></span>](#trimmerrootassembly)

<span data-ttu-id="55be6-456">Puede usar cualquiera de los [atributos de elementos](/visualstudio/msbuild/item-element-msbuild#attributes-and-elements) estándar, por ejemplo, `Include` y `Update`, en dichos elementos.</span><span class="sxs-lookup"><span data-stu-id="55be6-456">You can use any of the standard [item attributes](/visualstudio/msbuild/item-element-msbuild#attributes-and-elements), for example, `Include` and `Update`, on these items.</span></span> <span data-ttu-id="55be6-457">Use `Include` para agregar un nuevo elemento; y `Update`, para modificar uno existente.</span><span class="sxs-lookup"><span data-stu-id="55be6-457">Use `Include` to add a new item, and use `Update` to modify an existing item.</span></span> <span data-ttu-id="55be6-458">Por ejemplo, `Update` se suele usar para modificar un elemento que el SDK de .NET ha agregado de forma implícita.</span><span class="sxs-lookup"><span data-stu-id="55be6-458">For example, `Update` is often used to modify an item that has implicitly been added by the .NET SDK.</span></span>

### <a name="packagereference"></a><span data-ttu-id="55be6-459">PackageReference</span><span class="sxs-lookup"><span data-stu-id="55be6-459">PackageReference</span></span>

<span data-ttu-id="55be6-460">El elemento `PackageReference` define una referencia a un paquete NuGet.</span><span class="sxs-lookup"><span data-stu-id="55be6-460">The `PackageReference` item defines a reference to a NuGet package.</span></span>

<span data-ttu-id="55be6-461">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="55be6-461">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="55be6-462">El atributo `Version` especifica la versión o el intervalo de versiones.</span><span class="sxs-lookup"><span data-stu-id="55be6-462">The `Version` attribute specifies the version or version range.</span></span> <span data-ttu-id="55be6-463">Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges).</span><span class="sxs-lookup"><span data-stu-id="55be6-463">For information about how to specify a minimum version, maximum version, range, or exact match, see [Version ranges](/nuget/concepts/package-versioning#version-ranges).</span></span>

<span data-ttu-id="55be6-464">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="55be6-464">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

<span data-ttu-id="55be6-465">También puede [controlar los recursos de las dependencias](/nuget/consume-packages/package-references-in-project-files#controlling-dependency-assets) mediante metadatos como `PrivateAssets`.</span><span class="sxs-lookup"><span data-stu-id="55be6-465">You can also [control dependency assets](/nuget/consume-packages/package-references-in-project-files#controlling-dependency-assets) using metadata such as `PrivateAssets`.</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Contoso.Utility.UsefulStuff" Version="3.6.0">
    <PrivateAssets>all</PrivateAssets>
  </PackageReference>
</ItemGroup>
```

<span data-ttu-id="55be6-466">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="55be6-466">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="trimmerrootassembly"></a><span data-ttu-id="55be6-467">TrimmerRootAssembly</span><span class="sxs-lookup"><span data-stu-id="55be6-467">TrimmerRootAssembly</span></span>

<span data-ttu-id="55be6-468">El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado.</span><span class="sxs-lookup"><span data-stu-id="55be6-468">The `TrimmerRootAssembly` item lets you exclude an assembly from [*trimming*](../deploying/trim-self-contained.md).</span></span> <span data-ttu-id="55be6-469">El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="55be6-469">Trimming is the process of removing unused parts of the runtime from a packaged application.</span></span> <span data-ttu-id="55be6-470">En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.</span><span class="sxs-lookup"><span data-stu-id="55be6-470">In some cases, trimming might incorrectly remove required references.</span></span>

<span data-ttu-id="55be6-471">El siguiente código XML excluye del recorte el ensamblado `System.Security`.</span><span class="sxs-lookup"><span data-stu-id="55be6-471">The following XML excludes the `System.Security` assembly from trimming.</span></span>

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

## <a name="item-metadata"></a><span data-ttu-id="55be6-472">Metadatos de elementos</span><span class="sxs-lookup"><span data-stu-id="55be6-472">Item metadata</span></span>

<span data-ttu-id="55be6-473">Además de los [atributos de los elementos de MSBuild](/visualstudio/msbuild/item-element-msbuild#attributes-and-elements) estándar, el SDK de .NET pone a disposición las siguientes etiquetas de metadatos de los elementos:</span><span class="sxs-lookup"><span data-stu-id="55be6-473">In addition to the standard [MSBuild item attributes](/visualstudio/msbuild/item-element-msbuild#attributes-and-elements), the following item metadata tags are made available by the .NET SDK:</span></span>

- [<span data-ttu-id="55be6-474">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="55be6-474">CopyToPublishDirectory</span></span>](#copytopublishdirectory)
- [<span data-ttu-id="55be6-475">LinkBase</span><span class="sxs-lookup"><span data-stu-id="55be6-475">LinkBase</span></span>](#linkbase)

### <a name="copytopublishdirectory"></a><span data-ttu-id="55be6-476">CopyToPublishDirectory</span><span class="sxs-lookup"><span data-stu-id="55be6-476">CopyToPublishDirectory</span></span>

<span data-ttu-id="55be6-477">Los metadatos de `CopyToPublishDirectory` relativos a un elemento de MSBuild controlan cuándo se copia el elemento en el directorio de publicación.</span><span class="sxs-lookup"><span data-stu-id="55be6-477">The `CopyToPublishDirectory` metadata on an MSBuild item controls when the item is copied to the publish directory.</span></span> <span data-ttu-id="55be6-478">Los valores permitidos son `PreserveNewest`, que solo copia el elemento si ha cambiado; `Always`, que siempre lo copia; y `Never`, que nunca lo hace.</span><span class="sxs-lookup"><span data-stu-id="55be6-478">Allowable values are `PreserveNewest`, which only copies the item if it has changed, `Always`, which always copies the item, and `Never`, which never copies the item.</span></span> <span data-ttu-id="55be6-479">Desde el punto de vista del rendimiento, `PreserveNewest` es preferible porque permite una compilación incremental.</span><span class="sxs-lookup"><span data-stu-id="55be6-479">From a performance standpoint, `PreserveNewest` is preferable because it enables an incremental build.</span></span>

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a><span data-ttu-id="55be6-480">LinkBase</span><span class="sxs-lookup"><span data-stu-id="55be6-480">LinkBase</span></span>

<span data-ttu-id="55be6-481">En el caso de un elemento situado fuera del directorio del proyecto y sus subdirectorios, el destino de publicación usa los [metadatos de Link](/visualstudio/msbuild/common-msbuild-item-metadata) del elemento para determinar dónde se debe copiar este.</span><span class="sxs-lookup"><span data-stu-id="55be6-481">For an item that's outside of the project directory and its subdirectories, the publish target uses the item's [Link metadata](/visualstudio/msbuild/common-msbuild-item-metadata) to determine where to copy the item to.</span></span> <span data-ttu-id="55be6-482">`Link` también determina cómo se muestran los elementos situados fuera del árbol del proyecto en la ventana Explorador de soluciones de Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="55be6-482">`Link` also determines how items outside of the project tree are displayed in the Solution Explorer window of Visual Studio.</span></span>

<span data-ttu-id="55be6-483">Si no se especifica `Link` para un elemento situado fuera del cono del proyecto, este tiene `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)` como valor predeterminado.</span><span class="sxs-lookup"><span data-stu-id="55be6-483">If `Link` is not specified for an item that's outside of the project cone, it defaults to `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)`.</span></span> <span data-ttu-id="55be6-484">`LinkBase` permite especificar una carpeta base razonable para los elementos situados fuera del cono del proyecto.</span><span class="sxs-lookup"><span data-stu-id="55be6-484">`LinkBase` lets you specify a sensible base folder for items outside of the project cone.</span></span> <span data-ttu-id="55be6-485">La jerarquía de carpetas de la carpeta base se conserva por medio de `RecursiveDir`.</span><span class="sxs-lookup"><span data-stu-id="55be6-485">The folder hierarchy under the base folder is preserved via `RecursiveDir`.</span></span> <span data-ttu-id="55be6-486">Si no se especifica `LinkBase`, se omite de la ruta a `Link`.</span><span class="sxs-lookup"><span data-stu-id="55be6-486">If `LinkBase` is not specified, it's omitted from the `Link` path.</span></span>

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

<span data-ttu-id="55be6-487">En la imagen siguiente, se ilustra cómo se muestra globalmente un archivo incluido en el elemento anterior `Include` en el Explorador de soluciones.</span><span class="sxs-lookup"><span data-stu-id="55be6-487">The following image shows how a file that's included via the previous item `Include` glob displays in Solution Explorer.</span></span>

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="Elemento con metadatos de LinkBase en el Explorador de soluciones.":::

## <a name="see-also"></a><span data-ttu-id="55be6-489">Vea también</span><span class="sxs-lookup"><span data-stu-id="55be6-489">See also</span></span>

- [<span data-ttu-id="55be6-490">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="55be6-490">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="55be6-491">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="55be6-491">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="55be6-492">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="55be6-492">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="55be6-493">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="55be6-493">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="55be6-494">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="55be6-494">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
