---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades de MSBuild admitidas por el SDK de .NET Core.
ms.date: 02/14/2020
ms.topic: reference
ms.openlocfilehash: d4a204a1e0216313418d278ec3bd333f72db8751
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "81386661"
---
# <a name="msbuild-properties-for-net-core-sdk-projects"></a><span data-ttu-id="78190-103">Propiedades de MSBuild para proyectos del SDK de .NET Core</span><span class="sxs-lookup"><span data-stu-id="78190-103">MSBuild properties for .NET Core SDK projects</span></span>

<span data-ttu-id="78190-104">En esta página se describen las propiedades de MSBuild para configurar proyectos de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78190-104">This page describes MSBuild properties for configuring .NET Core projects.</span></span>

> [!NOTE]
> <span data-ttu-id="78190-105">Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78190-105">This page is a work in progress and does not list all of the useful MSBuild properties for the .NET Core SDK.</span></span> <span data-ttu-id="78190-106">Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).</span><span class="sxs-lookup"><span data-stu-id="78190-106">For a list of common MSBuild properties, see [Common MSBuild properties](/visualstudio/msbuild/common-msbuild-project-properties).</span></span>

## <a name="framework-properties"></a><span data-ttu-id="78190-107">Propiedades del marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="78190-107">Framework properties</span></span>

