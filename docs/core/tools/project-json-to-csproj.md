---
title: Comparación entre project.json y csproj
description: Vea una asignación entre los elementos project.json y csproj.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: c31590cf34990867b81af4d073846c2952928798
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714135"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a><span data-ttu-id="010ce-103">Una asignación entre propiedades project.json y csproj</span><span class="sxs-lookup"><span data-stu-id="010ce-103">A mapping between project.json and csproj properties</span></span>

<span data-ttu-id="010ce-104">Por [Nate McMaster](https://github.com/natemcmaster)</span><span class="sxs-lookup"><span data-stu-id="010ce-104">By [Nate McMaster](https://github.com/natemcmaster)</span></span>

<span data-ttu-id="010ce-105">Durante el desarrollo de las herramientas de .NET Core, se realizó un cambio de diseño importante para dejar de admitir los archivos *project.json* y trasladar en su lugar los proyectos .NET Core al formato MSBuild/csproj.</span><span class="sxs-lookup"><span data-stu-id="010ce-105">During the development of the .NET Core tooling, an important design change was made to no longer support *project.json* files and instead move the .NET Core projects to the MSBuild/csproj format.</span></span>

<span data-ttu-id="010ce-106">En este artículo se muestra cómo se representa la configuración de *project.json* en el formato MSBuild/csproj para que pueda aprender a usar el nuevo formato y comprender los cambios realizados por las herramientas de migración cuando actualice el proyecto a la versión más reciente de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="010ce-106">This article shows how the settings in *project.json* are represented in the MSBuild/csproj format so you can learn how to use the new format and understand the changes made by the migration tools when you're upgrading your project to the latest version of the tooling.</span></span>

## <a name="the-csproj-format"></a><span data-ttu-id="010ce-107">El formato csproj</span><span class="sxs-lookup"><span data-stu-id="010ce-107">The csproj format</span></span>

<span data-ttu-id="010ce-108">El nuevo formato, \*.csproj, está basado en XML.</span><span class="sxs-lookup"><span data-stu-id="010ce-108">The new format, \*.csproj, is an XML-based format.</span></span> <span data-ttu-id="010ce-109">En el ejemplo siguiente se muestra el nodo raíz de un proyecto .NET Core con el SDK `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="010ce-109">The following example shows the root node of a .NET Core project using the `Microsoft.NET.Sdk`.</span></span> <span data-ttu-id="010ce-110">Para proyectos web, el SDK que se usa es `Microsoft.NET.Sdk.Web`.</span><span class="sxs-lookup"><span data-stu-id="010ce-110">For web projects, the SDK used is `Microsoft.NET.Sdk.Web`.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a><span data-ttu-id="010ce-111">Propiedades comunes de nivel superior</span><span class="sxs-lookup"><span data-stu-id="010ce-111">Common top-level properties</span></span>

### <a name="name"></a><span data-ttu-id="010ce-112">name</span><span class="sxs-lookup"><span data-stu-id="010ce-112">name</span></span>

```json
{
  "name": "MyProjectName"
}
```

<span data-ttu-id="010ce-113">Ya no se admite.</span><span class="sxs-lookup"><span data-stu-id="010ce-113">No longer supported.</span></span> <span data-ttu-id="010ce-114">En csproj, viene determinado por el nombre de archivo del proyecto, que normalmente coincide con el nombre del directorio.</span><span class="sxs-lookup"><span data-stu-id="010ce-114">In csproj, this is determined by the project filename, which usually matches the directory name.</span></span> <span data-ttu-id="010ce-115">Por ejemplo: `MyProjectName.csproj`.</span><span class="sxs-lookup"><span data-stu-id="010ce-115">For example, `MyProjectName.csproj`.</span></span>

<span data-ttu-id="010ce-116">De forma predeterminada, el nombre de archivo del proyecto también especifica el valor de las propiedades `<AssemblyName>` y `<PackageId>`.</span><span class="sxs-lookup"><span data-stu-id="010ce-116">By default, the project filename also specifies the value of the `<AssemblyName>` and `<PackageId>` properties.</span></span>

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

<span data-ttu-id="010ce-117">La propiedad `<AssemblyName>` tendrá un valor diferente a `<PackageId>` si se ha definido la propiedad `buildOptions\outputName` en project.json.</span><span class="sxs-lookup"><span data-stu-id="010ce-117">The `<AssemblyName>` will have a different value than `<PackageId>` if `buildOptions\outputName` property was defined in project.json.</span></span>
<span data-ttu-id="010ce-118">Para obtener más información, consulte [Otras opciones de compilación comunes](#other-common-build-options).</span><span class="sxs-lookup"><span data-stu-id="010ce-118">For more information, see [Other common build options](#other-common-build-options).</span></span>

### <a name="version"></a><span data-ttu-id="010ce-119">version</span><span class="sxs-lookup"><span data-stu-id="010ce-119">version</span></span>

```json
{
  "version": "1.0.0-alpha-*"
}
```

<span data-ttu-id="010ce-120">Use las propiedades `VersionPrefix` y `VersionSuffix`:</span><span class="sxs-lookup"><span data-stu-id="010ce-120">Use the `VersionPrefix` and `VersionSuffix` properties:</span></span>

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

<span data-ttu-id="010ce-121">También puede usar la propiedad `Version`, pero esto puede invalidar la configuración de la versión durante el empaquetado:</span><span class="sxs-lookup"><span data-stu-id="010ce-121">You can also use the `Version` property, but this may override version settings during packaging:</span></span>

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a><span data-ttu-id="010ce-122">Otras opciones comunes de nivel de raíz</span><span class="sxs-lookup"><span data-stu-id="010ce-122">Other common root-level options</span></span>

```json
{
  "authors": [ "Anne", "Bob" ],
  "company": "Contoso",
  "language": "en-US",
  "title": "My library",
  "description": "This is my library.\r\nAnd it's really great!",
  "copyright": "Nugetizer 3000",
  "userSecretsId": "xyz123"
}
```

```xml
<PropertyGroup>
  <Authors>Anne;Bob</Authors>
  <Company>Contoso</Company>
  <NeutralLanguage>en-US</NeutralLanguage>
  <AssemblyTitle>My library</AssemblyTitle>
  <Description>This is my library.
And it's really great!</Description>
  <Copyright>Nugetizer 3000</Copyright>
  <UserSecretsId>xyz123</UserSecretsId>
</PropertyGroup>
```

## <a name="frameworks"></a><span data-ttu-id="010ce-123">frameworks</span><span class="sxs-lookup"><span data-stu-id="010ce-123">frameworks</span></span>

### <a name="one-target-framework"></a><span data-ttu-id="010ce-124">Un marco de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="010ce-124">One target framework</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {}
  }
}
```

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp1.0</TargetFramework>
</PropertyGroup>
```

### <a name="multiple-target-frameworks"></a><span data-ttu-id="010ce-125">Varios marcos de trabajo de destino</span><span class="sxs-lookup"><span data-stu-id="010ce-125">Multiple target frameworks</span></span>

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

<span data-ttu-id="010ce-126">Use la propiedad `TargetFrameworks` para definir la lista de los marcos de trabajo de destino.</span><span class="sxs-lookup"><span data-stu-id="010ce-126">Use the `TargetFrameworks` property to define your list of target frameworks.</span></span> <span data-ttu-id="010ce-127">Use el punto y coma para separar varios valores de marco de trabajo.</span><span class="sxs-lookup"><span data-stu-id="010ce-127">Use semi-colon to separate multiple framework values.</span></span>

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a><span data-ttu-id="010ce-128">dependencias</span><span class="sxs-lookup"><span data-stu-id="010ce-128">dependencies</span></span>

> [!IMPORTANT]
> <span data-ttu-id="010ce-129">Si la dependencia es un **proyecto** y no un paquete, el formato es diferente.</span><span class="sxs-lookup"><span data-stu-id="010ce-129">If the dependency is a **project** and not a package, the format is different.</span></span>
> <span data-ttu-id="010ce-130">Para obtener más información, consulte la sección [tipo de dependencia](#dependency-type).</span><span class="sxs-lookup"><span data-stu-id="010ce-130">For more information, see the [dependency type](#dependency-type) section.</span></span>

### <a name="netstandardlibrary-metapackage"></a><span data-ttu-id="010ce-131">Metapaquete NETStandard.Library</span><span class="sxs-lookup"><span data-stu-id="010ce-131">NETStandard.Library metapackage</span></span>

```json
{
  "dependencies": {
    "NETStandard.Library": "1.6.0"
  }
}
```

```xml
<PropertyGroup>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

### <a name="microsoftnetcoreapp-metapackage"></a><span data-ttu-id="010ce-132">Metapaquete Microsoft.NETCore.App</span><span class="sxs-lookup"><span data-stu-id="010ce-132">Microsoft.NETCore.App metapackage</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": "1.0.0"
  }
}
```

```xml
<PropertyGroup>
  <RuntimeFrameworkVersion>1.0.3</RuntimeFrameworkVersion>
