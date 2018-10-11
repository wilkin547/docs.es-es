---
title: Adiciones al formato csproj para .NET Core
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
author: blackdwarf
ms.author: mairaw
ms.date: 09/22/2017
ms.openlocfilehash: 1fd264da2863fbeb88900be0f6fe000acac08a09
ms.sourcegitcommit: fb78d8abbdb87144a3872cf154930157090dd933
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2018
ms.locfileid: "47216921"
---
# <a name="additions-to-the-csproj-format-for-net-core"></a>Adiciones al formato csproj para .NET Core

En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild). Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="implicit-package-references"></a>Referencias implícitas del paquete
Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto. `<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp2.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp2.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### <a name="recommendations"></a>Recomendaciones
Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library`, estos son los procedimientos recomendados:

* Si el destino es .NET Core o .NET Standard, nunca incluya una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library` mediante un elemento `<PackageReference>` en el archivo de proyecto.
* Si necesita una versión concreta del runtime cuando el destino es .NET Core, debe usar la propiedad `<RuntimeFrameworkVersion>` del proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.
    * Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.
* Si necesita una versión concreta del metapaquete `NetStandard.Library` cuando el destino es .NET Standard, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria.
* No agregue referencias a los metapaquetes `Microsoft.NETCore.App` y `NetStandard.Library` ni las actualice explícitamente en proyectos de .NET Framework. Si se necesita alguna versión de `NetStandard.Library` al usar un paquete NuGet basado en .NET Standard, NuGet instala automáticamente esa versión.

## <a name="default-compilation-includes-in-net-core-projects"></a>Inclusiones de compilación predeterminadas en proyectos .NET Core
Con el cambio al formato *csproj* en las últimas versiones del SDK, hemos trasladado las inclusiones y exclusiones predeterminadas para los elementos de compilación y los recursos incrustados a los archivos de propiedades del SDK. Esto implica que ya no tiene que especificar dichos elementos en el archivo del proyecto. 

El principal motivo de este cambio consiste en reducir el desorden en el archivo del proyecto. Los valores predeterminados presentes en el SDK deberían abarcar los casos de uso más habituales, por lo que no resulta necesario repetirlos en todos los proyectos que cree. Esto da lugar a archivos de proyecto más pequeños que resultan mucho más fáciles de entender, así como de editar manualmente si fuera necesario. 

En la siguiente tabla se muestra qué elementos y qué [globs](https://en.wikipedia.org/wiki/Glob_(programming)) se incluyen y excluyen en el SDK: 

| Elemento           | Glob para incluir                              | Glob para excluir                                                  | Glob para quitar                |
|-------------------|-------------------------------------------|---------------------------------------------------------------|----------------------------|
| Compile           | \*\*/\*.cs (u otras extensiones de lenguaje) | \*\*/\*.user;  \*\*/\*.\*proj;  \*\*/\*.sln;  \*\*/\*.vssscc  | N/D                        |
| EmbeddedResource  | \*\*/\*.resx                              | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | N/D                        |
| Ninguna              | \*\*/\*                                   | \*\*/\*.user; \*\*/\*.\*proj; \*\*/\*.sln; \*\*/\*.vssscc     | - \*\*/\*.cs; \*\*/\*.resx |

Si tiene globs en el proyecto e intenta crearlo usando el SDK más reciente, le aparecerá el siguiente error:

> Se han incluido elementos de compilación duplicados. El SDK de .NET incluye elementos de compilación del directorio del proyecto de forma predeterminada. Puede quitar estos elementos del archivo de proyecto o establecer la propiedad “EnableDefaultCompileItems” en “false” si quiere incluirlos explícitamente en el archivo del proyecto. 

Para evitar este error, puede quitar los elementos `Compile` explícitos que coinciden con los que aparecen en la tabla anterior o establecer la propiedad `<EnableDefaultCompileItems>` en `false` de esta forma:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
Al establecer esta propiedad en `false`, se invalidará la inclusión implícita y el comportamiento se revertirá a los SDK anteriores en los que tenía que especificar los globs predeterminados en el proyecto. 

Este cambio no modifica los mecanismos principales de otras inclusiones. En cambio, si quiere especificar, por ejemplo, que algunos archivos se publiquen con la aplicación, puede seguir usando los mecanismos con los que está familiarizado en *csproj* (por ejemplo, el elemento `<Content>`).

`<EnableDefaultCompileItems>` solo deshabilita globs `Compile`, pero no afecta a otros globs, como el glob `None` implícito, que también se aplica a elementos \*.cs. Por eso, el **Explorador de soluciones** sigue mostrando elementos \*.cs como parte del proyecto, incluso como elementos `None`. Del mismo modo, puede usar `<EnableDefaultNoneItems>` para deshabilitar el glob `None` implícito.

Para deshabilitar **todos los globs implícitos**, puede establecer la propiedad `<EnableDefaultItems>` en `false` como en el ejemplo siguiente:
```xml
<PropertyGroup>
    <EnableDefaultItems>false</EnableDefaultItems>