- [<span data-ttu-id="78190-108">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="78190-108">TargetFramework</span></span>](#targetframework)
- [<span data-ttu-id="78190-109">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="78190-109">TargetFrameworks</span></span>](#targetframeworks)
- [<span data-ttu-id="78190-110">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="78190-110">NetStandardImplicitPackageVersion</span></span>](#netstandardimplicitpackageversion)

### <a name="targetframework"></a><span data-ttu-id="78190-111">TargetFramework</span><span class="sxs-lookup"><span data-stu-id="78190-111">TargetFramework</span></span>

<span data-ttu-id="78190-112">La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación, que hace referencia de forma implícita a un [metapaquete](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="78190-112">The `TargetFramework` property specifies the target framework version for the app, which implicitly references a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="78190-113">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="78190-113">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="78190-114">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="78190-114">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="targetframeworks"></a><span data-ttu-id="78190-115">TargetFrameworks</span><span class="sxs-lookup"><span data-stu-id="78190-115">TargetFrameworks</span></span>

<span data-ttu-id="78190-116">Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino.</span><span class="sxs-lookup"><span data-stu-id="78190-116">Use the `TargetFrameworks` property when you want your app to target multiple platforms.</span></span> <span data-ttu-id="78190-117">Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="78190-117">For a list of valid target framework monikers, see [Target frameworks in SDK-style projects](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

> [!NOTE]
> <span data-ttu-id="78190-118">Esta propiedad se omite si se especifica `TargetFramework` (singular).</span><span class="sxs-lookup"><span data-stu-id="78190-118">This property is ignored if `TargetFramework` (singular) is specified.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="78190-119">Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).</span><span class="sxs-lookup"><span data-stu-id="78190-119">For more information, see [Target frameworks in SDK-style projects](../../standard/frameworks.md).</span></span>

### <a name="netstandardimplicitpackageversion"></a><span data-ttu-id="78190-120">NetStandardImplicitPackageVersion</span><span class="sxs-lookup"><span data-stu-id="78190-120">NetStandardImplicitPackageVersion</span></span>

> [!NOTE]
> <span data-ttu-id="78190-121">Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`.</span><span class="sxs-lookup"><span data-stu-id="78190-121">This property only applies to projects using `netstandard1.x`.</span></span> <span data-ttu-id="78190-122">No se aplica a los que usan `netstandard2.x`.</span><span class="sxs-lookup"><span data-stu-id="78190-122">It doesn't apply to projects that use `netstandard2.x`.</span></span>

<span data-ttu-id="78190-123">Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión de la plataforma anterior a la del [metapaquete](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="78190-123">Use the `NetStandardImplicitPackageVersion` property when you want to specify a framework version that's lower than the [metapackage](../packages.md#metapackages) version.</span></span> <span data-ttu-id="78190-124">El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.</span><span class="sxs-lookup"><span data-stu-id="78190-124">The project file in the following example targets `netstandard1.3` but uses the 1.6.0 version of `NETStandard.Library`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a><span data-ttu-id="78190-125">Publicación de propiedades</span><span class="sxs-lookup"><span data-stu-id="78190-125">Publish properties</span></span>

- [<span data-ttu-id="78190-126">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="78190-126">RuntimeIdentifier</span></span>](#runtimeidentifier)
- [<span data-ttu-id="78190-127">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="78190-127">RuntimeIdentifiers</span></span>](#runtimeidentifiers)
- [<span data-ttu-id="78190-128">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="78190-128">UseAppHost</span></span>](#useapphost)

### <a name="runtimeidentifier"></a><span data-ttu-id="78190-129">RuntimeIdentifier</span><span class="sxs-lookup"><span data-stu-id="78190-129">RuntimeIdentifier</span></span>

<span data-ttu-id="78190-130">La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="78190-130">The `RuntimeIdentifier` property lets you specify a single [runtime identifier (RID)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="78190-131">El RID permite publicar una implementación autocontenida.</span><span class="sxs-lookup"><span data-stu-id="78190-131">The RID enables publishing a self-contained deployment.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a><span data-ttu-id="78190-132">RuntimeIdentifiers</span><span class="sxs-lookup"><span data-stu-id="78190-132">RuntimeIdentifiers</span></span>

<span data-ttu-id="78190-133">La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto.</span><span class="sxs-lookup"><span data-stu-id="78190-133">The `RuntimeIdentifiers` property lets you specify a semicolon-delimited list of [runtime identifiers (RIDs)](../rid-catalog.md) for the project.</span></span> <span data-ttu-id="78190-134">Use esta propiedad si tiene que publicar para varios entornos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="78190-134">Use this property if you need to publish for multiple runtimes.</span></span> <span data-ttu-id="78190-135">`RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.</span><span class="sxs-lookup"><span data-stu-id="78190-135">`RuntimeIdentifiers` is used at restore time to ensure the right assets are in the graph.</span></span>

> [!TIP]
> <span data-ttu-id="78190-136">`RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.</span><span class="sxs-lookup"><span data-stu-id="78190-136">`RuntimeIdentifier` (singular) can provide faster builds when only a single runtime is required.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a><span data-ttu-id="78190-137">UseAppHost</span><span class="sxs-lookup"><span data-stu-id="78190-137">UseAppHost</span></span>

<span data-ttu-id="78190-138">La propiedad `UseAppHost` se presentó en la versión 2.1.400 del SDK de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="78190-138">The `UseAppHost` property was introduced in the 2.1.400 version of the .NET Core SDK.</span></span> <span data-ttu-id="78190-139">Controla si se crea o no un archivo ejecutable nativo para una implementación.</span><span class="sxs-lookup"><span data-stu-id="78190-139">It controls whether or not a native executable is created for a deployment.</span></span> <span data-ttu-id="78190-140">Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.</span><span class="sxs-lookup"><span data-stu-id="78190-140">A native executable is required for self-contained deployments.</span></span>

<span data-ttu-id="78190-141">En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="78190-141">In .NET Core 3.0 and later versions, a framework-dependent executable is created by default.</span></span> <span data-ttu-id="78190-142">Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.</span><span class="sxs-lookup"><span data-stu-id="78190-142">Set the `UseAppHost` property to `false` to disable generation of the executable.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="78190-143">Para obtener más información sobre la implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).</span><span class="sxs-lookup"><span data-stu-id="78190-143">For more information about deployment, see [.NET Core application deployment](../deploying/index.md).</span></span>

## <a name="compile-properties"></a><span data-ttu-id="78190-144">Propiedades de compilación</span><span class="sxs-lookup"><span data-stu-id="78190-144">Compile properties</span></span>

### <a name="langversion"></a><span data-ttu-id="78190-145">LangVersion</span><span class="sxs-lookup"><span data-stu-id="78190-145">LangVersion</span></span>

<span data-ttu-id="78190-146">La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación.</span><span class="sxs-lookup"><span data-stu-id="78190-146">The `LangVersion` property lets you specify a specific programming language version.</span></span> <span data-ttu-id="78190-147">Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.</span><span class="sxs-lookup"><span data-stu-id="78190-147">For example, if you want access to C# preview features, set `LangVersion` to `preview`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="78190-148">Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).</span><span class="sxs-lookup"><span data-stu-id="78190-148">For more information, see [C# language versioning](../../csharp/language-reference/configure-language-version.md#override-a-default).</span></span>

## <a name="nuget-packages"></a><span data-ttu-id="78190-149">Paquetes NuGet</span><span class="sxs-lookup"><span data-stu-id="78190-149">NuGet packages</span></span>

- [<span data-ttu-id="78190-150">PackageReference</span><span class="sxs-lookup"><span data-stu-id="78190-150">PackageReference</span></span>](#packagereference)
- [<span data-ttu-id="78190-151">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="78190-151">AssetTargetFallback</span></span>](#assettargetfallback)

### <a name="packagereference"></a><span data-ttu-id="78190-152">PackageReference</span><span class="sxs-lookup"><span data-stu-id="78190-152">PackageReference</span></span>

<span data-ttu-id="78190-153">El elemento `PackageReference` permite especificar una dependencia de NuGet.</span><span class="sxs-lookup"><span data-stu-id="78190-153">The `PackageReference` item lets you specify a NuGet dependency.</span></span> <span data-ttu-id="78190-154">Por ejemplo, es posible que quiera hacer referencia a un único paquete en lugar de a un [metapaquete](../packages.md#metapackages).</span><span class="sxs-lookup"><span data-stu-id="78190-154">For example, you may want to reference a single package instead of a [metapackage](../packages.md#metapackages).</span></span> <span data-ttu-id="78190-155">El atributo `Include` especifica el identificador del paquete.</span><span class="sxs-lookup"><span data-stu-id="78190-155">The `Include` attribute specifies the package ID.</span></span> <span data-ttu-id="78190-156">El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).</span><span class="sxs-lookup"><span data-stu-id="78190-156">The project file snippet in the following example references the [System.Runtime](https://www.nuget.org/packages/System.Runtime/) package.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

<span data-ttu-id="78190-157">Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).</span><span class="sxs-lookup"><span data-stu-id="78190-157">For more information, see [Package references in project files](/nuget/consume-packages/package-references-in-project-files).</span></span>

### <a name="assettargetfallback"></a><span data-ttu-id="78190-158">AssetTargetFallback</span><span class="sxs-lookup"><span data-stu-id="78190-158">AssetTargetFallback</span></span>

<span data-ttu-id="78190-159">La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para los proyectos a los que el proyecto hace referencia, y los paquetes NuGet que consume el proyecto.</span><span class="sxs-lookup"><span data-stu-id="78190-159">The `AssetTargetFallback` property lets you specify additional compatible framework versions for projects that your project references and NuGet packages that your project consumes.</span></span> <span data-ttu-id="78190-160">Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="78190-160">For example, if you specify a package dependency using `PackageReference` but that package doesn't contain assets that are compatible with your projects's `TargetFramework`, the `AssetTargetFallback` property comes into play.</span></span> <span data-ttu-id="78190-161">La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.</span><span class="sxs-lookup"><span data-stu-id="78190-161">The compatibility of the referenced package is rechecked using each target framework that's specified in `AssetTargetFallback`.</span></span>

<span data-ttu-id="78190-162">Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-framework-versions).</span><span class="sxs-lookup"><span data-stu-id="78190-162">You can set the `AssetTargetFallback` property to one or more [target framework versions](../../standard/frameworks.md#supported-target-framework-versions).</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a><span data-ttu-id="78190-163">Destinos pack y restore</span><span class="sxs-lookup"><span data-stu-id="78190-163">Pack and restore targets</span></span>

<span data-ttu-id="78190-164">En MSBuild 15.1 se presentaron los destinos `pack` y `restore` para crear y restaurar paquetes NuGet como parte de una compilación.</span><span class="sxs-lookup"><span data-stu-id="78190-164">MSBuild 15.1 introduced `pack` and `restore` targets for creating and restoring NuGet packages as part of a build.</span></span> <span data-ttu-id="78190-165">Para obtener información sobre las propiedades de MSBuild para estos destinos, incluido `PackageTargetFallback`, vea [pack y restore de NuGet como destinos de MSBuild](/nuget/reference/msbuild-targets).</span><span class="sxs-lookup"><span data-stu-id="78190-165">For information about the MSBuild properties for these targets, including `PackageTargetFallback`, see [NuGet pack and restore as MSBuild targets](/nuget/reference/msbuild-targets).</span></span>

## <a name="see-also"></a><span data-ttu-id="78190-166">Vea también</span><span class="sxs-lookup"><span data-stu-id="78190-166">See also</span></span>

- [<span data-ttu-id="78190-167">Referencia del esquema de MSBuild</span><span class="sxs-lookup"><span data-stu-id="78190-167">MSBuild schema reference</span></span>](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [<span data-ttu-id="78190-168">Propiedades comunes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="78190-168">Common MSBuild properties</span></span>](/visualstudio/msbuild/common-msbuild-project-properties)
- [<span data-ttu-id="78190-169">Propiedades de MSBuild para pack de NuGet</span><span class="sxs-lookup"><span data-stu-id="78190-169">MSBuild properties for NuGet pack</span></span>](/nuget/reference/msbuild-targets#pack-target)
- [<span data-ttu-id="78190-170">Propiedades de MSBuild para restore de NuGet</span><span class="sxs-lookup"><span data-stu-id="78190-170">MSBuild properties for NuGet restore</span></span>](/nuget/reference/msbuild-targets#restore-properties)
- [<span data-ttu-id="78190-171">Personalización de una compilación</span><span class="sxs-lookup"><span data-stu-id="78190-171">Customize a build</span></span>](/visualstudio/msbuild/customize-your-build)
