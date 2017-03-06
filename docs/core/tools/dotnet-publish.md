---
title: Comando dotnet-publish | Microsoft Docs
description: El comando dotnet-publish publica el proyecto de .NET Core en un directorio.
keywords: dotnet-publish, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 8a7e1c52-5c57-4bf5-abad-727450ebeefd
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 1cf1611ab83874ad44855521d21040d102206338

---

#<a name="dotnet-publish"></a>dotnet-publish

> [!WARNING]
> Este tema se aplica a .NET Core Tools Preview 2. Para la versión de .NET Core Tools RC4, consulte el tema [dotnet-publish (.NET Core Tools RC4)](../preview3/tools/dotnet-publish.md).

## <a name="name"></a>Nombre

`dotnet-publish`: empaqueta la aplicación y todas sus dependencias en una carpeta y la deja lista para publicarse.

## <a name="synopsis"></a>Sinopsis

`dotnet publish [project] 
    [--help] [--framework]  
    [--runtime] [--build-base-path] [--output]  
    [--version-suffix] [--configuration] [--native-subdirectory] [--no-build]`

## <a name="description"></a>Descripción

`dotnet publish` compila la aplicación, lee sus dependencias especificadas en el archivo [project.json](project-json.md) y publica el conjunto resultante de archivos en un directorio. 

Dependiendo del tipo de aplicación portátil, el directorio resultante contendrá lo siguiente:

1. *Aplicación portátil*: código de lenguaje intermedio (IL) de la aplicación y todas las dependencias administradas de la aplicación.
    * *Aplicación portátil con dependencias nativas*: igual que anteriormente con un subdirectorio para la plataforma admitida de cada dependencia nativa. 
2. *Aplicación autocontenida*: igual que anteriormente más el tiempo de ejecución completo para la plataforma de destino.

Para más información, consulte el tema [Implementación de aplicaciones .NET Core](../deploying/index.md).

## <a name="options"></a>Opciones

`[project]` 

El proyecto para publicar, cuyo valor predeterminado es el directorio actual si no se especifica `[project]`. Este valor puede ser una ruta de acceso al archivo [project.json](project-json.md) o al directorio del proyecto que contiene el archivo [project.json](project-json.md). Si no se encuentra ningún archivo [project.json](project-json.md), `dotnet publish` produce un error. 

`-h|--help`

Imprime una corta ayuda para el comando.  

`-f|--framework <FRAMEWORK>`

Publica la aplicación para un identificador de marco determinado (FID). Si no se especifica, el FID se lee de [project.json](project-json.md#frameworks). Si no se encuentra ningún marco válido, el comando produce un error. Si se encuentran varios marcos válidos, el comando publica para todos los marcos válidos. 

`-r|--runtime <RUNTIME_IDENTIFIER>`

Publica la aplicación para un determinado entorno de tiempo de ejecución. Para obtener una lista de identificadores de tiempo de ejecución (RID) que puede usar, consulte el [catálogo de RID](../rid-catalog.md).

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Directorio en el que se van a colocar las salidas temporales.

`-o|--output <OUTPUT_PATH>`

Especifique la ruta donde colocar el directorio. Si no se especifica, se toma como predeterminada *_./bin/[configuration]/[framework]/_* para aplicaciones portátiles o *_./bin/[configuration]/[framework]/[runtime]_* para implementaciones autocontenidas.

`--version-suffix [VERSION_SUFFIX]`

Define qué `*` debe reemplazarse por el campo de versión en el archivo project.json.

`-c|--configuration [Debug|Release]`

Configuración para usar al publicar. El valor predeterminado es `Debug`.

`[--native-subdirectory]` Mecanismo temporal para incluir subdirectorios de recursos nativos de paquetes de dependencia en la salida. 

`[--no-build]` No compila proyectos antes de publicarlos.

## <a name="examples"></a>Ejemplos

Publicación de una aplicación mediante el marco que se encuentra en `project.json`. Si `project.json` contiene el nodo [runtimes](project-json.md#runtimes), se publica para el RID de la plataforma actual.

`dotnet publish`

Publicación de la aplicación mediante el archivo [project.json](project-json.md) especificado:

`dotnet publish ~/projects/app1/project.json`
    
Publicación de la aplicación actual con el marco `netcoreapp1.0`:

`dotnet publish --framework netcoreapp1.0`
    
Publicación de la aplicación actual con el marco `netcoreapp1.0` y el entorno de tiempo de ejecución para `OS X 10.10` (este RID tiene que existir en el nodo `project.json` [runtimes](project-json.md#runtimes)):

`dotnet publish --framework netcoreapp1.0 --runtime osx.10.11-x64`

## <a name="see-also"></a>Vea también
* [Marcos](../../standard/frameworks.md)
* [Catálogo de identificadores de tiempo de ejecución (RID)](../rid-catalog.md)


<!--HONumber=Feb17_HO2-->


