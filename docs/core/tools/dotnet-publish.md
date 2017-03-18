---
title: Comando dotnet-publish | Microsoft Docs
description: El comando dotnet-publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/07/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: f2ef275a-7c5e-430a-8c30-65f52af62771
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 78487673d8fa07286605fb806f30083747b17386
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-publish"></a>dotnet-publish

## <a name="name"></a>Name

`dotnet-publish`: empaqueta la aplicación y todas sus dependencias en una carpeta y la deja lista para publicarse.

## <a name="synopsis"></a>Sinopsis

```
dotnet publish [project] [-f|--framework] [-r|--runtime] [-o|--output] [-c|--configuration] [--version-suffix] [-v|--verbosity]
dotnet publish [-h|--help]
```

## <a name="description"></a>Descripción

`dotnet publish` compila la aplicación, lee sus dependencias especificadas en el archivo project.json y publica el conjunto resultante de archivos en un directorio. La salida contendrá lo siguiente:

1. Código de lenguaje intermedio (IL) en un ensamblado con una extensión `*.dll`.
2. Archivo *deps.json* que contiene todas las dependencias del proyecto. 
3. Archivo *Runtime.config.json* que especifica el entorno de tiempo de ejecución compartido que espera la aplicación, así como otras opciones de configuración para el tiempo de ejecución (por ejemplo, el tipo de recolección de elementos no utilizados).
4. Todas las dependencias de la aplicación. Estas se copian de la caché de NuGet y a la carpeta de salida. 

El resultado del comando `dotnet publish` está listo para implementarse en una máquina remota para su ejecución y es la única manera compatible oficialmente para preparar la aplicación que se va a implementar en otra máquina (por ejemplo, un servidor) para su ejecución. Dependiendo del tipo de implementación que especifique el proyecto, la máquina remota tendrá que tener el entorno de tiempo de ejecución compartido de .NET Core instalado. Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).

## <a name="arguments"></a>Argumentos

`project` 

El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica `project`. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-f|--framework <FRAMEWORK>`

Publica la aplicación para la plataforma de destino especificada. La plataforma de destino tiene que especificarse en el archivo del proyecto.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Esto se usa al crear una [implementación autocontenida](../deploying/index.md#self-contained-deployments-scd). Para obtener una lista de identificadores de tiempo de ejecución (RID) que puede usar, consulte el [catálogo de RID](../rid-catalog.md). El valor predeterminado es publicar una [aplicación dependiente del marco](../deploying/index.md#framework-dependent-deployments-fdd).

`-o|--output <OUTPUT_PATH>`

Especifique la ruta donde colocar el directorio. Si no se especifica, se toma como predeterminada *_./bin/[configuration]/[framework]/_* para aplicaciones portátiles o *_./bin/[configuration]/[framework]/[runtime]_* para implementaciones autocontenidas.

`-c|--configuration {Debug|Release}`

Configuración para usar al compilar el proyecto. El valor predeterminado es `Debug`.

`--version-suffix <VERSION_SUFFIX>`

Define qué `*` debe reemplazarse por el campo de versión en el archivo del proyecto.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Los valores permitidos son `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` y `diag[nostic]`.

## <a name="examples"></a>Ejemplos

Publicar el proyecto que se ha encontrado en el directorio actual:

`dotnet publish`

Publicar la aplicación con el archivo del proyecto especificado:

`dotnet publish ~/projects/app1/app1.csproj`
    
Publicar el proyecto que se ha encontrado en el directorio actual con el marco `netcoreapp1.1`:

`dotnet publish --framework netcoreapp1.1`
    
Publica la aplicación actual con el marco `netcoreapp1.1` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el archivo de proyecto):

`dotnet publish --framework netcoreapp1.1 --runtime osx.10.11-x64`

## <a name="see-also"></a>Vea también
* [Marcos](../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)
