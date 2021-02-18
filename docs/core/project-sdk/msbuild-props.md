---
title: Propiedades de MSBuild para Microsoft.NET.Sdk
description: Referencia de las propiedades y los elementos de MSBuild admitidos por el SDK de .NET.
ms.date: 02/14/2020
ms.topic: reference
ms.custom: updateeachrelease
ms.openlocfilehash: 9cd387a4a8ad7f5b31a797d4d019a53799d926ff
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100432707"
---
# <a name="msbuild-reference-for-net-sdk-projects"></a>Referencia de MSBuild para proyectos del SDK de .NET

Esta página es una referencia de las propiedades y los elementos de MSBuild que puede usar para configurar proyectos de .NET.

> [!NOTE]
> Esta página es un trabajo en curso y no muestra todas las propiedades de MSBuild útiles para el SDK de .NET. Para obtener una lista de las propiedades comunes de MSBuild, vea [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties).

## <a name="framework-properties"></a>Propiedades del marco de trabajo

- [TargetFramework](#targetframework)
- [TargetFrameworks](#targetframeworks)
- [NetStandardImplicitPackageVersion](#netstandardimplicitpackageversion)

### <a name="targetframework"></a>TargetFramework

La propiedad `TargetFramework` especifica la versión de la plataforma de destino de la aplicación. Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).

```xml
<PropertyGroup>
  <TargetFramework>netcoreapp3.1</TargetFramework>
</PropertyGroup>
```

Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).

### <a name="targetframeworks"></a>TargetFrameworks

Use la propiedad `TargetFrameworks` cuando quiera que la aplicación tenga varias plataformas como destino. Para obtener una lista de los monikers de plataforma de destino válidos, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md#supported-target-frameworks).

> [!NOTE]
> Esta propiedad se omite si se especifica `TargetFramework` (singular).

```xml
<PropertyGroup>
  <TargetFrameworks>netcoreapp3.1;net462</TargetFrameworks>
</PropertyGroup>
```

Para obtener más información, vea [Plataformas de destino en proyectos de estilo SDK](../../standard/frameworks.md).

### <a name="netstandardimplicitpackageversion"></a>NetStandardImplicitPackageVersion

> [!NOTE]
> Esta propiedad solo se aplica a los proyectos que usan `netstandard1.x`. No se aplica a los que usan `netstandard2.x`.

Use la propiedad `NetStandardImplicitPackageVersion` si quiere especificar una versión del marco que sea inferior a la de la versión del metapaquete. El archivo del proyecto del ejemplo siguiente tiene como destino `netstandard1.3` pero usa la versión 1.6.0 de `NETStandard.Library`.

```xml
<PropertyGroup>
  <TargetFramework>netstandard1.3</TargetFramework>
  <NetStandardImplicitPackageVersion>1.6.0</NetStandardImplicitPackageVersion>
</PropertyGroup>
```

## <a name="package-properties"></a>Propiedades del paquete

Puede especificar propiedades como `PackageId`, `PackageVersion`, `PackageIcon`, `Title` y `Description` para describir el paquete que se crea a partir del proyecto. Para más información sobre estas y otras propiedades, vea [Destino de pack](/nuget/reference/msbuild-targets#pack-target).

```xml
<PropertyGroup>
  ...
  <PackageId>ClassLibDotNetStandard</PackageId>
  <Version>1.0.0</Version>
  <Authors>John Doe</Authors>
  <Company>Contoso</Company>
</PropertyGroup>
```

## <a name="publish-properties-items-and-metadata"></a>Propiedades, elementos y metadatos de publicación

- [AppendRuntimeIdentifierToOutputPath](#appendruntimeidentifiertooutputpath)
- [AppendTargetFrameworkToOutputPath](#appendtargetframeworktooutputpath)
- [CopyLocalLockFileAssemblies](#copylocallockfileassemblies)
- [CopyToPublishDirectory](#copytopublishdirectory)
- [LinkBase](#linkbase)
- [PreserveCompilationContext](#preservecompilationcontext)
- [PreserveCompilationReferences](#preservecompilationreferences)
- [RuntimeIdentifier](#runtimeidentifier)
- [RuntimeIdentifiers](#runtimeidentifiers)
- [TrimmerRootAssembly](#trimmerrootassembly)
- [UseAppHost](#useapphost)

### <a name="copytopublishdirectory"></a>CopyToPublishDirectory

Los metadatos de `CopyToPublishDirectory` relativos a un elemento de MSBuild controlan cuándo se copia el elemento en el directorio de publicación. Los valores permitidos son `PreserveNewest`, que solo copia el elemento si ha cambiado; `Always`, que siempre lo copia; y `Never`, que nunca lo hace. Desde el punto de vista del rendimiento, `PreserveNewest` es preferible porque permite una compilación incremental.

```xml
<ItemGroup>
  <None Update="appsettings.Development.json" CopyToOutputDirectory="PreserveNewest" CopyToPublishDirectory="PreserveNewest" />
</ItemGroup>
```

### <a name="linkbase"></a>LinkBase

En el caso de un elemento situado fuera del directorio del proyecto y sus subdirectorios, el destino de publicación usa los [metadatos de Link](/visualstudio/msbuild/common-msbuild-item-metadata) del elemento para determinar dónde se debe copiar este. `Link` también determina cómo se muestran los elementos situados fuera del árbol del proyecto en la ventana Explorador de soluciones de Visual Studio.

Si no se especifica `Link` para un elemento situado fuera del cono del proyecto, este tiene `%(LinkBase)\%(RecursiveDir)%(Filename)%(Extension)` como valor predeterminado. `LinkBase` permite especificar una carpeta base razonable para los elementos situados fuera del cono del proyecto. La jerarquía de carpetas de la carpeta base se conserva por medio de `RecursiveDir`. Si no se especifica `LinkBase`, se omite de la ruta a `Link`.

```xml
<ItemGroup>
  <Content Include="..\Extras\**\*.cs" LinkBase="Shared"/>
</ItemGroup>
```

En la imagen siguiente, se ilustra cómo se muestra globalmente un archivo incluido en el elemento anterior `Include` en el Explorador de soluciones.

:::image type="content" source="media/solution-explorer-linkbase.png" alt-text="Elemento con metadatos de LinkBase en el Explorador de soluciones.":::

### <a name="appendtargetframeworktooutputpath"></a>AppendTargetFrameworkToOutputPath

La propiedad `AppendTargetFrameworkToOutputPath` controla si el [moniker de la plataforma de destino (TFM)](../../standard/frameworks.md) se anexa a la ruta de salida (definida por [OutputPath](/visualstudio/msbuild/common-msbuild-project-properties#list-of-common-properties-and-parameters)). El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida. El hecho de establecer `AppendTargetFrameworkToOutputPath` en `false` impide que el TFM se anexe a la ruta de salida. Sin embargo, sin el TFM en la ruta de salida, es posible que varios artefactos de compilación se sobrescriban entre sí.

Por ejemplo, en el caso de una aplicación de .NET 5.0, la ruta de salida cambia de `bin\Debug\net5.0` a `bin\Debug` con la opción de configuración siguiente:

```xml
<PropertyGroup>
  <AppendTargetFrameworkToOutputPath>false</AppendTargetFrameworkToOutputPath>
</PropertyGroup>
```

### <a name="appendruntimeidentifiertooutputpath"></a>AppendRuntimeIdentifierToOutputPath

La propiedad `AppendRuntimeIdentifierToOutputPath` controla si el [id. del entorno de ejecución (RID)](../rid-catalog.md) se anexa a la ruta de salida. El SDK de .NET anexa automáticamente el marco de destino (y, si está disponible, también el id. del entorno de ejecución) a la ruta de salida. El hecho de establecer `AppendRuntimeIdentifierToOutputPath` en `false` impide que el RID se anexe a la ruta de salida.

Por ejemplo, en el caso de una aplicación de .NET 5.0 y un RID de `win10-x64`, la ruta de salida cambia de `bin\Debug\net5.0\win10-x64` a `bin\Debug\net5.0` con la opción de configuración siguiente:

```xml
<PropertyGroup>
  <AppendRuntimeIdentifierToOutputPath>false</AppendRuntimeIdentifierToOutputPath>
</PropertyGroup>
```

### <a name="copylocallockfileassemblies"></a>CopyLocalLockFileAssemblies

La propiedad `CopyLocalLockFileAssemblies` es útil para los proyectos de complementos que tienen dependencias de otras bibliotecas. Si establece esta propiedad en `true`, todas las dependencias de paquetes NuGet se copian en el directorio de salida. Esto significa que puede usar la salida de `dotnet build` para ejecutar el complemento en cualquier equipo.

```xml
<PropertyGroup>
  <CopyLocalLockFileAssemblies>true</CopyLocalLockFileAssemblies>
</PropertyGroup>
```

> [!TIP]
> Como alternativa, puede usar `dotnet publish` para publicar la biblioteca de clases. Para obtener más información, vea [dotnet publish](../tools/dotnet-publish.md).

### <a name="preservecompilationcontext"></a>PreserveCompilationContext

La propiedad `PreserveCompilationContext` permite a una aplicación creada o publicada compilar más código en tiempo de ejecución con la misma configuración que se utilizó en el momento de la creación. Los ensamblados a los que se hace referencia en el tiempo de compilación se copiarán en el subdirectorio *ref* del directorio de salida. Los nombres de los ensamblados de referencia se almacenan en el archivo *.deps.json* de la aplicación junto con las opciones que se pasan al compilador. Puede recuperar esta información mediante las propiedades <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompileLibraries?displayProperty=nameWithType> y <xref:Microsoft.Extensions.DependencyModel.DependencyContext.CompilationOptions?displayProperty=nameWithType>.

Esta funcionalidad la usan principalmente MVC de ASP.NET Core y páginas Razor para admitir la compilación en tiempo de ejecución de archivos Razor.

```xml
<PropertyGroup>
  <PreserveCompilationContext>true</PreserveCompilationContext>
</PropertyGroup>
```

### <a name="preservecompilationreferences"></a>PreserveCompilationReferences

La propiedad `PreserveCompilationReferences` es similar a la propiedad [PreserveCompilationContext](#preservecompilationcontext), salvo que solo copia los ensamblados a los que se hace referencia en el directorio de publicación, sin el archivo *.deps.json*.

```xml
<PropertyGroup>
  <PreserveCompilationReferences>true</PreserveCompilationReferences>
</PropertyGroup>
```

Para obtener más información, consulte las [propiedades del SDK de Razor](/aspnet/core/razor-pages/sdk#properties).

### <a name="runtimeidentifier"></a>RuntimeIdentifier

La propiedad `RuntimeIdentifier` permite especificar un único [identificador de tiempo de ejecución (RID)](../rid-catalog.md) para el proyecto. El RID permite publicar una implementación autocontenida.

```xml
<PropertyGroup>
  <RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
</PropertyGroup>
```

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers

La propiedad `RuntimeIdentifiers` permite especificar una lista delimitada por puntos y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Use esta propiedad si tiene que publicar para varios entornos de ejecución. `RuntimeIdentifiers` se usa en el momento de la restauración para asegurarse de que los recursos adecuados están en el gráfico.

> [!TIP]
> `RuntimeIdentifier` (singular) puede proporcionar compilaciones más rápidas cuando solo se requiere un entorno de ejecución.

```xml
<PropertyGroup>
  <RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
</PropertyGroup>
```

### <a name="trimmerrootassembly"></a>TrimmerRootAssembly

El elemento `TrimmerRootAssembly` permite excluir del [*recorte*](../deploying/trim-self-contained.md) un ensamblado. El recorte es el proceso de quitar de una aplicación empaquetada las partes que no se han usado del tiempo de ejecución. En algunos casos, el recorte podría quitar de forma incorrecta las referencias necesarias.

El siguiente código XML excluye del recorte el ensamblado `System.Security`.

```xml
<ItemGroup>
  <TrimmerRootAssembly Include="System.Security" />
</ItemGroup>
```

### <a name="useapphost"></a>UseAppHost

La propiedad `UseAppHost` controla si se crea o no un archivo ejecutable nativo para una implementación. Un archivo ejecutable nativo es obligatorio para las implementaciones independientes.

En .NET Core 3.0 y versiones posteriores, se crea de forma predeterminada un ejecutable dependiente del marco de trabajo. Establezca la propiedad `UseAppHost` en `false` para deshabilitar la generación del archivo ejecutable.

```xml
<PropertyGroup>
  <UseAppHost>false</UseAppHost>
</PropertyGroup>
```

Para más información sobre la implementación, consulte [Implementación de aplicaciones .NET](../deploying/index.md).

## <a name="compile-properties"></a>Propiedades de compilación

- [EmbeddedResourceUseDependentUponConvention](#embeddedresourceusedependentuponconvention)
- [LangVersion](#langversion)

### <a name="embeddedresourceusedependentuponconvention"></a>EmbeddedResourceUseDependentUponConvention

La propiedad `EmbeddedResourceUseDependentUponConvention` define si los nombres del archivo de manifiesto del recurso se generan a partir de la información de tipo de los archivos de código fuente que se ubican conjuntamente con archivos de recursos. Por ejemplo, si *Form1.resx* está en la misma carpera que *Form1.cs*, y `EmbeddedResourceUseDependentUponConvention` se establece en `true`, el archivo *.resources* generado toma su nombre del primer tipo que se define en *Form1.cs*. Por ejemplo, si `MyNamespace.Form1` es el primer tipo definido en *Form1.cs*, el nombre de archivo generado es *myNameSpace.Form1.Resources*.

> [!NOTE]
> Si se especifican los metadatos `LogicalName`, `ManifestResourceName` o `DependentUpon` para un elemento `EmbeddedResource`, el nombre del archivo de manifiesto generado para ese archivo de recurso se basa en esos metadatos.

De forma predeterminada, en un nuevo proyecto de .NET, esta propiedad se establece en `true`. Si se establece en `false` y no se especifica ningún metadato `LogicalName`, `ManifestResourceName` o `DependentUpon` para el elemento `EmbeddedResource` del archivo de proyecto, el nombre del archivo de manifiesto del recurso se basa en el espacio de nombres raíz del proyecto y en la ruta de acceso relativa al archivo *.resx*. Para más información, consulte [Denominación de los archivos de manifiesto de recurso](../resources/manifest-file-names.md).

```xml
<PropertyGroup>
  <EmbeddedResourceUseDependentUponConvention>true</EmbeddedResourceUseDependentUponConvention>
</PropertyGroup>
```

### <a name="langversion"></a>LangVersion

La propiedad `LangVersion` permite especificar una versión concreta del lenguaje de programación. Por ejemplo, si quiere acceder a las características en vista previa de C#, establezca `LangVersion` en `preview`.

```xml
<PropertyGroup>
  <LangVersion>preview</LangVersion>
</PropertyGroup>
```

Para obtener más información, vea [Control de versiones del lenguaje C#](../../csharp/language-reference/configure-language-version.md#override-a-default).

## <a name="default-item-inclusion-properties"></a>Propiedades de inclusión de elementos predeterminados

- [DefaultExcludesInProjectFolder](#defaultexcludesinprojectfolder)
- [DefaultItemExcludes](#defaultitemexcludes)
- [EnableDefaultCompileItems](#enabledefaultcompileitems)
- [EnableDefaultEmbeddedResourceItems](#enabledefaultembeddedresourceitems)
- [EnableDefaultItems](#enabledefaultitems)
- [EnableDefaultNoneItems](#enabledefaultnoneitems)

Para obtener más información, consulte [Inclusiones y exclusiones predeterminadas](overview.md#default-includes-and-excludes).

### <a name="defaultitemexcludes"></a>DefaultItemExcludes

Use la propiedad `DefaultItemExcludes` para definir patrones globales para archivos y carpetas que deban excluirse de los patrones globales de inclusión, exclusión y eliminación. De forma predeterminada, las carpetas *./bin* y *./obj* se excluyen de los patrones globales.

```xml
<PropertyGroup>
  <DefaultItemExcludes>$(DefaultItemExcludes);**/*.myextension</DefaultItemExcludes>
</PropertyGroup>
```

### <a name="defaultexcludesinprojectfolder"></a>DefaultExcludesInProjectFolder

Use la propiedad `DefaultExcludesInProjectFolder` para definir patrones globales para archivos y carpetas de la carpeta del proyecto que deban excluirse de los patrones globales de inclusión, exclusión y eliminación. De forma predeterminada, las carpetas que empiezan por un punto (`.`), como *.git* y *.vs*, se excluyen de los patrones globales.

Esta propiedad es muy similar a otra, `DefaultItemExcludes`, salvo por el hecho de que esta solo tiene en cuenta los archivos y las carpetas de la carpeta del proyecto. En el caso de que un patrón global pretenda, de forma no intencionada, relacionar elementos de fuera de la carpeta del proyecto con una ruta de acceso relativa, use la propiedad `DefaultExcludesInProjectFolder`, en lugar de `DefaultItemExcludes`.

```xml
<PropertyGroup>
  <DefaultExcludesInProjectFolder>$(DefaultExcludesInProjectFolder);**/myprefix*/**</DefaultExcludesInProjectFolder>
</PropertyGroup>
```

### <a name="enabledefaultitems"></a>EnableDefaultItems

La propiedad `EnableDefaultItems` controla si los elementos de compilación, los elementos de los recursos incrustados y los elementos `None` se incluyen en el proyecto de forma implícita. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultItems` en `false` para deshabilitar toda inclusión de archivos implícita.

```xml
<PropertyGroup>
  <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="enabledefaultcompileitems"></a>EnableDefaultCompileItems

La propiedad `EnableDefaultCompileItems` controla si los elementos de compilación se incluyen en el proyecto de forma implícita. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultCompileItems` en `false` para deshabilitar la inclusión implícita de los archivos *.cs, así como la de otras extensiones de nombres de archivos.

```xml
<PropertyGroup>
  <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```

### <a name="enabledefaultembeddedresourceitems"></a>EnableDefaultEmbeddedResourceItems

La propiedad `EnableDefaultEmbeddedResourceItems` controla si los elementos de los recursos incrustados se incluyen en el proyecto de forma implícita. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultEmbeddedResourceItems` en `false` para deshabilitar la inclusión implícita de los archivos de los recursos incrustados.

```xml
<PropertyGroup>
  <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
</PropertyGroup>
```

### <a name="enabledefaultnoneitems"></a>EnableDefaultNoneItems

La propiedad `EnableDefaultNoneItems` controla si los elementos `None` (archivos que no tienen ningún rol en el proceso de compilación) se incluyen implícitamente en el proyecto. El valor predeterminado es `true`. Establezca la propiedad `EnableDefaultNoneItems` en `false` para deshabilitar la inclusión implícita de elementos `None`.

```xml
<PropertyGroup>
  <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
</PropertyGroup>
```

## <a name="code-analysis-properties"></a>Propiedades de análisis de código

- [AnalysisLevel](#analysislevel)
- [AnalysisMode](#analysismode)
- [CodeAnalysisTreatWarningsAsErrors](#codeanalysistreatwarningsaserrors)
- [EnableNETAnalyzers](#enablenetanalyzers)
- [EnforceCodeStyleInBuild](#enforcecodestyleinbuild)

### <a name="analysislevel"></a>AnalysisLevel

La propiedad `AnalysisLevel` permite especificar un nivel de análisis de código. Por ejemplo, si quiere acceder a la versión preliminar de los analizadores de código, establezca `AnalysisLevel` en `preview`.

Valor predeterminado:

- Si el proyecto tiene como destino .NET 5.0 o posterior, o si ha agregado la propiedad [AnalysisMode](#analysismode), el valor predeterminado es `latest`.
- De lo contrario, se omite esta propiedad, a menos que se agregue explícitamente al archivo de proyecto.

```xml
<PropertyGroup>
  <AnalysisLevel>preview</AnalysisLevel>
</PropertyGroup>
```

En la siguiente tabla se muestran las opciones disponibles.

| Value | Significado |
|-|-|
| `latest` | Se usan los analizadores de código que se han publicado más recientemente. Este es el valor predeterminado. |
| `preview` | Se usan los analizadores de código más recientes, incluso si están en versión preliminar. |
| `5.0` | Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles. |
| `5` | Se usa el conjunto de reglas que se habilitó para .NET 5,0, incluso si hay reglas más recientes disponibles. |

> [!NOTE]
> Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.

### <a name="analysismode"></a>AnalysisMode

A partir de .NET 5.0, el SDK de .NET incluye todas las [reglas "CA" de calidad del código](../../fundamentals/code-analysis/quality-rules/index.md). De forma predeterminada, solo [algunas reglas están habilitadas](../../fundamentals/code-analysis/overview.md#enabled-rules) como advertencias de compilación. La propiedad `AnalysisMode` le permite personalizar el conjunto de reglas que están habilitadas de forma predeterminada. Puede cambiar a un modo de análisis más agresivo (exclusión) o a uno más conservador (inclusión). Por ejemplo, si quiere habilitar todas las reglas de forma predeterminada como advertencias de compilación, establezca el valor en `AllEnabledByDefault`.

```xml
<PropertyGroup>
  <AnalysisMode>AllEnabledByDefault</AnalysisMode>
</PropertyGroup>
```

En la siguiente tabla se muestran las opciones disponibles.

| Value | Significado |
|-|-|
| `Default` | Modo predeterminado, en el que ciertas reglas están habilitadas como advertencias de compilación, otras están habilitadas como sugerencias del IDE de Visual Studio y el resto están deshabilitadas. |
| `AllEnabledByDefault` | Modo agresivo o de exclusión, en el que todas las reglas están habilitadas de forma predeterminada como advertencias de compilación. Puede [excluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para deshabilitarlas. |
| `AllDisabledByDefault` | Modo conservador o de inclusión, en el que todas las reglas están deshabilitadas de forma predeterminada. Puede [incluir](../../fundamentals/code-analysis/configuration-options.md) de forma selectiva reglas individuales para habilitarlas. |

> [!NOTE]
> Esta propiedad no tiene ningún efecto en el análisis de código de los proyectos que no hacen referencia a un [SDK de proyecto](overview.md), por ejemplo, los proyectos de .NET Framework heredados que hacen referencia al paquete NuGet Microsoft.CodeAnalysis.NetAnalyzers.

### <a name="codeanalysistreatwarningsaserrors"></a>CodeAnalysisTreatWarningsAsErrors

La propiedad `CodeAnalysisTreatWarningsAsErrors` le permite configurar si las advertencias de análisis de calidad del código (CAxxxx) se deben tratar como advertencias e interrumpir la compilación. Si usa la marca `-warnaserror` al compilar los proyectos, las advertencias de [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) también se tratan como errores. Si no quiere que las advertencias de análisis de calidad del código se traten como errores, puede establecer la propiedad `CodeAnalysisTreatWarningsAsErrors` de MSBuild en `false` en el archivo del proyecto.

```xml
<PropertyGroup>
  <CodeAnalysisTreatWarningsAsErrors>false</CodeAnalysisTreatWarningsAsErrors>
</PropertyGroup>
```

### <a name="enablenetanalyzers"></a>EnableNETAnalyzers

De forma predeterminada, el [análisis de calidad del código de .NET](../../fundamentals/code-analysis/overview.md#code-quality-analysis) está habilitado para los proyectos que tienen como destino .NET 5.0 o una versión posterior. Puede habilitar el análisis de código de .NET para los proyectos de estilo SDK que tienen como destino versiones anteriores de .NET si establece la propiedad `EnableNETAnalyzers` en `true`. Para deshabilitar el análisis de código en cualquier proyecto, establezca esta propiedad en `false`.

```xml
<PropertyGroup>
  <EnableNETAnalyzers>true</EnableNETAnalyzers>
</PropertyGroup>
```

### <a name="enforcecodestyleinbuild"></a>EnforceCodeStyleInBuild

> [!NOTE]
> En la actualidad, esta característica es experimental y puede cambiar entre las versiones .NET 5 y .NET 6.

El [análisis del estilo del código de .NET](../../fundamentals/code-analysis/overview.md#code-style-analysis) está deshabilitado de forma predeterminada en la compilación para todos los proyectos de .NET. Puede habilitar el análisis del estilo del código para los proyectos de .NET estableciendo la propiedad `EnforceCodeStyleInBuild` en `true`.

```xml
<PropertyGroup>
  <EnforceCodeStyleInBuild>true</EnforceCodeStyleInBuild>
</PropertyGroup>
```

Todas las reglas de estilo del código [configuradas](../../fundamentals/code-analysis/overview.md#code-style-analysis) como advertencias o errores se ejecutarán en la compilación y notificarán infracciones.

## <a name="run-time-configuration-properties"></a>Propiedades de configuración del tiempo de ejecución

Puede configurar algunos comportamientos del tiempo de ejecución si especifica las propiedades de MSBuild en el archivo de proyecto de la aplicación. Para obtener información sobre otras formas de configurar el comportamiento del tiempo de ejecución, consulte [Opciones de configuración en tiempo de ejecución de .NET Core](../run-time-config/index.md).

- [ConcurrentGarbageCollection](#concurrentgarbagecollection)
- [InvariantGlobalization](#invariantglobalization)
- [RetainVMGarbageCollection](#retainvmgarbagecollection)
- [ServerGarbageCollection](#servergarbagecollection)
- [ThreadPoolMaxThreads](#threadpoolmaxthreads)
- [ThreadPoolMinThreads](#threadpoolminthreads)
- [TieredCompilation](#tieredcompilation)
- [TieredCompilationQuickJit](#tieredcompilationquickjit)
- [TieredCompilationQuickJitForLoops](#tieredcompilationquickjitforloops)

### <a name="concurrentgarbagecollection"></a>ConcurrentGarbageCollection

La propiedad `ConcurrentGarbageCollection` configura si está habilitada la [recolección de elementos no utilizados en segundo plano (simultánea)](../../standard/garbage-collection/background-gc.md). Establezca el valor en `false` para deshabilitar la recolección de elementos no utilizados en segundo plano. Para obtener más información, vea [Recolección de elementos no utilizados en segundo plano](../run-time-config/garbage-collector.md#background-gc).

```xml
<PropertyGroup>
  <ConcurrentGarbageCollection>false</ConcurrentGarbageCollection>
</PropertyGroup>
```

### <a name="invariantglobalization"></a>InvariantGlobalization

La propiedad `InvariantGlobalization` configura si la aplicación se ejecuta en modo *invariable de globalización*, lo que significa que no tiene acceso a datos específicos de la referencia cultural. Establezca el valor en `true` para ejecutar en el modo invariable de globalización. Para obtener más información, consulte [Modo invariable](../run-time-config/globalization.md#invariant-mode).

```xml
<PropertyGroup>
  <InvariantGlobalization>true</InvariantGlobalization>
</PropertyGroup>
```

### <a name="retainvmgarbagecollection"></a>RetainVMGarbageCollection

La propiedad `RetainVMGarbageCollection` configura el recolector de elementos no utilizados para colocar los segmentos de memoria eliminados en una lista en espera para su uso futuro o para liberarlos. Al establecer el valor en `true`, se indica al recolector de elementos no utilizados que coloque los segmentos en una lista en espera. Para obtener más información, vea [Retain VM (Conservar VM)](../run-time-config/garbage-collector.md#retain-vm).

```xml
<PropertyGroup>
  <RetainVMGarbageCollection>true</RetainVMGarbageCollection>
</PropertyGroup>
```

### <a name="servergarbagecollection"></a>ServerGarbageCollection

La propiedad `ServerGarbageCollection` configura si la aplicación usa la [recolección de elementos no utilizados de estación de trabajo o la de servidor](../../standard/garbage-collection/workstation-server-gc.md). Establezca el valor en `true` para usar la recolección de elementos no utilizados de servidor. Para obtener más información, vea [Estación de trabajo frente a servidor](../run-time-config/garbage-collector.md#workstation-vs-server).

```xml
<PropertyGroup>
  <ServerGarbageCollection>true</ServerGarbageCollection>
</PropertyGroup>
```

### <a name="threadpoolmaxthreads"></a>ThreadPoolMaxThreads

La propiedad `ThreadPoolMaxThreads` configura el número máximo de subprocesos para el grupo de subprocesos de trabajo. Para obtener más información, consulte [Máximo de subprocesos](../run-time-config/threading.md#maximum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMaxThreads>20</ThreadPoolMaxThreads>
</PropertyGroup>
```

### <a name="threadpoolminthreads"></a>ThreadPoolMinThreads

La propiedad `ThreadPoolMinThreads` configura el número mínimo de subprocesos para el grupo de subprocesos de trabajo. Para obtener más información, consulte [Mínimo de subprocesos](../run-time-config/threading.md#minimum-threads).

```xml
<PropertyGroup>
  <ThreadPoolMinThreads>4</ThreadPoolMinThreads>
</PropertyGroup>
```

### <a name="tieredcompilation"></a>TieredCompilation

La propiedad `TieredCompilation` configura si el compilador Just-In-Time (JIT) usa la [compilación en niveles](../whats-new/dotnet-core-3-0.md#tiered-compilation). Establezca el valor en `false` para deshabilitar la compilación en niveles. Para obtener más información, vea [Compilación en niveles](../run-time-config/compilation.md#tiered-compilation).

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

### <a name="tieredcompilationquickjit"></a>TieredCompilationQuickJit

La propiedad `TieredCompilationQuickJit` configura si el compilador JIT usa JIT rápido. Establezca el valor en `false` para deshabilitar JIT rápido. Para obtener más información, vea [JIT rápido](../run-time-config/compilation.md#quick-jit).

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

### <a name="tieredcompilationquickjitforloops"></a>TieredCompilationQuickJitForLoops

La propiedad `TieredCompilationQuickJitForLoops` configura si el compilador JIT usa JIT rápido en métodos que contienen bucles. Establezca el valor en `true` para habilitar JIT rápido en métodos que contienen bucles. Para obtener más información, vea [JIT rápido para bucles](../run-time-config/compilation.md#quick-jit-for-loops).

```xml
<PropertyGroup>
  <TieredCompilationQuickJitForLoops>true</TieredCompilationQuickJitForLoops>
</PropertyGroup>
```

## <a name="reference-properties-and-items"></a>Referencia de propiedades y elementos

- [AssetTargetFallback](#assettargetfallback)
- [DisableImplicitFrameworkReferences](#disableimplicitframeworkreferences)
- [PackageReference](#packagereference)
- [ProjectReference](#projectreference)
- [Referencia](#reference)
- [Propiedades relacionadas con la restauración](#restore-related-properties)

### <a name="assettargetfallback"></a>AssetTargetFallback

La propiedad `AssetTargetFallback` permite especificar versiones de la plataforma compatibles adicionales para las referencias de proyectos y los paquetes NuGet. Por ejemplo, si se especifica una dependencia de paquete mediante `PackageReference` pero ese paquete no contiene recursos compatibles con el valor `TargetFramework` del proyecto, entra en juego la propiedad `AssetTargetFallback`. La compatibilidad del paquete al que se hace referencia se vuelve a comprobar con cada plataforma de destino que se especifica en `AssetTargetFallback`. Esta propiedad reemplaza la propiedad en desuso `PackageTargetFallback`.

Puede establecer la propiedad `AssetTargetFallback` en una o varias [versiones de plataforma de destino](../../standard/frameworks.md#supported-target-frameworks).

```xml
<PropertyGroup>
  <AssetTargetFallback>net461</AssetTargetFallback>
</PropertyGroup>
```

### <a name="disableimplicitframeworkreferences"></a>DisableImplicitFrameworkReferences

La propiedad `DisableImplicitFrameworkReferences` controla los elementos `FrameworkReference` implícitos cuando el destino es .NET Core 3.0 y versiones posteriores. Cuando el destino es .NET Core 2.1 o .NET Standard 2.0 y versiones anteriores, controla los elementos [PackageReference](#packagereference) implícitos en los paquetes de un metapaquete. (Un metapaquete es un paquete basado en la plataforma que consta únicamente de dependencias en otros paquetes). Esta propiedad también controla las referencias implícitas como `System` y `System.Core` cuando el destino es .NET Framework.

Establezca esta propiedad en `true` para deshabilitar los elementos `FrameworkReference` o [PackageReference](#packagereference) implícitos. Si establece esta propiedad en `true`, puede agregar referencias explícitas solo a las plataformas o paquetes que necesite.

```xml
<PropertyGroup>
  <DisableImplicitFrameworkReferences>true</DisableImplicitFrameworkReferences>
</PropertyGroup>
```

### <a name="packagereference"></a>PackageReference

El elemento `PackageReference` define una referencia a un paquete NuGet.

El atributo `Include` especifica el identificador del paquete. El atributo `Version` especifica la versión o el intervalo de versiones. Para obtener más información sobre cómo especificar una versión mínima, una máxima, un intervalo o una coincidencia exacta, vea [Intervalos de versiones](/nuget/concepts/package-versioning#version-ranges). También puede agregar [atributos de recurso](#asset-attributes) a una referencia de paquete.

El fragmento del archivo del proyecto del ejemplo siguiente hace referencia al paquete [System.Runtime](https://www.nuget.org/packages/System.Runtime/).

```xml
<ItemGroup>
  <PackageReference Include="System.Runtime" Version="4.3.0" />
</ItemGroup>
```

Para obtener más información, vea [Referencias de paquete en un archivo del proyecto](/nuget/consume-packages/package-references-in-project-files).

#### <a name="asset-attributes"></a>Atributos de recurso

Los metadatos de `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` se pueden agregar a una referencia de paquete.

| Atributo | Descripción |
| - | - |
| `IncludeAssets` | Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` se deben consumir. De forma predeterminada, se incluyen todos los recursos del paquete. |
| `ExcludeAssets`| Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` no se deben consumir. |
| `PrivateAssets` | Indica qué recursos pertenecientes al paquete especificado por `<PackageReference>` se deben consumir, pero no pasar al proyecto siguiente. Cuando este atributo no está presente, los recursos `Analyzers`, `Build` y `ContentFiles` son privados de forma predeterminada. |

Estos atributos pueden contener uno o varios de los siguientes elementos, separados por punto y coma (`;`), si aparece más de uno:

- `Compile`: el contenido de la carpeta *lib* está disponible para compilación.
- `Runtime`: el contenido de la carpeta *runtime* está distribuido.
- `ContentFiles`: se usa el contenido de la carpeta *contentfiles*.
- `Build`: se usan los archivos props/targets de la carpeta *build*.
- `Native`: el contenido de recursos nativos se copia en la carpeta *output* en runtime.
- `Analyzers`: se usan los analizadores.

Como alternativa, el atributo puede contener:

- `None`: no se usa ninguno de los recursos.
- `All`: se usan todos los recursos.

### <a name="projectreference"></a>ProjectReference

El elemento `ProjectReference` define una referencia a otro proyecto. El proyecto al que se hace referencia se agrega como una dependencia del paquete NuGet, es decir, se trata como `PackageReference`.

El atributo `Include` especifica la ruta de acceso al proyecto. También puede agregar los metadatos `IncludeAssets`, `ExcludeAssets` y `PrivateAssets` a una referencia de proyecto.

El fragmento del archivo de proyecto de este ejemplo hace referencia a un proyecto denominado `Project2`.

```xml
<ItemGroup>
  <ProjectReference Include="..\Project2.csproj" />
</ItemGroup>
```

### <a name="reference"></a>Referencia

El elemento `Reference` define una referencia a un archivo de ensamblado.

El atributo `Include` especifica el nombre del archivo y los metadatos `HintPath` especifican la ruta de acceso al ensamblado.

```xml
<ItemGroup>
  <Reference Include="MyAssembly">
    <HintPath>..\..\Assemblies\MyAssembly.dll</HintPath>
  </Reference>
</ItemGroup>
```

### <a name="restore-related-properties"></a>Propiedades relacionadas con la restauración

La restauración de un paquete al que se hace referencia instala todas sus dependencias directas y todas las dependencias de esas dependencias. Puede personalizar la restauración de paquetes especificando propiedades como `RestorePackagesPath` y `RestoreIgnoreFailedSources`. Para más información sobre estas y otras propiedades, vea [Destino de restore](/nuget/reference/msbuild-targets#restore-target).

```xml
<PropertyGroup>
  <RestoreIgnoreFailedSource>true</RestoreIgnoreFailedSource>
</PropertyGroup>
```

## <a name="run-properties"></a>Propiedades de Run

Las siguientes propiedades se usan para iniciar una aplicación con el comando [`dotnet run`](../tools/dotnet-run.md):

- [RunArguments](#runarguments)
- [RunWorkingDirectory](#runworkingdirectory)

### <a name="runarguments"></a>RunArguments

La propiedad `RunArguments` define los argumentos que se pasan a la aplicación cuando se ejecuta.

```xml
<PropertyGroup>
  <RunArguments>-mode dryrun</RunArguments>
</PropertyGroup>
```

> [!TIP]
> Puede especificar los argumentos adicionales que se pasarán a la aplicación mediante la opción [`--` para `dotnet run`](../tools/dotnet-run.md#options).

### <a name="runworkingdirectory"></a>RunWorkingDirectory

La propiedad `RunWorkingDirectory` define el directorio de trabajo en el que se iniciará el proceso. Puede ser una ruta de acceso absoluta o relativa al directorio del proyecto. Si no se especifica un directorio, se usa `OutDir` como directorio de trabajo.

```xml
<PropertyGroup>
  <RunWorkingDirectory>c:\temp</RunWorkingDirectory>
</PropertyGroup>
```

## <a name="hosting-properties"></a>Propiedades de hospedaje

- [EnableComHosting](#enablecomhosting)
- [EnableDynamicLoading](#enabledynamicloading)

### <a name="enablecomhosting"></a>EnableComHosting

La propiedad `EnableComHosting` indica que un ensamblado proporciona un servidor COM. Al establecer `EnableComHosting` en `true` también implica que [EnableDynamicLoading](#enabledynamicloading) es `true`.

```xml
<PropertyGroup>
  <EnableComHosting>True</EnableComHosting>
</PropertyGroup>
```

Para obtener más información, vea [Exposición de componentes de .NET en COM](../native-interop/expose-components-to-com.md).

### <a name="enabledynamicloading"></a>EnableDynamicLoading

La propiedad `EnableDynamicLoading` indica que un ensamblado es un componente cargado dinámicamente. El componente podría ser una [biblioteca de COM](/windows/win32/com/the-component-object-model) o una biblioteca que no es de COM que se puede [usar desde un host nativo](../tutorials/netcore-hosting.md). Establecer esta propiedad en `true` tiene los efectos siguientes:

- Se genera un archivo *runtimeconfig.json*.
- La [puesta al día](../whats-new/dotnet-core-3-0.md#major-version-runtime-roll-forward) se establece en `LatestMinor`.
- Las referencias de NuGet se copian localmente.

```xml
<PropertyGroup>
  <EnableDynamicLoading>true</EnableDynamicLoading>
</PropertyGroup>
```

## <a name="see-also"></a>Vea también

- [Referencia del esquema de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference)
- [Propiedades comunes de MSBuild](/visualstudio/msbuild/common-msbuild-project-properties)
- [Propiedades de MSBuild para pack de NuGet](/nuget/reference/msbuild-targets#pack-target)
- [Propiedades de MSBuild para restore de NuGet](/nuget/reference/msbuild-targets#restore-properties)
- [Personalización de una compilación](/visualstudio/msbuild/customize-your-build)
