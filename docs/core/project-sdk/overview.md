---
title: Información general sobre el SDK de proyectos de .NET Core
titleSuffix: ''
description: Obtenga información sobre los SDK de proyectos de .NET Core.
ms.date: 02/02/2020
ms.topic: conceptual
ms.openlocfilehash: 88ec1bf2c4917c69b80b997d090219097694d2bc
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2020
ms.locfileid: "83206059"
---
# <a name="net-core-project-sdks"></a>SDK de proyectos de .NET Core

Los proyectos de .NET Core están asociados a un kit de desarrollo de software (SDK). Cada *SDK de proyecto* es un conjunto de [destinos de MSBuild](/visualstudio/msbuild/msbuild-targets) y [tareas](/visualstudio/msbuild/msbuild-tasks) asociadas que se encarga de compilar, empaquetar y publicar código. Un proyecto que hace referencia a un SDK de proyecto en ocasiones se denomina *proyecto de estilo SDK*.

## <a name="available-sdks"></a>SDK disponibles

Los siguientes SDK están disponibles para .NET Core:

| ID | Descripción | Repositorio|
| - | - | - |
| `Microsoft.NET.Sdk` | El SDK de .NET Core | https://github.com/dotnet/sdk |
| `Microsoft.NET.Sdk.Web` | El [SDK web](/aspnet/core/razor-pages/web-sdk) de .NET Core | https://github.com/aspnet/websdk |
| `Microsoft.NET.Sdk.Razor` | El [SDK de Razor](/aspnet/core/razor-pages/sdk) de .NET Core |
| `Microsoft.NET.Sdk.Worker` | El SDK del servicio de trabajo de .NET Core |
| `Microsoft.NET.Sdk.WindowsDesktop` | El SDK WinForms y WPF de .NET Core |

El SDK de .NET Core es el SDK base de .NET Core. Los otros SDK hacen referencia al SDK de .NET Core, y los proyectos asociados a los demás SDK disponen de todas las propiedades del SDK de .NET Core. El SDK Web, por ejemplo, depende de los SDK de .NET Core y de Razor.

También puede crear un SDK propio que se puede distribuir a través de NuGet.

## <a name="project-files"></a>Archivos de proyecto

Los proyectos de .NET Core se basan en el formato [MSBuild](/visualstudio/msbuild/msbuild). Los archivos de proyecto, que tienen extensiones como *.csproj* para los proyectos de C# y *.fsproj* para los de F#, están en formato XML. El elemento raíz de un archivo de proyecto de MSBuild es [Project](/visualstudio/msbuild/project-element-msbuild). El elemento `Project` tiene un atributo `Sdk` opcional que especifica qué SDK (y versión) se van a usar. Para usar las herramientas de .NET Core y compilar el código, establezca el atributo `Sdk` en uno de los identificadores de la tabla [SDK disponibles](#available-sdks).

```xml
<Project Sdk="Microsoft.NET.Sdk">
  ...
</Project>
```

Para especificar un SDK que proviene de NuGet, incluya la versión al final del nombre, o bien especifique el nombre y la versión en el archivo *global.json*.

```xml
<Project Sdk="MSBuild.Sdk.Extras/2.0.54">
  ...
</Project>
```

Otra manera de especificar el SDK es mediante el elemento [Sdk](/visualstudio/msbuild/sdk-element-msbuild) de nivel superior:

```xml
<Project>
  <Sdk Name="Microsoft.NET.Sdk" />
  ...
</Project>
```

Al hacer referencia a un SDK de una de estas formas, se simplifican enormemente los archivos de proyecto de .NET Core. Durante la evaluación del proyecto, MSBuild agrega importaciones implícitas para `Sdk.props` en la parte superior del archivo del proyecto y para `Sdk.targets` en la inferior.

```xml
<Project>
  <!-- Implicit top import -->
  <Import Project="Sdk.props" Sdk="Microsoft.NET.Sdk" />
  ...
  <!-- Implicit bottom import -->
  <Import Project="Sdk.targets" Sdk="Microsoft.NET.Sdk" />
</Project>
```