</PropertyGroup>
```

### <a name="recommendation"></a>Recomendación
Con csproj, se recomienda quitar los globs predeterminados del proyecto y agregar solo rutas de archivos con globs para aquellos artefactos que su aplicación o biblioteca necesita para varios escenarios (por ejemplo, tiempo de ejecución y empaquetado NuGet).

## <a name="how-to-see-the-whole-project-as-msbuild-sees-it"></a>Visualización del proyecto completo tal como MSBuild lo ve

Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos. Preprocese el proyecto con [el conmutador `/pp`](/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:

`dotnet msbuild -pp:fullproject.xml`

Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:

`dotnet msbuild -p:TargetFramework=netcoreapp2.0 -pp:fullproject.xml`

## <a name="additions"></a>Adiciones

### <a name="sdk-attribute"></a>Atributo Sdk 
El elemento `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`. `Sdk` especifica qué SDK usará el proyecto. El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](/visualstudio/msbuild/msbuild-tasks) y [destinos](/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core. Se incluyen dos SDK principales con las herramientas de .NET Core:

1. El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`
2. El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`

Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código. 

### <a name="packagereference"></a>PackageReference
Elemento que especifica una dependencia de NuGet en el proyecto. El atributo `Include` especifica el identificador del paquete. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### <a name="version"></a>Versión
`Version` especifica la versión del paquete que se va a restaurar. El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges). El comportamiento predeterminado es una coincidencia de versión exacta. Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.

#### <a name="includeassets-excludeassets-and-privateassets"></a>IncludeAssets, ExcludeAssets y PrivateAssets
El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir. 

El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.

El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente. 

> [!NOTE]
> `PrivateAssets` es equivalente al elemento *project.json*/*xproj* `SuppressParent`.

Estos atributos pueden contener uno o varios de los siguientes elementos:

* `Compile`: el contenido de la carpeta lib está disponible para compilación.
* `Runtime`: el contenido de la carpeta runtime está distribuido.
* `ContentFiles`: se usa el contenido de la carpeta *contentfiles*.
* `Build`: se usan los archivos props/targets de la carpeta de compilación.
* `Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.
* `Analyzers`: se usan los analizadores.

Como alternativa, el atributo puede contener:

* `None`: no se usa ninguno de los recursos.
* `All`: se usan todos los recursos.

