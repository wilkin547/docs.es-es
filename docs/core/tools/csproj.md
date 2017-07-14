---
title: Referencia de csproj | Microsoft Docs
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
keywords: referencia, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 05/24/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
ms.translationtype: Human Translation
ms.sourcegitcommit: e47bec77aa3b87f7a46b1c60387cbf8c1193ff17
ms.openlocfilehash: bbbf3616e7836d029116fe0b307b00001ecdd7da
ms.contentlocale: es-es
ms.lasthandoff: 06/27/2017

---

# Adiciones al formato csproj para .NET Core
<a id="additions-to-the-csproj-format-for-net-core" class="xliff"></a>

En este documento se describen los cambios que se han agregado a los archivos de proyecto como parte del cambio de *project.json* a *csproj* y [MSBuild](https://github.com/Microsoft/MSBuild). Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## Referencias implícitas del paquete
<a id="implicit-package-references" class="xliff"></a>
Se hace una referencia implícita a los metapaquetes basándose en los marcos de trabajo de destino especificados en la propiedad `<TargetFramework>` o `<TargetFrameworks>` del archivo del proyecto. `<TargetFrameworks>` se ignora si `<TargetFramework>` se especifica, independientemente del orden.

```xml
 <PropertyGroup>
   <TargetFramework>netcoreapp1.1</TargetFramework>
 </PropertyGroup>
 ```
 
 ```xml
 <PropertyGroup>
   <TargetFrameworks>netcoreapp1.1;net462</TargetFrameworks>
 </PropertyGroup>
 ```

### Recomendaciones
<a id="recommendations" class="xliff"></a>
Como se hace referencia implícitamente a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library`, estos son los procedimientos recomendados:

* Nunca tenga una referencia explícita a los metapaquetes `Microsoft.NETCore.App` o `NetStandard.Library` a través de un elemento `<PackageReference>` en el archivo de proyecto.
* Si necesita una versión específica del tiempo de ejecución, debe usar la propiedad `<RuntimeFrameworkVersion>` de su proyecto (por ejemplo, `1.0.4`) en lugar de hacer referencia al metapaquete.
    * Esto puede ocurrir si está usando [implementaciones autocontenidas](../deploying/index.md#self-contained-deployments-scd) y necesita una versión de revisión específica del tiempo de ejecución de LTS 1.0.0, por ejemplo.
* Si necesita una versión específica del metapaquete `NetStandard.Library`, puede usar la propiedad `<NetStandardImplicitPackageVersion>` y establecer la versión necesaria. 

## Inclusiones de compilación predeterminadas en proyectos .NET Core
<a id="default-compilation-includes-in-net-core-projects" class="xliff"></a>
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

### Recomendación
<a id="recommendation" class="xliff"></a>
Con csproj, se recomienda quitar los globs predeterminados del proyecto y agregar solo rutas de archivos con globs para aquellos artefactos que su aplicación o biblioteca necesita para varios escenarios (por ejemplo, tiempo de ejecución y empaquetado NuGet).

## Visualización del proyecto completo tal como MSBuild lo ve
<a id="how-to-see-the-whole-project-as-msbuild-sees-it" class="xliff"></a>

Aunque dichos cambios de csproj simplifican considerablemente los archivos de proyecto, quizá desee visualizar el proyecto totalmente expandido tal y como MSBuild lo ve después de haber incluido el SDK y sus destinos. Preprocese el proyecto con [el conmutador `/pp`](https://docs.microsoft.com/en-us/visualstudio/msbuild/msbuild-command-line-reference#preprocess) del comando [`dotnet msbuild`](dotnet-msbuild.md), que muestra qué archivos se han importado, sus orígenes y sus contribuciones a la compilación sin tener que compilar el proyecto realmente:

`dotnet msbuild /pp:fullproject.xml`

Si el proyecto tiene varios marcos de destino, los resultados del comando deben centrarse solo en uno de ellos, especificándolo como una propiedad de MSBuild:

`dotnet msbuild /p:TargetFramework=netcoreapp2.0 /pp:fullproject.xml`

## Adiciones
<a id="additions" class="xliff"></a>

### Atributo Sdk
<a id="sdk-attribute" class="xliff"></a> 
El elemento `<Project>` del archivo *.csproj* tiene un nuevo atributo denominado `Sdk`. `Sdk` especifica qué SDK usará el proyecto. El SDK, como se describe en el [documento sobre capas](cli-msbuild-architecture.md), es un conjunto de [tareas](https://docs.microsoft.com/visualstudio/msbuild/msbuild-tasks) y [destinos](https://docs.microsoft.com/visualstudio/msbuild/msbuild-targets) de MSBuild que pueden generar código de .NET Core. Se incluyen dos SDK principales con las herramientas de .NET Core:

1. El SDK de .NET Core con el id. de `Microsoft.NET.Sdk`
2. El SDK web de .NET Core con el id. de `Microsoft.NET.Sdk.Web`

Debe tener el conjunto de atributos `Sdk` establecido en uno de esos id. del elemento `<Project>` para poder usar las herramientas de .NET Core y generar el código. 

### PackageReference
<a id="packagereference" class="xliff"></a>
Elemento que especifica una dependencia de NuGet en el proyecto. El atributo `Include` especifica el identificador del paquete. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

#### Versión
<a id="version" class="xliff"></a>
`Version` especifica la versión del paquete que se va a restaurar. El elemento respeta las reglas del esquema de versiones de NuGet.

#### IncludeAssets, ExcludeAssets y PrivateAssets
<a id="includeassets-excludeassets-and-privateassets" class="xliff"></a>
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

### DotnetCliToolReference
<a id="dotnetclitoolreference" class="xliff"></a>
El elemento `<DotNetCliToolReference>` especifica la herramienta de la CLI que el usuario quiere restaurar en el contexto del proyecto. Es un sustituto del nodo `tools` de *project.json*. 

```xml
<DotNetCliToolReference Include="<package-id>" Version="" />
```

#### Versión
<a id="version" class="xliff"></a>
`Version` especifica la versión del paquete que se va a restaurar. El atributo respeta las reglas del esquema de versiones de NuGet.

### RuntimeIdentifiers
<a id="runtimeidentifiers" class="xliff"></a>
El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Los RID permiten publicar implementaciones autocontenidas. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


### RuntimeIdentifier
<a id="runtimeidentifier" class="xliff"></a>
El elemento `<RuntimeIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../rid-catalog.md) para el proyecto. Los RID permiten publicar una implementación autocontenida. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