> [!TIP]
> En un equipo con Windows, los archivos *Sdk.props* y *Sdk.targets* se pueden encontrar en la carpeta *%ProgramFiles%\dotnet\sdk\\[versión]\Sdks\Microsoft.NET.Sdk\Sdk*.

### <a name="preprocess-the-project-file"></a>Procesamiento previo del archivo del proyecto

Puede ver el proyecto totalmente expandido como MSBuild lo ve después de incluir el SDK y sus destinos mediante el comando `dotnet msbuild -preprocess`. El conmutador [preprocess](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](../tools/dotnet-msbuild.md) muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente.

Si el proyecto tiene varias plataformas de destino, para centrar los resultados del comando en una sola, debe especificarla como una propiedad de MSBuild. Por ejemplo:

`dotnet msbuild -property:TargetFramework=netcoreapp2.0 -preprocess:output.xml`

### <a name="default-compilation-includes"></a>Inclusiones de compilación predeterminadas

Las inclusiones y exclusiones predeterminadas de los elementos de compilación, los recursos insertados y los elementos `None` se definen en el SDK. A diferencia de los proyectos de .NET Framework que no son de SDK, no es necesario especificar estos elementos en el archivo del proyecto, ya que los valores predeterminados cubren los casos de uso más comunes. Como resultado, el archivo de proyecto es más pequeño y más fácil de entender y editar manualmente, si es necesario.

En la tabla siguiente se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK de .NET Core:

| Elemento           | Glob para incluir                              | Glob para excluir                                                  | Glob para quitar              |
|-------------------|-------------------------------------------|---------------------------------------------------------------|--------------------------|
| Compile           | \*\*/\*.cs (u otras extensiones de lenguaje) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | N/D                      |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                      |
| None              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | \*\*/\*.cs; \*\*/\*.resx |

> [!NOTE]
> De forma predeterminada, las carpetas `./bin` y `./obj` (representadas por las propiedades de MSBuild `$(BaseOutputPath)` y `$(BaseIntermediateOutputPath)`) se excluyen de los globs. Las exclusiones se representan por medio de la propiedad `$(DefaultItemExcludes)`.

#### <a name="build-errors"></a>Errores de compilación

Si define explícitamente cualquiera de estos elementos en el archivo del proyecto, es probable que obtenga un error de compilación "NETSDK1022" similar al siguiente:

  > Se han incluido elementos de compilación duplicados. El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada. Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto.

  > Se incluyeron elementos "EmbeddedResource" duplicados. El SDK de .NET incluye elementos "EmbeddedResource" del directorio del proyecto de forma predeterminada. Puede quitar estos elementos del archivo del proyecto, o bien establecer la propiedad "EnableDefaultEmbeddedResourceItems" en "false" si quiere incluirlos en él de forma explícita.

Para resolver los errores, lleve a cabo una de las siguientes acciones:

- Quite los elementos `Compile`, `EmbeddedResource` o `None` explícitos que coincidan con los implícitos enumerados en la tabla anterior.

- Establezca la propiedad `EnableDefaultItems` en `false` para deshabilitar toda la inclusión de archivos implícita:

  ```xml
  <PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
  </PropertyGroup>
  ```

  Si quiere especificar que se publiquen archivos con la aplicación, puede seguir usando los mecanismos de MSBuild conocidos para ello, por ejemplo, el elemento `Content`.

- Deshabilite de forma selectiva solo los globs `Compile`, `EmbeddedResource` o `None` estableciendo la propiedad `EnableDefaultCompileItems`, `EnableDefaultEmbeddedResourceItems` o `EnableDefaultNoneItems` en `false`:

  ```xml
  <PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
    <EnableDefaultEmbeddedResourceItems>false</EnableDefaultEmbeddedResourceItems>
    <EnableDefaultNoneItems>false</EnableDefaultNoneItems>
  </PropertyGroup>
  ```

  Si solo deshabilita los globs `Compile`, el Explorador de soluciones de Visual Studio sigue mostrando elementos \*.cs como parte del proyecto, incluidos como elementos `None`. Para deshabilitar el glob `None` implícito, establezca `EnableDefaultNoneItems` en `false`.

