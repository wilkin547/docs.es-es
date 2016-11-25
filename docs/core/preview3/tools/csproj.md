---
title: Referencia de csproj | SDK de .NET Core
description: Conozca las diferencias entre los archivos csproj de .NET Core y los existentes
keywords: referencia, csproj, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: bdc29497-64f2-4d11-a21b-4097e0bdf5c9
translationtype: Human Translation
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: af32bc592762d7e8cb4e3b180656d9c3464df4a5

---

<a name="additions-to-csproj-format-for-net-core"></a>Adiciones al formato csproj para .NET Core
----------------------------------------

# <a name="overview"></a>Información general 
En este documento se describen los cambios que se han agregado a los archivos csproj como parte del traslado de project.json a csproj y [MSBuild](https://github.com/Microsoft/MSBuild). En él solo de describen **los deltas a archivos csproj que no son de Core**. Si necesita más información sobre la sintaxis y la referencia del archivo de proyecto general, consulte la documentación del [archivo de proyecto de MSBuild](). 

> **Nota:** Este documento se ampliará en el futuro, así que compruebe a menudo por si se ha agregado nuevo contenido. 

# <a name="additions"></a>Adiciones

## <a name="packagereference"></a>PackageReference
Especifica una dependencia de NuGet en el proyecto. El atributo `Include` especifica el identificador del paquete. 

```xml
<PackageReference Include="<package-id>">
    <Version></Version>
    <PrivateAssets></PrivateAssets>
    <IncludeAssets></IncludeAssets>
    <ExcludeAssets></ExcludeAssets>
</PackageReference>
```

### <a name="version"></a>Versión
`<Version>` especifica la versión del paquete que se va a restaurar. El elemento respeta las reglas del esquema de versiones de NuGet.

### <a name="includeassets"></a>IncludeAssets
El elemento secundario `<IncludeAssets>` especifica qué recursos que pertenecen al paquete especificado en el elemento principal `<PackageReference>` se deben consumir. 

El elemento puede contener uno o varios de los siguientes valores:

* Compile �: el contenido de la carpeta lib disponible con el que se compila.
* Runtime �: el contenido de la carpeta runtime distribuida.
* ContentFiles �: el contenido de la carpeta contentfiles utilizada.
* Build �: se usan los archivos props/targets de la carpeta de compilación.
* Native: el contenido de recursos nativos copiado en la carpeta de salida en tiempo de ejecución.
* Analyzers �: se usan los analizadores.

Como alternativa, el elemento puede contener:

* None �: no se usa ninguna esas cosas.
* All �: se usan todas esas cosas.

### <a name="excludeassets"></a>ExcludeAssets
El elemento secundario `<ExcluseAssets>` especifica qué recursos que pertenecen al paquete especificado en el elemento principal `<PackageReference>` no se deben consumir.

El elemento puede contener uno o varios de los siguientes valores:

* Compile �: el contenido de la carpeta lib disponible con el que se compila.
* Runtime �: el contenido de la carpeta runtime distribuida.
* ContentFiles �: el contenido de la carpeta contentfiles utilizada.
* Build �: se usan los archivos props/targets de la carpeta de compilación.
* Native: el contenido de recursos nativos copiado en la carpeta de salida en tiempo de ejecución.
* Analyzers �: se usan los analizadores.

Como alternativa, el elemento puede contener:

* None �: no se usa ninguna esas cosas.
* All �: se usan todas esas cosas.

### <a name="privateassets"></a>PrivateAssets
El elemento secundario `<PrivateAssets>` especifica qué recursos que pertenecen al paquete especificado en el elemento principal `<PackageReference>` se deben consumir, pero que no deben pasar al proyecto siguiente. 

> **Nota:** Se trata de un nuevo término para el elemento `SupressParent` de project.json/xproj. 

El elemento puede contener uno o varios de los siguientes valores:

* Compile �: el contenido de la carpeta lib disponible con el que se compila.
* Runtime �: el contenido de la carpeta runtime distribuida.
* ContentFiles �: el contenido de la carpeta contentfiles utilizada.
* Build �: se usan los archivos props/targets de la carpeta de compilación.
* Native: el contenido de recursos nativos copiado en la carpeta de salida en tiempo de ejecución.
* Analyzers �: se usan los analizadores.

Como alternativa, el elemento puede contener:

* None �: no se usa ninguna esas cosas.
* All �: se usan todas esas cosas.

## <a name="dotnetclitoolreference"></a>DotnetCliToolReference
El elemento `<DotnetCliToolReference>` especifica la herramienta de CLI que desea restaurar el usuario en el contexto del proyecto. Es una sustitución del nodo `tools` `project.json`. 

### <a name="version"></a>Versión
`<Version>` especifica la versión del paquete que se va a restaurar. El elemento respeta las reglas del esquema de versiones de NuGet.

## <a name="runtimeidentifiers"></a>RuntimeIdentifiers
El elemento `<RuntimeIdentifiers>` permite especificar una lista delimitada por punto y coma de [identificadores en tiempo de ejecución](../../rid-catalog.md) del proyecto. Estos permiten publicar implementaciones autocontenidas. 




<!--HONumber=Nov16_HO3-->


