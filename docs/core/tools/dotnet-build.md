---
title: Comando dotnet-build | Microsoft Docs
description: El comando dotnet-build compila un proyecto y todas sus dependencias.
keywords: dotnet-build, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 17c2db54f871795c370a6475c21e36736a6b46c3
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-build"></a>dotnet-build

## <a name="name"></a>Name

`dotnet-build`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

```
dotnet build [project] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity]
dotnet build [--help]
```

## <a name="description"></a>Descripción
El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios. Los archivos binarios son los archivos de símbolos que se han usado para la depuración (tienen una extensión `*.pdb`), así como el código del proyecto en lenguaje intermedio (IL) con una extensión `*.dll`. Además, se generará un archivo JSON que muestra las dependencias de la aplicación con la extensión `*.deps.json`. Por último, también se generará un archivo `runtime.config.json`. Este archivo especifica en qué entorno de tiempo de ejecución compartido y en qué versión se ejecutará el código compilado. 

Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resolverán desde la caché de NuGet y no estarán disponibles en el resultado compilado del proyecto. Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina que se va a ejecutar. Esto difiere del comportamiento de .NET Framework en el que compilar un proyecto ejecutable (una aplicación) generará un resultado que puede ejecutarse en cualquier máquina que tenga .NET Framework instalado. Para obtener una experiencia similar en .NET Core, tiene que usar el comando [dotnet publish](dotnet-publish.md). Puede encontrar más información sobre esto en el documento [Implementación de aplicaciones .NET Core](../deploying/index.md). 

La compilación requiere la existencia de un archivo *assets.json* (un archivo que muestra todas las dependencias de la aplicación), lo que significa que tiene que ejecutar [`dotnet restore`](dotnet-restore.md) antes de compilar el proyecto. La falta del archivo de recursos se manifiesta como la incapacidad de las herramientas para resolver ensamblados de referencia, lo que provocará errores. 

`dotnet build` usa MSBuild para compilar el proyecto, por lo tanto admite las compilaciones en paralelo y las compilaciones incrementales. Consulte la [documentación de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild) para obtener más información sobre estos temas. 

Además de sus opciones, el comando `dotnet build` también aceptará opciones de MSBuild, como `/p` para establecer propiedades o `/l` para definir un registrador. Puede obtener más información sobre estas opciones en la documentación del comando [`dotnet msbuild`](dotnet-msbuild.md). Si quiere saber cuándo 

Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto. En el siguiente ejemplo se muestra un proyecto que generará un código ejecutable: 


```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Para generar una biblioteca, simplemente omita esa propiedad. La principal diferencia en el resultado es que el archivo de DLL de IL para una biblioteca no contendrá ningún punto de entrada y no será posible ejecutarlo. 

## <a name="arguments"></a>Argumentos

`project`

El archivo del proyecto que se va a compilar.
Si no se especifica un archivo del proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en `proj` y usa ese archivo.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción.

`-f|--framework <FRAMEWORK>`

Compila para un marco específico. El marco debe definirse en el [archivo de proyecto](csproj.md).

`-c|--configuration [Debug|Release]`

Define una configuración con la que se va a realizar la compilación. Si se omite, se adopta el valor predeterminado de `Debug`.

`-r|--runtime [RUNTIME_IDENTIFIER]`

Tiempo de ejecución de destino con el que realizar la compilación. Para obtener una lista de identificadores de tiempo de ejecución (RID) que puede usar, consulte el [catálogo de RID](../rid-catalog.md).

`--version-suffix [VERSION_SUFFIX]`

Define qué `*` debe reemplazarse por el campo de versión en el archivo del proyecto. El formato sigue las instrucciones de versión de NuGet.

`--no-incremental`

Marca la compilación como no segura para la compilación incremental. Esto desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

`--no-dependencies`

Omite las referencias de proyecto a proyecto y solo compila el proyecto raíz especificado para compilar.

`-v|--verbosity`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet build`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet build --configuration Release`

Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`