## <a name="customize-the-build"></a>Personalización de la compilación

Hay varias maneras de [personalizar una compilación](/visualstudio/msbuild/customize-your-build). Es posible que quiera invalidar una propiedad y pasarla como argumento a un comando [msbuild](/visualstudio/msbuild/msbuild-command-line-reference) o [dotnet](../tools/index.md). También puede agregar la propiedad al archivo del proyecto o a un archivo *Directory.Build.props*. Para obtener una lista de propiedades útiles para los proyectos de .NET Core, consulte [Referencia de MSBuild para proyectos de SDK de .NET Core](msbuild-props.md).

### <a name="custom-targets"></a>Destinos personalizados

Los proyectos de .NET Core pueden empaquetar propiedades y destinos de MSBuild personalizados para su uso en proyectos que consuman el paquete. Use este tipo de extensibilidad cuando quiera:

- Extender el proceso de compilación.
- Acceder a artefactos del proceso de compilación, como los archivos generados.
- Inspeccionar una configuración en la que se va a invocar la compilación.

Para agregar propiedades o destinos de compilación personalizados, coloque los archivos con el formato `<package_id>.targets` o `<package_id>.props` (por ejemplo, `Contoso.Utility.UsefulStuff.targets`) en la carpeta *build* del proyecto.

El fragmento de código XML siguiente es de un archivo *.csproj* que indica al comando [`dotnet pack`](../tools/dotnet-pack.md) lo que debe empaquetar. El elemento `<ItemGroup Label="dotnet pack instructions">` coloca los archivos de destino en la carpeta *build* dentro del paquete. El elemento `<Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">` coloca los ensamblados y los archivos *.json* en la carpeta *build*.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  ...
  <ItemGroup Label="dotnet pack instructions">
    <Content Include="build\*.targets">
      <Pack>true</Pack>
      <PackagePath>build\</PackagePath>
    </Content>
  </ItemGroup>
  <Target Name="CollectRuntimeOutputs" BeforeTargets="_GetPackageFiles">
    <!-- Collect these items inside a target that runs after build but before packaging. -->
    <ItemGroup>
      <Content Include="$(OutputPath)\*.dll;$(OutputPath)\*.json">
        <Pack>true</Pack>
        <PackagePath>build\</PackagePath>
      </Content>
    </ItemGroup>
  </Target>
  ...
  
</Project>
```

Para consumir un destino personalizado en el proyecto, agregue un elemento `PackageReference` que apunte al paquete y su versión. A diferencia de las herramientas, el paquete de destinos personalizados se incluye en el cierre de dependencia del proyecto que lo usa.

Puede configurar cómo se usa el destino personalizado. Como es un destino de MSBuild, puede depender de un destino concreto, ejecutarse después de otro destino o bien invocarse de forma manual mediante el comando `dotnet msbuild -t:<target-name>`. Pero para proporcionar una mejor experiencia de usuario, puede combinar las herramientas y los destinos personalizados por proyecto. En este escenario, la herramienta por proyecto acepta los parámetros necesarios y los traduce en la invocación de [`dotnet msbuild`](../tools/dotnet-msbuild.md) necesaria que ejecuta el destino. Puede ver una muestra de esta clase de sinergia en el [repositorio de ejemplos de MVP Summit 2016 Hackathon](https://github.com/dotnet/MVPSummitHackathon2016) del proyecto [`dotnet-packer`](https://github.com/dotnet/MVPSummitHackathon2016/tree/master/dotnet-packer).

## <a name="see-also"></a>Vea también

- [Instalación de .NET Core](../install/index.md)
- [Procedimiento para usar los SDK de proyecto de MSBuild](/visualstudio/msbuild/how-to-use-project-sdk)
- [Empaquetado de destinos y propiedades de MSBuild personalizados con NuGet](/nuget/create-packages/creating-a-package#include-msbuild-props-and-targets-in-a-package)
