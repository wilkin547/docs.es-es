---
title: 'Comando dotnet-build: CLI de .NET Core | Microsoft Docs'
description: El comando dotnet-build compila un proyecto y todas sus dependencias.
keywords: dotnet-build, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 5e1a2bc4-a919-4a86-8f33-a9b218b1fcb3
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: e5deac8a7b8faac97ccf8b801f274a2c03268d64
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-build"></a>dotnet-build

## <a name="name"></a>Name

`dotnet-build`: compila un proyecto y todas sus dependencias.

## <a name="synopsis"></a>Sinopsis

`dotnet build [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-r|--runtime] [--version-suffix] [--no-incremental] [--no-dependencies] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet build` crea el proyecto y sus dependencias en un conjunto de archivos binarios. Los archivos binarios incluyen el código del proyecto en archivos de lenguaje intermedio (IL) con una extensión *.dll* y los archivos de símbolos usados para la depuración con una extensión *.pdb*. Se genera un archivo JSON de dependencias (*\*. deps.json*) que incluye las dependencias de la aplicación. Se genera un archivo *\*.runtimeconfig.json*, que especifica el tiempo de ejecución compartido y su versión de la aplicación.

Si el proyecto tiene dependencias de terceros, como bibliotecas de NuGet, estas se resuelven desde la caché de NuGet y no están disponibles en la salida compilada del proyecto. Teniendo eso en cuenta, el producto de `dotnet build` no está listo para transferirse a otra máquina para ejecutarse. Esto contrasta con el comportamiento de .NET Framework en el que al compilar un proyecto ejecutable (una aplicación) se genera ese ejecutable en cualquier máquina donde esté instalado .NET. Para tener una experiencia similar con .NET Core, use el comando [dotnet publish](dotnet-publish.md). Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md). 

La compilación requiere el archivo *project.assets.json*, que muestra las dependencias de la aplicación. El archivo se crea al ejecutar [`dotnet restore`](dotnet-restore.md) antes de compilar el proyecto. Sin el archivo de recursos, las herramientas no pueden resolver los ensamblados de referencia, lo que dará lugar a errores.

`dotnet build` usa MSBuild para compilar el proyecto; por lo tanto, admite las compilaciones en paralelo e incrementales. Para más información, consulte [Compilaciones incrementales](https://docs.microsoft.com/visualstudio/msbuild/incremental-builds). 

Además de sus opciones, el comando `dotnet build` acepta opciones de MSBuild, como `/p` para establecer propiedades o `/l` para definir un registrador. Aprenda más sobre de estas opciones en la [referencia de línea de comandos de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference). 

Si el proyecto es ejecutable o no viene determinado por la propiedad `<OutputType>` en el archivo del proyecto. En el siguiente ejemplo se muestra un proyecto que generará un código ejecutable:

```xml
<PropertyGroup>
  <OutputType>Exe</OutputType>
</PropertyGroup>
```

Para generar una biblioteca, omita la propiedad `<OutputType>`. La principal diferencia en la salida compilada es que la DLL de IL para una biblioteca no contiene puntos de entrada y no se puede ejecutar. 

## <a name="arguments"></a>Argumentos

`PROJECT`

El archivo del proyecto que se va a compilar. Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción.

`-f|--framework <FRAMEWORK>`

Compila para un [marco de trabajo](../../standard/frameworks.md) específico. El marco se debe definir en el [archivo de proyecto](csproj.md).

`-c|--configuration <CONFIGURATION>`

Define la configuración de compilación. Si se omite, la configuración de compilación usa de forma predeterminada `Debug`. Use `Release` para compilar una configuración de versión.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Especifica el tiempo de ejecución de destino. Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md).

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de la versión de un asterisco (`*`) en el campo de versión del archivo del proyecto. El formato sigue las instrucciones de versión de NuGet.

`--no-incremental`

Marca la compilación como no segura para la compilación incremental. Esto desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

`--no-dependencies`

Omite las referencias de proyecto a proyecto (P2P) y solo compila el proyecto raíz especificado para compilar.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet build`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet build --configuration Release`

Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`

