---
title: 'Comando dotnet-publish: CLI de .NET Core | Microsoft Docs'
description: El comando dotnet-publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: dff752a9d31ec92b113dae9eed20cd72faf57c84
ms.openlocfilehash: 48bfe6c77ee6c5d905069f47da5512ac63a24b2a
ms.lasthandoff: 03/22/2017

---

# <a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish`: empaqueta la aplicación y sus dependencias en una carpeta para su implementación en un sistema de hospedaje.

## <a name="synopsis"></a>Sinopsis

`dotnet publish [<PROJECT>] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

`dotnet publish`: compila la aplicación, lee sus dependencias especificadas en el archivo de proyecto y publica el conjunto resultante de archivos en un directorio. La salida contendrá lo siguiente:

* Código de lenguaje intermedio (IL) en un ensamblado con una extensión `*.dll`.
* Archivo *\*.deps.json* que contiene todas las dependencias del proyecto.
* Archivo *\*Runtime.config.json* que especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).
* Todas las dependencias de la aplicación. Estas se copian de la caché de NuGet a la carpeta de salida.

La salida del comando `dotnet publish` está preparada para la implementación de un sistema de hospedaje (por ejemplo, un servidor, un equipo PC o Mac o un equipo portátil) para la ejecución y es la única manera admitida oficialmente de preparar la aplicación para la implementación. Dependiendo del tipo de implementación que especifique el proyecto, el sistema de hospedaje puede o no tener instalado el entorno de tiempo de ejecución compartido de .NET Core. Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md). Para la estructura de directorios de una aplicación publicada, consulte [Directory structure](https://docs.microsoft.com/en-us/aspnet/core/hosting/directory-structure) (Estructura de directorios).

## <a name="arguments"></a>Argumentos

`PROJECT` 

El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-f|--framework <FRAMEWORK>`

Publica la aplicación para el [marco de trabajo de destino especificado](../../standard/frameworks.md). Debe especificar el marco de trabajo de destino en el archivo de proyecto.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida (SCD)](../deploying/index.md#self-contained-deployments-scd). Para obtener una lista de identificadores de tiempo de ejecución (RID), consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco de trabajo (FDD)](../deploying/index.md#framework-dependent-deployments-fdd).

`-o|--output <OUTPUT_DIRECTORY>`

Especifica la ruta de acceso del directorio de salida. Si no se especifica, el valor predeterminado es *./bin/[configuration]/[framework]/* para una implementación dependiente del marco de trabajo o *./bin/[configuration]/[framework]/[runtime]* para una implementación independiente.

`-c|--configuration <CONFIGURATION>`

Configuración para usar al compilar el proyecto. El valor predeterminado es `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Define el sufijo de versión para reemplazar el asterisco (`*`) en el campo de versión del archivo de proyecto.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Publica el proyecto en el directorio actual:

`dotnet publish`

Publicar la aplicación con el archivo del proyecto especificado:

`dotnet publish ~/projects/app1/app1.csproj`
    
Publica el proyecto en el directorio actual mediante el marco de trabajo `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Publica la aplicación actual mediante el marco de trabajo `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Vea también

* [Marcos de trabajo de destino](../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)