</PropertyGroup>
```

<span data-ttu-id="010ce-133">Tenga en cuenta que el valor `<RuntimeFrameworkVersion>` del proyecto migrado viene determinado por la versión del SDK que ha instalado.</span><span class="sxs-lookup"><span data-stu-id="010ce-133">Note that the `<RuntimeFrameworkVersion>` value in the migrated project is determined by the version of the SDK you have installed.</span></span>

### <a name="top-level-dependencies"></a><span data-ttu-id="010ce-134">Dependencias de nivel superior</span><span class="sxs-lookup"><span data-stu-id="010ce-134">Top-level dependencies</span></span>

```json
{
  "dependencies": {
    "Microsoft.AspNetCore": "1.1.0"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.AspNetCore" Version="1.1.0" />
</ItemGroup>
```

### <a name="per-framework-dependencies"></a><span data-ttu-id="010ce-135">Dependencias por marco de trabajo</span><span class="sxs-lookup"><span data-stu-id="010ce-135">Per-framework dependencies</span></span>

```json
{
  "framework": {
    "net451": {
      "dependencies": {
        "System.Collections.Immutable": "1.3.1"
      }
    },
    "netstandard1.5": {
      "dependencies": {
        "Newtonsoft.Json": "9.0.1"
      }
    }
  }
}
```

```xml
<ItemGroup Condition="'$(TargetFramework)'=='net451'">
  <PackageReference Include="System.Collections.Immutable" Version="1.3.1" />
</ItemGroup>

<ItemGroup Condition="'$(TargetFramework)'=='netstandard1.5'">
  <PackageReference Include="Newtonsoft.Json" Version="9.0.1" />
</ItemGroup>
```

### <a name="imports"></a><span data-ttu-id="010ce-136">imports</span><span class="sxs-lookup"><span data-stu-id="010ce-136">imports</span></span>

```json
{
  "dependencies": {
    "YamlDotNet": "4.0.1-pre309"
  },
  "frameworks": {
    "netcoreapp1.0": {
      "imports": [
        "dnxcore50",
        "dotnet"
      ]
    }
  }
}
```

```xml
<PropertyGroup>
  <PackageTargetFallback>dnxcore50;dotnet</PackageTargetFallback>
</PropertyGroup>
<ItemGroup>
  <PackageReference Include="YamlDotNet" Version="4.0.1-pre309" />
</ItemGroup>
```

### <a name="dependency-type"></a><span data-ttu-id="010ce-137">dependency type</span><span class="sxs-lookup"><span data-stu-id="010ce-137">dependency type</span></span>

#### <a name="type-project"></a><span data-ttu-id="010ce-138">type: project</span><span class="sxs-lookup"><span data-stu-id="010ce-138">type: project</span></span>

```json
{
  "dependencies": {
    "MyOtherProject": "1.0.0-*",
    "AnotherProject": {
      "type": "project"
    }
  }
}
```

```xml
<ItemGroup>
  <ProjectReference Include="..\MyOtherProject\MyOtherProject.csproj" />
  <ProjectReference Include="..\AnotherProject\AnotherProject.csproj" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="010ce-139">Esto interrumpirá la forma en que `dotnet pack --version-suffix $suffix` determina la versión de dependencia de una referencia de proyecto.</span><span class="sxs-lookup"><span data-stu-id="010ce-139">This will break the way that `dotnet pack --version-suffix $suffix` determines the dependency version of a project reference.</span></span>

#### <a name="type-build"></a><span data-ttu-id="010ce-140">type: build</span><span class="sxs-lookup"><span data-stu-id="010ce-140">type: build</span></span>

```json
{
  "dependencies": {
    "Microsoft.EntityFrameworkCore.Design": {
      "version": "1.1.0",
      "type": "build"
    }
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.EntityFrameworkCore.Design" Version="1.1.0" PrivateAssets="All" />
</ItemGroup>
```

#### <a name="type-platform"></a><span data-ttu-id="010ce-141">type: platform</span><span class="sxs-lookup"><span data-stu-id="010ce-141">type: platform</span></span>

```json
{
  "dependencies": {
    "Microsoft.NETCore.App": {
      "version": "1.1.0",
      "type": "platform"
    }
  }
}
```

<span data-ttu-id="010ce-142">No existe ningún equivalente en csproj.</span><span class="sxs-lookup"><span data-stu-id="010ce-142">There is no equivalent in csproj.</span></span>

## <a name="runtimes"></a><span data-ttu-id="010ce-143">runtimes</span><span class="sxs-lookup"><span data-stu-id="010ce-143">runtimes</span></span>

```json
{
  "runtimes": {
    "win7-x64": {},
    "osx.10.11-x64": {},
    "ubuntu.16.04-x64": {}
  }
}
```

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win7-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="standalone-apps-self-contained-deployment"></a><span data-ttu-id="010ce-144">Aplicaciones independientes (implementación autocontenida)</span><span class="sxs-lookup"><span data-stu-id="010ce-144">Standalone apps (self-contained deployment)</span></span>

<span data-ttu-id="010ce-145">En project.json, definir una sección `runtimes` implica que la aplicación se ha mantenido independiente durante la compilación y la publicación.</span><span class="sxs-lookup"><span data-stu-id="010ce-145">In project.json, defining a `runtimes` section means the app was standalone during build and publish.</span></span>
<span data-ttu-id="010ce-146">En MSBuild, todos los proyectos son *portátiles* durante la compilación, pero se pueden publicar como independientes.</span><span class="sxs-lookup"><span data-stu-id="010ce-146">In MSBuild, all projects are *portable* during build, but can be published as standalone.</span></span>

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

<span data-ttu-id="010ce-147">Para obtener más información, consulte [Implementaciones autocontenidas (SCD)](../deploying/index.md#self-contained-deployments-scd).</span><span class="sxs-lookup"><span data-stu-id="010ce-147">For more information, see [Self-contained deployments (SCD)](../deploying/index.md#self-contained-deployments-scd).</span></span>

## <a name="tools"></a><span data-ttu-id="010ce-148">tools</span><span class="sxs-lookup"><span data-stu-id="010ce-148">tools</span></span>

```json
{
  "tools": {
    "Microsoft.EntityFrameworkCore.Tools.DotNet": "1.0.0-*"
  }
}
```

```xml
<ItemGroup>
  <DotNetCliToolReference Include="Microsoft.EntityFrameworkCore.Tools.DotNet" Version="1.0.0" />
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="010ce-149">En csproj no se admite `imports` en herramientas.</span><span class="sxs-lookup"><span data-stu-id="010ce-149">`imports` on tools are not supported in csproj.</span></span> <span data-ttu-id="010ce-150">Las herramientas que necesitan importaciones no funcionarán con el nuevo SDK `Microsoft.NET.Sdk`.</span><span class="sxs-lookup"><span data-stu-id="010ce-150">Tools that need imports will not work with the new `Microsoft.NET.Sdk`.</span></span>

## <a name="buildoptions"></a><span data-ttu-id="010ce-151">buildOptions</span><span class="sxs-lookup"><span data-stu-id="010ce-151">buildOptions</span></span>

<span data-ttu-id="010ce-152">Consulte también [Archivos](#files).</span><span class="sxs-lookup"><span data-stu-id="010ce-152">See also [Files](#files).</span></span>

### <a name="emitentrypoint"></a><span data-ttu-id="010ce-153">emitEntryPoint</span><span class="sxs-lookup"><span data-stu-id="010ce-153">emitEntryPoint</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": true
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

<span data-ttu-id="010ce-154">Si `emitEntryPoint` era `false`, el valor de `OutputType` se convierte en `Library`, que es el valor predeterminado:</span><span class="sxs-lookup"><span data-stu-id="010ce-154">If `emitEntryPoint` was `false`, the value of `OutputType` is converted to `Library`, which is the default value:</span></span>

```json
{
  "buildOptions": {
    "emitEntryPoint": false
  }
}
```

```xml
<PropertyGroup>
  <OutputType>Library</OutputType>
  <!-- or, omit altogether. It defaults to 'Library' -->
</PropertyGroup>
```

### <a name="keyfile"></a><span data-ttu-id="010ce-155">keyFile</span><span class="sxs-lookup"><span data-stu-id="010ce-155">keyFile</span></span>

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

<span data-ttu-id="010ce-156">El elemento `keyFile` se expande a tres propiedades en MSBuild:</span><span class="sxs-lookup"><span data-stu-id="010ce-156">The `keyFile` element expands to three properties in MSBuild:</span></span>

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a><span data-ttu-id="010ce-157">Otras opciones de compilación comunes</span><span class="sxs-lookup"><span data-stu-id="010ce-157">Other common build options</span></span>

```json
{
  "buildOptions": {
    "warningsAsErrors": true,
    "nowarn": ["CS0168", "CS0219"],
    "xmlDoc": true,
    "preserveCompilationContext": true,
    "outputName": "Different.AssemblyName",
    "debugType": "portable",
    "allowUnsafe": true,
    "define": ["TEST", "OTHERCONDITION"]
  }
}
```

```xml
<PropertyGroup>
  <TreatWarningsAsErrors>true</TreatWarningsAsErrors>
  <NoWarn>$(NoWarn);CS0168;CS0219</NoWarn>
  <GenerateDocumentationFile>true</GenerateDocumentationFile>
  <PreserveCompilationContext>true</PreserveCompilationContext>
  <AssemblyName>Different.AssemblyName</AssemblyName>
  <DebugType>portable</DebugType>
  <AllowUnsafeBlocks>true</AllowUnsafeBlocks>
  <DefineConstants>$(DefineConstants);TEST;OTHERCONDITION</DefineConstants>
</PropertyGroup>
```

## <a name="packoptions"></a><span data-ttu-id="010ce-158">packOptions</span><span class="sxs-lookup"><span data-stu-id="010ce-158">packOptions</span></span>

<span data-ttu-id="010ce-159">Consulte también [Archivos](#files).</span><span class="sxs-lookup"><span data-stu-id="010ce-159">See also [Files](#files).</span></span>

### <a name="common-pack-options"></a><span data-ttu-id="010ce-160">Opciones comunes de empaquetado</span><span class="sxs-lookup"><span data-stu-id="010ce-160">Common pack options</span></span>

```json
{
  "packOptions": {
    "summary": "numl is a machine learning library intended to ease the use of using standard modeling techniques for both prediction and clustering.",
    "tags": ["machine learning", "framework"],
    "releaseNotes": "Version 0.9.12-beta",
    "iconUrl": "http://numl.net/images/ico.png",
    "projectUrl": "http://numl.net",
    "licenseUrl": "https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md",
    "requireLicenseAcceptance": false,
    "repository": {
      "type": "git",
      "url": "https://raw.githubusercontent.com/sethjuarez/numl"
    },
    "owners": ["Seth Juarez"]
  }
}
```

```xml
<PropertyGroup>
  <!-- summary is not migrated from project.json, but you can use the <Description> property for that if needed. -->
  <PackageTags>machine learning;framework</PackageTags>
  <PackageReleaseNotes>Version 0.9.12-beta</PackageReleaseNotes>
  <PackageIconUrl>http://numl.net/images/ico.png</PackageIconUrl>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

<span data-ttu-id="010ce-161">No hay ningún equivalente del elemento `owners` en MSBuild.</span><span class="sxs-lookup"><span data-stu-id="010ce-161">There is no equivalent for the `owners` element in MSBuild.</span></span>
<span data-ttu-id="010ce-162">Para `summary`, puede usar la propiedad `<Description>` de MSBuild, aunque el valor de `summary` no se migra automáticamente a esa propiedad, ya que esta se asigna al elemento [`description`](#other-common-root-level-options).</span><span class="sxs-lookup"><span data-stu-id="010ce-162">For `summary`, you can use the MSBuild `<Description>` property, even though the value of `summary` is not migrated automatically to that property, since that property is mapped to the [`description`](#other-common-root-level-options) element.</span></span>

## <a name="scripts"></a><span data-ttu-id="010ce-163">scripts</span><span class="sxs-lookup"><span data-stu-id="010ce-163">scripts</span></span>

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

<span data-ttu-id="010ce-164">Su equivalente en MSBuild es [target](/visualstudio/msbuild/msbuild-targets):</span><span class="sxs-lookup"><span data-stu-id="010ce-164">Their equivalent in MSBuild are [targets](/visualstudio/msbuild/msbuild-targets):</span></span>

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a><span data-ttu-id="010ce-165">runtimeOptions</span><span class="sxs-lookup"><span data-stu-id="010ce-165">runtimeOptions</span></span>

```json
{
  "runtimeOptions": {
    "configProperties": {
      "System.GC.Server": true,
      "System.GC.Concurrent": true,
      "System.GC.RetainVM": true,
      "System.Threading.ThreadPool.MinThreads": 4,
      "System.Threading.ThreadPool.MaxThreads": 25
    }
  }
}
```

<span data-ttu-id="010ce-166">Todos los valores de configuración de este grupo, excepto la propiedad “System.GC.Server”, se colocan en un archivo denominado *runtimeconfig.template.json* en la carpeta del proyecto, con opciones elevadas al objeto raíz durante el proceso de migración:</span><span class="sxs-lookup"><span data-stu-id="010ce-166">All settings in this group, except for the "System.GC.Server" property, are placed into a file called *runtimeconfig.template.json* in the project folder, with options lifted to the root object during the migration process:</span></span>

```json
{
  "configProperties": {
    "System.GC.Concurrent": true,
    "System.GC.RetainVM": true,
    "System.Threading.ThreadPool.MinThreads": 4,
    "System.Threading.ThreadPool.MaxThreads": 25
  }
}
```

<span data-ttu-id="010ce-167">Se migra la propiedad “System.GC.Server” al archivo csproj:</span><span class="sxs-lookup"><span data-stu-id="010ce-167">The "System.GC.Server" property is migrated into the csproj file:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

<span data-ttu-id="010ce-168">En cambio, puede establecer todos esos valores en csproj, así como en propiedades de MSBuild:</span><span class="sxs-lookup"><span data-stu-id="010ce-168">However, you can set all those values in the csproj as well as MSBuild properties:</span></span>

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a><span data-ttu-id="010ce-169">shared</span><span class="sxs-lookup"><span data-stu-id="010ce-169">shared</span></span>

```json
{
  "shared": "shared/**/*.cs"
}
```

<span data-ttu-id="010ce-170">No se admite en csproj.</span><span class="sxs-lookup"><span data-stu-id="010ce-170">Not supported in csproj.</span></span> <span data-ttu-id="010ce-171">En su lugar, debe incluir archivos de contenido en el archivo *.nuspec*.</span><span class="sxs-lookup"><span data-stu-id="010ce-171">You must instead create include content files in your *.nuspec* file.</span></span>
<span data-ttu-id="010ce-172">Para obtener más información, consulte [Including content files](/nuget/schema/nuspec#including-content-files) (Incluir archivos de contenido).</span><span class="sxs-lookup"><span data-stu-id="010ce-172">For more information, see [Including content files](/nuget/schema/nuspec#including-content-files).</span></span>

## <a name="files"></a><span data-ttu-id="010ce-173">archivos</span><span class="sxs-lookup"><span data-stu-id="010ce-173">files</span></span>

<span data-ttu-id="010ce-174">En *project.json*, la compilación y el empaquetado podrían ampliarse para compilar e insertar desde diferentes carpetas.</span><span class="sxs-lookup"><span data-stu-id="010ce-174">In *project.json*, build and pack could be extended to compile and embed from different folders.</span></span>
<span data-ttu-id="010ce-175">En MSBuild, esto se hace mediante [elementos](/visualstudio/msbuild/common-msbuild-project-items).</span><span class="sxs-lookup"><span data-stu-id="010ce-175">In MSBuild, this is done using [items](/visualstudio/msbuild/common-msbuild-project-items).</span></span> <span data-ttu-id="010ce-176">En el siguiente ejemplo se muestra una conversión común:</span><span class="sxs-lookup"><span data-stu-id="010ce-176">The following example is a common conversion:</span></span>

```json
{
  "buildOptions": {
    "compile": {
      "copyToOutput": "notes.txt",
      "include": "../Shared/*.cs",
      "exclude": "../Shared/Not/*.cs"
    },
    "embed": {
      "include": "../Shared/*.resx"
    }
  },
  "packOptions": {
    "include": "Views/",
    "mappings": {
      "some/path/in/project.txt": "in/package.txt"
    }
  },
  "publishOptions": {
    "include": [
      "files/",
      "publishnotes.txt"
    ]
  }
}
```

```xml
<ItemGroup>
  <Compile Include="..\Shared\*.cs" Exclude="..\Shared\Not\*.cs" />
  <EmbeddedResource Include="..\Shared\*.resx" />
  <Content Include="Views\**\*" PackagePath="%(Identity)" />
  <None Include="some/path/in/project.txt" Pack="true" PackagePath="in/package.txt" />
  
  <None Include="notes.txt" CopyToOutputDirectory="Always" />
  <!-- CopyToOutputDirectory = { Always, PreserveNewest, Never } -->

  <Content Include="files\**\*" CopyToPublishDirectory="PreserveNewest" />
  <None Include="publishnotes.txt" CopyToPublishDirectory="Always" />
  <!-- CopyToPublishDirectory = { Always, PreserveNewest, Never } -->
</ItemGroup>
```

> [!NOTE]
> <span data-ttu-id="010ce-177">El SDK de .NET Core agrega automáticamente muchos de los [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) predeterminados.</span><span class="sxs-lookup"><span data-stu-id="010ce-177">Many of the default [globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are added automatically by the .NET Core SDK.</span></span>
> <span data-ttu-id="010ce-178">Para obtener más información, consulte [Default Compile Item Values](https://aka.ms/sdkimplicititems) (Valores de elementos de compilación predeterminados).</span><span class="sxs-lookup"><span data-stu-id="010ce-178">For more information, see [Default Compile Item Values](https://aka.ms/sdkimplicititems).</span></span>

<span data-ttu-id="010ce-179">Todos los elementos `ItemGroup` de MSBuild admiten `Include`, `Exclude` y `Remove`.</span><span class="sxs-lookup"><span data-stu-id="010ce-179">All MSBuild `ItemGroup` elements support `Include`, `Exclude`, and `Remove`.</span></span>

<span data-ttu-id="010ce-180">Se puede modificar el diseño del paquete dentro de .nupkg con `PackagePath="path"`.</span><span class="sxs-lookup"><span data-stu-id="010ce-180">Package layout inside the .nupkg can be modified with `PackagePath="path"`.</span></span>

<span data-ttu-id="010ce-181">A excepción de `Content`, la mayoría de los grupos de elementos requiere que se agregue explícitamente `Pack="true"` para incluirlos en el paquete.</span><span class="sxs-lookup"><span data-stu-id="010ce-181">Except for `Content`, most item groups require explicitly adding `Pack="true"` to be included in the package.</span></span> <span data-ttu-id="010ce-182">`Content` se colocará en la carpeta *content* de un paquete, puesto que la propiedad `<IncludeContentInPack>` de MSBuild está establecida como `true` de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="010ce-182">`Content` will be put in the *content* folder in a package since the MSBuild `<IncludeContentInPack>` property is set to `true` by default.</span></span>
<span data-ttu-id="010ce-183">Para obtener más información, consulte [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package) (Incluir contenido en un paquete).</span><span class="sxs-lookup"><span data-stu-id="010ce-183">For more information, see [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package).</span></span>

<span data-ttu-id="010ce-184">`PackagePath="%(Identity)"` es una forma rápida de establecer la ruta del paquete como la ruta del archivo relativa al proyecto.</span><span class="sxs-lookup"><span data-stu-id="010ce-184">`PackagePath="%(Identity)"` is a short way of setting package path to the project-relative file path.</span></span>

## <a name="testrunner"></a><span data-ttu-id="010ce-185">testRunner</span><span class="sxs-lookup"><span data-stu-id="010ce-185">testRunner</span></span>

### <a name="xunit"></a><span data-ttu-id="010ce-186">xUnit</span><span class="sxs-lookup"><span data-stu-id="010ce-186">xUnit</span></span>

```json
{
  "testRunner": "xunit",
  "dependencies": {
    "dotnet-test-xunit": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="xunit" Version="2.2.0-*" />
  <PackageReference Include="xunit.runner.visualstudio" Version="2.2.0-*" />
</ItemGroup>
```

### <a name="mstest"></a><span data-ttu-id="010ce-187">MSTest</span><span class="sxs-lookup"><span data-stu-id="010ce-187">MSTest</span></span>

```json
{
  "testRunner": "mstest",
  "dependencies": {
    "dotnet-test-mstest": "<any>"
  }
}
```

```xml
<ItemGroup>
  <PackageReference Include="Microsoft.NET.Test.Sdk" Version="15.0.0-*" />
  <PackageReference Include="MSTest.TestAdapter" Version="1.1.12-*" />
  <PackageReference Include="MSTest.TestFramework" Version="1.1.11-*" />
</ItemGroup>
```

## <a name="see-also"></a><span data-ttu-id="010ce-188">Vea también</span><span class="sxs-lookup"><span data-stu-id="010ce-188">See also</span></span>

- [<span data-ttu-id="010ce-189">Introducción de alto nivel de cambios en la CLI</span><span class="sxs-lookup"><span data-stu-id="010ce-189">High-level overview of changes in CLI</span></span>](../tools/cli-msbuild-architecture.md)
