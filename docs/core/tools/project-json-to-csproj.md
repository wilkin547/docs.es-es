---
title: Comparación entre project.json y csproj
description: Vea una asignación entre los elementos project.json y csproj.
author: natemcmaster
ms.date: 03/13/2017
ms.openlocfilehash: 7de9f623a57a6a094debd3e018edc1560d837fc2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970881"
---
# <a name="a-mapping-between-projectjson-and-csproj-properties"></a>Una asignación entre propiedades project.json y csproj

Por [Nate McMaster](https://github.com/natemcmaster)

Durante el desarrollo de las herramientas de .NET Core, se realizó un cambio de diseño importante para dejar de admitir los archivos *project.json* y trasladar en su lugar los proyectos .NET Core al formato MSBuild/csproj.

En este artículo se muestra cómo se representa la configuración de *project.json* en el formato MSBuild/csproj para que pueda aprender a usar el nuevo formato y comprender los cambios realizados por las herramientas de migración cuando actualice el proyecto a la versión más reciente de la herramienta.

## <a name="the-csproj-format"></a>El formato csproj

El nuevo formato, \*.csproj, está basado en XML. En el ejemplo siguiente se muestra el nodo raíz de un proyecto .NET Core con el SDK `Microsoft.NET.Sdk`. Para proyectos web, el SDK que se usa es `Microsoft.NET.Sdk.Web`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
...
</Project>
```

## <a name="common-top-level-properties"></a>Propiedades comunes de nivel superior

### <a name="name"></a>name

```json
{
  "name": "MyProjectName"
}
```

Ya no se admite. En csproj, viene determinado por el nombre de archivo del proyecto, que normalmente coincide con el nombre del directorio. Por ejemplo: `MyProjectName.csproj`.

De forma predeterminada, el nombre de archivo del proyecto también especifica el valor de las propiedades `<AssemblyName>` y `<PackageId>`.

```xml
<PropertyGroup>
  <AssemblyName>MyProjectName</AssemblyName>
  <PackageId>MyProjectName</PackageId>
</PropertyGroup>
```

La propiedad `<AssemblyName>` tendrá un valor diferente a `<PackageId>` si se ha definido la propiedad `buildOptions\outputName` en project.json.
Para obtener más información, consulte [Otras opciones de compilación comunes](#other-common-build-options).

### <a name="version"></a>version

```json
{
  "version": "1.0.0-alpha-*"
}
```

Use las propiedades `VersionPrefix` y `VersionSuffix`:

```xml
<PropertyGroup>
  <VersionPrefix>1.0.0</VersionPrefix>
  <VersionSuffix>alpha</VersionSuffix>
</PropertyGroup>
```

También puede usar la propiedad `Version`, pero esto puede invalidar la configuración de la versión durante el empaquetado:

```xml
<PropertyGroup>
  <Version>1.0.0-alpha</Version>
</PropertyGroup>
```

### <a name="other-common-root-level-options"></a>Otras opciones comunes de nivel de raíz

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

## <a name="frameworks"></a>frameworks

### <a name="one-target-framework"></a>Un marco de trabajo de destino

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

### <a name="multiple-target-frameworks"></a>Varios marcos de trabajo de destino

```json
{
  "frameworks": {
    "netcoreapp1.0": {},
    "net451": {}
  }
}
```

Use la propiedad `TargetFrameworks` para definir la lista de los marcos de trabajo de destino. Use el punto y coma para separar varios valores de marco de trabajo.

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp1.0;net451</TargetFrameworks>
</PropertyGroup>
```

## <a name="dependencies"></a>dependencias

> [!IMPORTANT]
> Si la dependencia es un **proyecto** y no un paquete, el formato es diferente.
> Para obtener más información, consulte la sección [tipo de dependencia](#dependency-type).

### <a name="netstandardlibrary-metapackage"></a>Metapaquete NETStandard.Library

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

### <a name="microsoftnetcoreapp-metapackage"></a>Metapaquete Microsoft.NETCore.App

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

El valor `<RuntimeFrameworkVersion>` del proyecto migrado viene determinado por la versión del SDK que ha instalado.

### <a name="top-level-dependencies"></a>Dependencias de nivel superior

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

### <a name="per-framework-dependencies"></a>Dependencias por marco de trabajo

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

### <a name="imports"></a>imports

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

### <a name="dependency-type"></a>dependency type

#### <a name="type-project"></a>type: project

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
> Esto interrumpirá la forma en que `dotnet pack --version-suffix $suffix` determina la versión de dependencia de una referencia de proyecto.

#### <a name="type-build"></a>type: build

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

#### <a name="type-platform"></a>type: platform

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

No existe ningún equivalente en csproj.

## <a name="runtimes"></a>runtimes

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

### <a name="standalone-apps-self-contained-deployment"></a>Aplicaciones independientes (implementación autocontenida)

En project.json, definir una sección `runtimes` implica que la aplicación se ha mantenido independiente durante la compilación y la publicación.
En MSBuild, todos los proyectos son *portátiles* durante la compilación, pero se pueden publicar como independientes.

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

Para obtener más información, consulte [Implementaciones autocontenidas (SCD)](../deploying/index.md#publish-self-contained).

## <a name="tools"></a>tools

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
> En csproj no se admite `imports` en herramientas. Las herramientas que necesitan importaciones no funcionarán con el nuevo SDK `Microsoft.NET.Sdk`.

## <a name="buildoptions"></a>buildOptions

Consulte también [Archivos](#files).

### <a name="emitentrypoint"></a>emitEntryPoint

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

Si `emitEntryPoint` era `false`, el valor de `OutputType` se convierte en `Library`, que es el valor predeterminado:

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

### <a name="keyfile"></a>keyFile

```json
{
  "buildOptions": {
    "keyFile": "MyKey.snk"
  }
}
```

El elemento `keyFile` se expande a tres propiedades en MSBuild:

```xml
<PropertyGroup>
  <AssemblyOriginatorKeyFile>MyKey.snk</AssemblyOriginatorKeyFile>
  <SignAssembly>true</SignAssembly>
  <PublicSign Condition="'$(OS)' != 'Windows_NT'">true</PublicSign>
</PropertyGroup>
```

### <a name="other-common-build-options"></a>Otras opciones de compilación comunes

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

## <a name="packoptions"></a>packOptions

Consulte también [Archivos](#files).

### <a name="common-pack-options"></a>Opciones comunes de empaquetado

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
  <PackageIcon>ico.png</PackageIcon>
  <PackageProjectUrl>http://numl.net</PackageProjectUrl>
  <PackageLicenseUrl>https://raw.githubusercontent.com/sethjuarez/numl/master/LICENSE.md</PackageLicenseUrl>
  <PackageRequireLicenseAcceptance>false</PackageRequireLicenseAcceptance>
  <RepositoryType>git</RepositoryType>
  <RepositoryUrl>https://raw.githubusercontent.com/sethjuarez/numl</RepositoryUrl>
  <!-- owners is not supported in MSBuild -->
</PropertyGroup>
```

No hay ningún equivalente del elemento `owners` en MSBuild. En `summary`, puede usar la propiedad `<Description>` de MSBuild. El valor de `summary` no se migra automáticamente a esa propiedad, ya que está asignada al elemento [`description`](#other-common-root-level-options).  [PackageIconUrl está en desuso](/nuget/reference/msbuild-targets#packageiconurl) en favor de PackageIcon.

## <a name="scripts"></a>scripts

```json
{
  "scripts": {
    "precompile": "generateCode.cmd",
    "postpublish": [ "obfuscate.cmd", "removeTempFiles.cmd" ]
  }
}
```

Sus equivalentes en MSBuild son [destinos](/visualstudio/msbuild/msbuild-targets):

```xml
<Target Name="MyPreCompileTarget" BeforeTargets="Build">
  <Exec Command="generateCode.cmd" />
</Target>

<Target Name="MyPostCompileTarget" AfterTargets="Publish">
  <Exec Command="obfuscate.cmd" />
  <Exec Command="removeTempFiles.cmd" />
</Target>
```

## <a name="runtimeoptions"></a>runtimeOptions

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

Todos los valores de configuración de este grupo, excepto la propiedad `System.GC.Server`, se colocan en un archivo denominado *runtimeconfig.template.json* en la carpeta del proyecto, con opciones elevadas al objeto raíz durante el proceso de migración:

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

La propiedad `System.GC.Server` se migra en el archivo csproj:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

En cambio, puede establecer todos esos valores en csproj, así como en propiedades de MSBuild:

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
  <ConcurrentGarbageCollection>true</ConcurrentGarbageCollection>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
  <ThreadPoolMaxThreads>25</ThreadPoolMaxThreads>
</PropertyGroup>
```

## <a name="shared"></a>shared

```json
{
  "shared": "shared/**/*.cs"
}
```

No se admite en csproj. En su lugar, cree archivos de contenido de inclusión en el archivo *.nuspec*.
Para obtener más información, consulte [Including content files](/nuget/schema/nuspec#including-content-files) (Incluir archivos de contenido).

## <a name="files"></a>archivos

En *project.json*, la compilación y el empaquetado podrían ampliarse para compilar e insertar desde diferentes carpetas.
En MSBuild, esto se hace mediante [elementos](/visualstudio/msbuild/common-msbuild-project-items). En el siguiente ejemplo se muestra una conversión común:

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
> El SDK de .NET Core agrega automáticamente muchos de los [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) predeterminados. Para más información, consulte [Inclusiones de compilación predeterminadas](../project-sdk/overview.md#default-includes-and-excludes).

Todos los elementos `ItemGroup` de MSBuild admiten `Include`, `Exclude` y `Remove`.

Se puede modificar el diseño del paquete dentro de .nupkg con `PackagePath="path"`.

A excepción de `Content`, la mayoría de los grupos de elementos requiere que se agregue explícitamente `Pack="true"` para incluirlos en el paquete. `Content` se colocará en la carpeta *content* de un paquete, puesto que la propiedad `<IncludeContentInPack>` de MSBuild está establecida como `true` de forma predeterminada.
Para obtener más información, consulte [Including content in a package](/nuget/schema/msbuild-targets#including-content-in-a-package) (Incluir contenido en un paquete).

`PackagePath="%(Identity)"` es una forma rápida de establecer la ruta del paquete como la ruta del archivo relativa al proyecto.

## <a name="testrunner"></a>testRunner

### <a name="xunit"></a>xUnit

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

### <a name="mstest"></a>MSTest

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

## <a name="see-also"></a>Vea también

- [Introducción de alto nivel de cambios en la CLI](cli-msbuild-architecture.md)