### PackageTargetFallback
<a id="packagetargetfallback" class="xliff"></a> 
El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes. Está diseñado para permitir que los paquetes que usan la dotnet [TxM (destino x moniker)](https://docs.microsoft.com/nuget/schema/target-frameworks) funcionen con paquetes que no declaran una dotnet TxM. Si el proyecto usa la dotnet TxM, todos los paquetes de los que depende también deben tener una dotnet TxM, a menos que agregue el elemento `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas sin dotnet sean compatibles con dotnet. 

En el ejemplo siguiente se proporcionan los elementos Fallback para todos los destinos del proyecto: 

```xml
<PackageTargetFallback>
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

En el ejemplo siguiente se especifican los elementos Fallback solo para el destino `netcoreapp1.0`:

```xml
<PackageTargetFallback Condition="'$(TargetFramework)'=='netcoreapp1.0'">
    $(PackageTargetFallback);portable-net45+win8+wpa81+wp8
</PackageTargetFallback >
```

## Propiedades de metadatos de NuGet
<a id="nuget-metadata-properties" class="xliff"></a>
Con el paso a MSBuild, hemos trasladado los metadatos de entrada que se usan cuando se empaqueta un paquete de NuGet de archivos *project.json* a *.csproj*. Las entradas son propiedades de MSBuild, por lo que deben ir dentro de un grupo `<PropertyGroup>`. La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK. 

### IsPackable
<a id="ispackable" class="xliff"></a>
Un valor booleano que especifica si se puede empaquetar el proyecto. El valor predeterminado es `true`. 

### PackageVersion
<a id="packageversion" class="xliff"></a>
Especifica la versión que tendrá el paquete resultante. Acepta todos los formatos de la cadena de versión de NuGet. El valor predeterminado es `$(Version)`, es decir, de la propiedad `Version` del proyecto. 

### PackageId
<a id="packageid" class="xliff"></a>
Especifica el nombre para el paquete resultante. Si no se especifica, la operación `pack` usará de forma predeterminada el elemento `AssemblyName` o el nombre del directorio como el nombre del paquete. 

### Title
<a id="title" class="xliff"></a>
Un título fácil de usar del paquete, que se usa normalmente en las visualizaciones de la interfaz de usuario, como en nuget.org, y el Administrador de paquetes de Visual Studio. Si no se especifica, se usa el identificador del paquete en su lugar.

### Authors
<a id="authors" class="xliff"></a>
Una lista separada por punto y coma de los autores de los paquetes, que coinciden con los nombres de perfil de nuget.org. Estos se muestran en la galería de NuGet, en nuget.org, y se usan para hacer referencias cruzadas a paquetes de los mismos autores.

### Description
<a id="description" class="xliff"></a>
Una descripción larga del paquete para su visualización en la interfaz de usuario.

### Copyright
<a id="copyright" class="xliff"></a>
Detalles de copyright del paquete.

### PackageRequireLicenseAcceptance
<a id="packagerequirelicenseacceptance" class="xliff"></a>
Un valor booleano que especifica si el cliente debe pedir al consumidor que acepte la licencia del paquete antes de instalarlo. De manera predeterminada, es `false`.

### PackageLicenseUrl
<a id="packagelicenseurl" class="xliff"></a>
Una dirección URL a la licencia que se aplica al paquete.

### PackageProjectUrl
<a id="packageprojecturl" class="xliff"></a>
Una dirección URL de la página principal del paquete, que a menudo se muestra en las visualizaciones de la interfaz de usuario, así como en nuget.org.

### PackageIconUrl
<a id="packageiconurl" class="xliff"></a>
Una dirección URL para una imagen de 64 x 64 con fondo transparente para usarla como icono para el paquete en la visualización de la interfaz de usuario.

### PackageReleaseNotes
<a id="packagereleasenotes" class="xliff"></a>
Notas de la versión para el paquete.

### PackageTags
<a id="packagetags" class="xliff"></a>
Una lista de etiquetas delimitada por punto y coma que designa el paquete.

### PackageOutputPath
<a id="packageoutputpath" class="xliff"></a>
Determina la ruta de acceso de salida en la que se va a quitar el paquete empaquetado. El valor predeterminado es `$(OutputPath)`. 

### IncludeSymbols
<a id="includesymbols" class="xliff"></a>
Este valor booleano indica si el paquete debe crear un paquete de símbolos adicionales cuando se empaqueta el proyecto. Este paquete tendrá una extensión *.symbols.nupkg* y copiará los archivos PDB junto con el archivo DLL y otros archivos de salida.

### IncludeSource
<a id="includesource" class="xliff"></a>
Este valor booleano indica si el proceso de empaquetado debe crear un paquete de origen. El paquete de origen contiene el código fuente de la biblioteca, así como archivos PDB. Los archivos de origen se colocan en el directorio `src/ProjectName`, en el archivo de paquete resultante. 

### IsTool
<a id="istool" class="xliff"></a>
Especifica si se copian todos los archivos de salida en la carpeta *tools* en lugar de la carpeta *lib*. Tenga en cuenta que esto es diferente de un elemento `DotNetCliTool`, que se especifica estableciendo el elemento `PackageType` en el archivo *.csproj*.

### RepositoryUrl
<a id="repositoryurl" class="xliff"></a>
Especifica la dirección URL del repositorio donde reside el código fuente del paquete o desde el que se está creando. 

### RepositoryType
<a id="repositorytype" class="xliff"></a>
Especifica el tipo del repositorio. El valor predeterminado es “git”. 

### NoPackageAnalysis
<a id="nopackageanalysis" class="xliff"></a>
Especifica que el paquete no debe ejecutar el análisis de paquetes después de crear el paquete.

### MinClientVersion
<a id="minclientversion" class="xliff"></a>
Especifica la versión mínima del cliente de NuGet que puede instalar este paquete, aplicada por nuget.exe y el Administrador de paquetes de Visual Studio.

### IncludeBuildOutput
<a id="includebuildoutput" class="xliff"></a>
Este valor booleano especifica si se deben empaquetar los ensamblados de salida de la compilación en el archivo *.nupkg* o no.

### IncludeContentInPack
<a id="includecontentinpack" class="xliff"></a>
Este valor booleano especifica si los elementos del tipo `Content` se incluirán automáticamente en el paquete resultante. De manera predeterminada, es `true`. 

### BuildOutputTargetFolder
<a id="buildoutputtargetfolder" class="xliff"></a>
Especifica la carpeta en la que se colocarán los ensamblados de salida. Los ensamblados de salida (y otros archivos de salida) se copian en sus respectivas carpetas de marco.

### ContentTargetFolders
<a id="contenttargetfolders" class="xliff"></a>
Esta propiedad especifica la ubicación predeterminada a la que deben ir todos los archivos de contenido si no se especifica `PackagePath` para ellos. El valor predeterminado es “content;contentFiles”.

### NuspecFile
<a id="nuspecfile" class="xliff"></a>
Ruta de acceso relativa o absoluta al archivo *.nuspec* que se usa para el empaquetado. 

> [!NOTE]
> Si se especifica el archivo *.nuspec*, se usa **exclusivamente** para la información de empaquetado y no se usa ninguna de la información de los proyectos. 

### NuspecBasePath
<a id="nuspecbasepath" class="xliff"></a>
Ruta de acceso base para el archivo *.nuspec*.

### NuspecProperties
<a id="nuspecproperties" class="xliff"></a>
Lista separada por punto y coma de pares clave=valor.

