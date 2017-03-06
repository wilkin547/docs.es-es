---
title: Referencia de csproj | Microsoft Docs
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
keywords: referencia, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 07/02/2017
ms.topic: article
ms.prod: .net-core
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 0402707f98af8b716b041ba1260162cd227918cc
ms.openlocfilehash: 98f6ced2a199bdbe2f91f46e48ffd3ac52438cf8

---

# <a name="additions-to-the-csproj-format-for-net-core"></a>Adiciones al formato csproj para .NET Core

[!INCLUDE[preview-warning](../../../includes/warning.md)]

En este documento se describen los cambios que se han agregado a los archivos csproj como parte del traslado de `project.json` a `csproj` y [MSBuild](https://github.com/Microsoft/MSBuild). Para obtener más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-project-file-schema-reference).  

## <a name="additions"></a>Adiciones

* Elemento PackageReference que especifica una dependencia de NuGet en el proyecto. El atributo `Include` especifica el identificador del paquete. 

```xml
<PackageReference Include="<package-id>" Version="" PrivateAssets="" IncludeAssets="" ExcludeAssets="" />
```

## <a name="version"></a>Versión
`Version` especifica la versión del paquete que se va a restaurar. El elemento respeta las reglas del esquema de versiones de NuGet.

## <a name="includeassets"></a>IncludeAssets
El atributo `IncludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir. 

El atributo puede contener uno o varios de los siguientes valores:

* `Compile`: el contenido de la carpeta lib está disponible para compilación.
* `Runtime`: el contenido de la carpeta runtime está distribuido.
* `ContentFiles`: el contenido de la carpeta contentfiles se utiliza.
* `Build`: se usan los archivos props/targets de la carpeta de compilación.
* `Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.
* `Analyzers`: se usan los analizadores.

Como alternativa, el atributo puede contener:

* `None`: no se usa ninguno de los recursos.
* `All`: se usan todos los recursos.

## <a name="excludeassets"></a>ExcludeAssets
El atributo `ExcludeAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` no se deben consumir.

El atributo puede contener uno o varios de los siguientes valores:

* `Compile`: el contenido de la carpeta lib está disponible para compilación.
* `Runtime`: el contenido de la carpeta runtime está distribuido.
* `ContentFiles`: el contenido de la carpeta contentfiles se utiliza.
* `Build`: se usan los archivos props/targets de la carpeta de compilación.
* `Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.
* `Analyzers`: se usan los analizadores.

Como alternativa, el elemento puede contener:

* `None`: no se usa ninguno de los recursos.
* `All`: se usan todos los recursos.

## <a name="privateassets"></a>PrivateAssets
El atributo `PrivateAssets` especifica qué recursos que pertenecen al paquete especificado por `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente. 

> [!NOTE]
> Se trata de un nuevo término para el elemento `SuppressParent` de project.json/xproj. 

El atributo puede contener uno o varios de los siguientes valores:

* `Compile`: el contenido de la carpeta lib está disponible para compilación.
* `Runtime`: el contenido de la carpeta runtime está distribuido.
* `ContentFiles`: el contenido de la carpeta contentfiles se utiliza.
* `Build`: se usan los archivos props/targets de la carpeta de compilación.
* `Native`: el contenido de recursos nativos se copia en la carpeta de salida en tiempo de ejecución.
* `Analyzers`: se usan los analizadores.

Como alternativa, el atributo puede contener:

* `None`: no se usa ninguno de los recursos.
* `All`: se usan todos los recursos.

* El elemento `<DotnetCliToolReference>` DotnetCliToolReference especifica la herramienta de CLI que desea restaurar el usuario en el contexto del proyecto. Es una sustitución del nodo `tools` `project.json`. 

```xml
<DotnetCliToolReference Include="<package-id>" Version="" />
```

## <a name="version"></a>Versión
`Version` especifica la versión del paquete que se va a restaurar. El atributo respeta las reglas del esquema de versiones de NuGet.

* RuntimeIdentifiers El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores de tiempo ejecución (RID)](../../rid-catalog.md) para el proyecto. Los RID permiten publicar implementaciones autocontenidas. 

```xml
<RuntimeIdentifiers>win10-x64;osx.10.11-x64;ubuntu.16.04-x64</RuntimeIdentifiers>
```


* RuntimeIdentifier El elemento `<RuntieIdentifier>` permite especificar solo un [identificador de tiempo ejecución (RID)](../../rid-catalog.md) para el proyecto. Los RID permiten publicar una implementación autocontenida. 

```xml
<RuntimeIdentifier>ubuntu.16.04-x64</RuntimeIdentifier>
```


* PackageTargetFallback El elemento `<PackageTargetFallback>` permite especificar un conjunto de destinos compatibles que se usarán al restaurar los paquetes. Está diseñado para permitir que los paquetes que utilizan la dotnet TxM funcionen con paquetes que no declaran un dotnet TxM. Si el proyecto usa el dotnet TxM, todos los paquetes de los que depende también deben tienen un dotnet TxM, a menos que agregue el `<PackageTargetFallback>` a su proyecto a fin de permitir que las plataformas dotnet sean compatibles con dotnet. 

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

## <a name="nuget-metadata-properties"></a>Propiedades de metadatos de NuGet
Con el paso a MSbuild, hemos eliminado los metadatos de entrada que se utilizan cuando se empaqueta un paquete de NuGet de los archivos project.json a csproj. Las entradas son propiedades de MSBuild. La siguiente es la lista de propiedades que se utilizan como entradas para el proceso de empaquetado cuando se usa el comando `dotnet pack` o el destino de MSBuild `Pack` que es parte del SDK. 

* IsPackable
* PackageVersion
* PackageId
* Título
* Authors
* Descripción
* Copyright
* PackageRequireLicenseAcceptance
* PackageLicenseUrl
* PackageProjectUrl
* PackageIconUrl
* PackageReleaseNotes
* PackageTags
* PackageOutputPath
* IncludeSymbols
* IncludeSource
* PackageTypes
* IsTool
* RepositoryUrl
* RepositoryType
* NoPackageAnalysis
* MinClientVersion
* IncludeBuildOutput
* IncludeContentInPack
* BuildOutputTargetFolder
* ContentTargetFolders
* NuspecFile
* NuspecBasePath
* NuspecProperties


<!--HONumber=Feb17_HO2-->


