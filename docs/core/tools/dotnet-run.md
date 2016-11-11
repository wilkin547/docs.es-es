---
title: Comando dotnet-run | SDK de .NET Core
description: "El comando dotnet-run proporciona una opción conveniente para ejecutar la aplicación desde el código fuente."
keywords: dotnet-run, CLI, comando de la CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/07/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 495ff50b-cb30-4d30-8f20-beb3d5e7c31f
translationtype: Human Translation
ms.sourcegitcommit: c6ee3f5663d0a3f62914e8de474cca4d15340c9d
ms.openlocfilehash: 18731d9fcc190371d908779a69a81114e0685aba

---

#<a name="dotnetrun"></a>dotnet-run

## <a name="name"></a>Nombre 

dotnet-run: ejecuta el código fuente disponible sin comandos explícitos e compilación o lanzamiento

## <a name="synopsis"></a>Sinopsis

`dotnet run [--help] [--framework] [--configuration]
    [--project] [[--] [application arguments]]`

## <a name="description"></a>Descripción
El comando `dotnet run` proporciona una opción conveniente para ejecutar la aplicación desde el código fuente con un comando. Compila el código fuente, genera un programa de salida y luego ejecuta ese programa. Este comando es útil para el desarrollo iterativo rápido y también puede usarse para ejecutar un programa con origen distribuido (por ejemplo, un sitio web).

Este comando se basa en [dotnet build](dotnet-build.md) para compilar entradas de origen en un ensamblado. NET, antes de iniciar el programa. Los requisitos de este comando y el control de entradas de origen se heredan todos del comando de compilación. En la documentación del comando de compilación se proporciona más información sobre de esos requisitos.

Los archivos de salida se escriben en la carpeta *bin* secundaria, que se crea si no existe. Los archivos se sobrescribirán según sea necesario. Los archivos temporales se escriben en la carpeta *obj* secundaria.  

En el caso de un proyecto con varios marcos especificados, `dotnet run` selecciona primero los marcos de .NET Core. Si no existen, se genera un error de salida. Para especificar otros marcos, use el argumento `--framework`.

El comando `dotnet run` debe usarse en el contexto de proyectos, no de ensamblados compilados. Si, por el contrario, lo que intenta es ejecutar una DLL de aplicación portátil, debe usar [dotnet](dotnet.md) sin ningún comando, como en el ejemplo siguiente:
 
`dotnet myapp.dll`

Para más información sobre el controlador `dotnet`, consulte el tema [Herramientas de la interfaz de línea de comandos (CLI) de .NET Core](index.md).

## <a name="options"></a>Opciones

`--`

Delimita los argumentos a `dotnet run` a partir de argumentos de la aplicación que se va a ejecutar. Todos los argumentos después de este se pasarán a la aplicación que se ejecuta. 

`-h|--help`

Imprime una corta ayuda para el comando.

`-f`, `--framework <FRAMEWORK_IDENTIFIER>`

Ejecuta la aplicación por un identificador de marco determinado (FID). 

`-c`, `--configuration <Debug|Release>`

Configuración para usar al publicar. El valor predeterminado es `Debug`.

`-p`, `--project [PATH]`

Especifica el proyecto que se va a ejecutar. Puede ser una ruta de acceso a un archivo [project.json](project-json.md) o a un directorio que contiene un archivo [project.json](project-json.md). Si no se especifica, se toma como predeterminado el directorio actual. 

## <a name="examples"></a>Ejemplos

Ejecución del proyecto en el directorio actual:`dotnet run` 

Ejecución del proyecto especificado:

`dotnet run --project /projects/proj1/project.json`

Ejecución del proyecto en el directorio actual (el argumento `--help` en este ejemplo se pasa a la aplicación que se ejecuta, dado que se usó el argumento `--`):

`dotnet run --configuration Release -- --help`


<!--HONumber=Nov16_HO1-->


