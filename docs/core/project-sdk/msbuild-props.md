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
# <a name="msbuild-properties-for-net-core-sdk-projects"></a>Propiedades de MSBuild para proyectos del SDK de .NET Core

En esta página se describen las propiedades de MSBuild para configurar proyectos de .NET Core.

> [!NOTE]
> Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET Core. Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Propiedades del marco de trabajo

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación, que hace referencia de forma implícita a un [metapaquete](../packages.md#metapackages). Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netcoreapp3.1</TargetFramework>
  </PropertyGroup>
</Project>
```

Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino. Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-framework-versions).

> [!NOTE]
> Esta propiedad se omite si se especifica `TargetFramework` (singular).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
  </PropertyGroup>
</Project>
```

Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`. No se aplica a los que usan `netstandard2.x`.

Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión de la plataforma anterior a la del [metapaquete](../packages.md#metapackages). El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <TargetFramework>netstandard1.3</TargetFramework>
    <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
  </PropertyGroup>
</Project>
```

## <a name="publish-properties"></a>Publicación de propiedades

- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [UseAppHost](#useapphost)

### <a name="runtimeidentifier"></a>RuntimeIdentifier

La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto. El RID permite publicar una implementación autocontenida.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
  </PropertyGroup>
</Project>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Use esta propiedad si tiene que publicar para varios entornos de ejecución. `RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.

> [!TIP]
> `RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

### <a name="useapphost"></a>UseAppHost

La propiedad `UseAppHost` se presentó en la versión 2.1.400 del SDK de .NET Core. Controla si se crea o no un archivo ejecutable nativo para una implementación. Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.

En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo. Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <UseAppHost>false</UseAppHost>
  </PropertyGroup>
</Project>
```

Para obtener más información sobre la implementación, vea [Implementación de aplicaciones .NET Core](../deploying/index.md).

## <a name="compile-properties"></a>Propiedades de compilación

### <a name="langversion"></a>LangVersion

La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación. Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <LangVersion>preview</LangVersion>
  </PropertyGroup>
</Project>
```

Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="nuget-packages"></a>Paquetes NuGet

- [PackageReference](#packagereference)
- [AssetTargetFallback](#assettargetfallback)

### <a name="packagereference"></a>PackageReference

El elemento `PackageReference` permite especificar una dependencia de NuGet. Por ejemplo, es posible que quiera hacer referencia a un único paquete en lugar de a un [metapaquete](../packages.md#metapackages). El atributo `Include` especifica el identificador del paquete. El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <ItemGroup>
    <PackageReference Include="System.Runtime" Version="4.3.0" />
  </ItemGroup>
</Project>
```

Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).

### <a name="assettargetfallback"></a>AssetTargetFallback

La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para los proyectos a los que el proyecto hace referencia, y los paquetes NuGet que consume el proyecto. Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`. La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`.

Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-framework-versions).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
  <PropertyGroup>
    <AssetTargetFallback>net461</AssetTargetFallback>
  </PropertyGroup>
</Project>
```

### <a name="pack-and-restore-targets"></a>Destinos pack y restore

En MSBuild 15.1 se presentaron los destinos `pack` y `restore` para crear y restaurar paquetes NuGet como parte de una compilación. Para obtener información sobre las propiedades de MSBuild para estos destinos, incluido `PackageTargetFallback`, vea [pack y restore de NuGet como destinos de MSBuild](/nuget/reference/msbuild-targets).

## <a name="see-also"></a>Vea también

- [Referencia del esquema de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Propiedades de MSBuild para pack de NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Propiedades de MSBuild para restore de NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Personalización de una compilación](/visualstudio/msbuild/customize-your-build)