### <a name="dotnetclitoolreference"></a>DotnetCliToolReference
El elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto. Es un sustituto del nodo `tools` de *project.json*. 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### <a name="version"></a>Versión
`Version` especifica la versión del paquete que se va a restaurar. El atributo respeta las reglas del esquema de [versiones de NuGet](/nuget/create-packages/dependency-versions#version-ranges). El comportamiento predeterminado es una coincidencia de versión exacta. Por ejemplo, si se especifica `Version="1.2.3"`, es equivalente a la notación de NuGet `[1.2.3]` para la versión exacta 1.2.3 del paquete.

### <a name="runtimeidentifiers"></a>RuntimeIdentifiers
El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Los RID permiten publicar implementaciones autocontenidas. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```

### <a name="runtimeidentifier"></a>RuntimeIdentifier
El elemento `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Los RID permiten publicar una implementación autocontenida. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```

### <a name="packagetargetfallback"></a>PackageTargetFallback 
El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes. Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM. Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet. 

En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto: 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp2.1`:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp2.1'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## <a name="nuget-metadata-properties"></a>Propiedades de metadatos de NuGet
Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete de NuGet de archivos *project.json* a *.csproj*. Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`. La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK. 

### <a name="ispackable"></a>IsPackable
Un valor booleano que especifica si se puede empaquetar el proyecto. El valor predeterminado es `true`. 

### <a name="packageversion"></a>PackageVersion
Especifica la versión que tendrá el paquete resultante. Acepta todos los formatos de la cadena de versión de NuGet. El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto. 

### <a name="packageid"></a>PackageId
Especifica el nombre para el paquete resultante. Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete. 

### <a name="title"></a>Title
Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio. Si no se especifica, se usa el identificador del paquete en su lugar.

### <a name="authors"></a>Authors
Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.

### <a name="description"></a>Description
Una descripción larga del paquete para su visualización en la interfaz de usuario.

### <a name="copyright"></a>Copyright
Detalles de copyright del paquete.

### <a name="packagerequirelicenseacceptance"></a>PackageRequireLicenseAcceptance
Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo. De manera predeterminada, es `false`.

### <a name="packagelicenseurl"></a>PackageLicenseUrl
Una dirección URL a la licencia que se aplica al paquete.

### <a name="packageprojecturl"></a>PackageProjectUrl
Una dirección URL de la página principal del paquete, que a menudo se muestra en las visualizaciones de la interfaz de usuario, así como en nuget.org.

### <a name="packageiconurl"></a>PackageIconUrl
Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.

### <a name="packagereleasenotes"></a>PackageReleaseNotes
Notas de la versión para el paquete.

### <a name="packagetags"></a>PackageTags
Una lista de etiquetas delimitada por punto y coma que designa el paquete.

### <a name="packageoutputpath"></a>PackageOutputPath
Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado. El valor predeterminado es `$(OutputPath)`. 

### <a name="includesymbols"></a>IncludeSymbols
Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto. Este paquete tendrá una extensión *.symbols.nupkg* y copiará los archivos PDB junto con el archivo DLL y otros archivos de salida.

### <a name="includesource"></a>IncludeSource
Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen. El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB. Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante. 

### <a name="istool"></a>IsTool
Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*. Tenga en cuenta que esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.

### <a name="repositoryurl"></a>RepositoryUrl
Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando. 

### <a name="repositorytype"></a>RepositoryType
Especifica el tipo del repositorio. El valor predeterminado es “git”. 

### <a name="nopackageanalysis"></a>NoPackageAnalysis
Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.

### <a name="minclientversion"></a>MinClientVersion
Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.

### <a name="includebuildoutput"></a>IncludeBuildOutput
Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.

### <a name="includecontentinpack"></a>IncludeContentInPack
Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante. De manera predeterminada, es `true`. 

### <a name="buildoutputtargetfolder"></a>BuildOutputTargetFolder
Especifica la carpeta en la que se colocarán los ensamblados de salida. Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.

### <a name="contenttargetfolders"></a>ContentTargetFolders
Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos. El valor predeterminado es “content;contentFiles”.

### <a name="nuspecfile"></a>NuspecFile
Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado. 

> [!NOTE]
> Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos. 

### <a name="nuspecbasepath"></a>NuspecBasePath
Ruta de acceso base para el archivo *.nuspec*.

### <a name="nuspecproperties"></a>NuspecProperties
Lista separada por punto y coma de pares clave=valor.

## <a name="assemblyinfo-properties"></a>Propiedades de AssemblyInfo
Los [atributos de ensamblado](../../framework/app-domains/set-assembly-attributes.md) que solían estar presentes en un archivo *AssemblyInfo* ahora se generan automáticamente a partir de las propiedades.

### <a name="properties-per-attribute"></a>Propiedades por atributo

Cada atributo tiene una propiedad que controla su contenido y otra para deshabilitar la generación, tal como se muestra en la tabla siguiente:

| Atributo                                                      | Propiedad.               | Propiedad que se va a deshabilitar                             |
|----------------------------------------------------------------|------------------------|-------------------------------------------------|
| <xref:System.Reflection.AssemblyCompanyAttribute>              | `Company`              | `GenerateAssemblyCompanyAttribute`              |
| <xref:System.Reflection.AssemblyConfigurationAttribute>        | `Configuration`        | `GenerateAssemblyConfigurationAttribute`        |
| <xref:System.Reflection.AssemblyCopyrightAttribute>            | `Copyright`            | `GenerateAssemblyCopyrightAttribute`            |
| <xref:System.Reflection.AssemblyDescriptionAttribute>          | `Description`          | `GenerateAssemblyDescriptionAttribute`          |
| <xref:System.Reflection.AssemblyFileVersionAttribute>          | `FileVersion`          | `GenerateAssemblyFileVersionAttribute`          |
| <xref:System.Reflection.AssemblyInformationalVersionAttribute> | `InformationalVersion` | `GenerateAssemblyInformationalVersionAttribute` |
| <xref:System.Reflection.AssemblyProductAttribute>              | `Product`              | `GenerateAssemblyProductAttribute`              |
| <xref:System.Reflection.AssemblyTitleAttribute>                | `AssemblyTitle`        | `GenerateAssemblyTitleAttribute`                |
| <xref:System.Reflection.AssemblyVersionAttribute>              | `AssemblyVersion`      | `GenerateAssemblyVersionAttribute`              |
| <xref:System.Resources.NeutralResourcesLanguageAttribute>      | `NeutralLanguage`      | `GenerateNeutralResourcesLanguageAttribute`     |

Notas:

* El comportamiento predeterminado de `AssemblyVersion` y `FileVersion` consiste en adoptar el valor de `$(Version)` sin sufijo. Por ejemplo, si `$(Version)` es `1.2.3-beta.4`, entonces el valor sería `1.2.3`.
* El valor predeterminado de `InformationalVersion` es el de `$(Version)`.
* `InformationalVersion` tiene `$(SourceRevisionId)` anexado si la propiedad está presente. Puede deshabilitarse mediante `IncludeSourceRevisionInInformationalVersion`.
* Las propiedades `Copyright` y `Description` también se utilizan para metadatos de NuGet.
* `Configuration` se comparte con todos los procesos de compilación y se establece mediante el parámetro `--configuration` de los comandos `dotnet`.

### <a name="generateassemblyinfo"></a>GenerateAssemblyInfo 
Un valor booleano que habilita o deshabilita toda la generación de AssemblyInfo. El valor predeterminado es `true`. 

### <a name="generatedassemblyinfofile"></a>GeneratedAssemblyInfoFile 
La ruta de acceso del archivo de información del ensamblado generado. De forma predeterminada, se trata de un archivo del directorio `$(IntermediateOutputPath)` (obj).
