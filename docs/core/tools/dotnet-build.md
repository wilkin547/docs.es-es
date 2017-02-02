---
title: Comando dotnet-build | Microsoft Docs
description: El comando dotnet-build compila un proyecto y todas sus dependencias.
keywords: dotnet-build, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/13/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 70285a83-4103-4617-be8b-d0e1e9a4a91d
translationtype: Human Translation
ms.sourcegitcommit: 2ad428dcda9ef213a8487c35a48b33929259abba
ms.openlocfilehash: 3cb552590bf45ec73d84cc902a505b3048301b9f

---

#<a name="dotnet-build"></a>dotnet-build

> [!WARNING]
> Este tema se aplica a .NET Core Tools Preview 2. Para la versión .NET Core Tools Preview 4 de Visual Studio 2017 RC, consulte el tema [dotnet-build (Tooling Preview 4)](../preview3/tools/dotnet-build.md).

## <a name="name"></a>Nombre 
`dotnet-build`: compila un proyecto y todas sus dependencias. 

## <a name="synopsis"></a>Sinopsis

`dotnet build [--help] [--output]  
    [--build-base-path] [--framework]  
    [--configuration]  [--runtime] [--version-suffix]
    [--build-profile]  [--no-incremental] [--no-dependencies]
    [<project>]`

## <a name="description"></a>Descripción

El comando `dotnet build` compila varios archivos de origen de un proyecto de origen y sus dependencias en un archivo binario. De forma predeterminada, el archivo binario resultante está en lenguaje intermedio (IL) y tiene una extensión DLL. 
`dotnet build`También quita un archivo `\*.deps` que describe lo que necesita el host para ejecutar la aplicación.  

La compilación requiere la existencia de un archivo de bloqueo, lo que significa que tiene que ejecutar [`dotnet restore`](dotnet-restore.md) antes de compilar el código.

Antes de comenzar cualquier compilación, el verbo `build` analiza el proyecto y sus dependencias para realizar las comprobaciones de seguridad incrementales.
Si todas las comprobaciones son correctas, la compilación continúa con la compilación incremental del proyecto y sus dependencias; de lo contrario, retrocede a la compilación no incremental. Mediante una marca de perfil, los usuarios pueden elegir recibir información adicional sobre cómo pueden mejorar los tiempos de compilación.

Todos los proyectos del gráfico de dependencias que necesitan compilación deben pasar las comprobaciones de seguridad siguientes para que el proceso de compilación sea incremental:
- no usar scripts con anterioridad o posterioridad a la compilación
- no cargar herramientas de compilación desde PATH (por ejemplo, resgen, compiladores)
- usar solo compiladores conocidos (csc, vbc, fsc)

Para compilar una aplicación ejecutable en lugar de una biblioteca, necesita una sección de [configuración especial](project-json.md#emitentrypoint) en el archivo project.json:

```json
{ 
    "buildOptions": {
      "emitEntryPoint": true
    }
}
```

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción.

`-b|--build-base-path <OUTPUT_DIRECTORY>`

Directorio en el que se van a colocar las salidas temporales.

`-f|--framework <FRAMEWORK>`

Compila para un marco específico. El marco debe definirse en el archivo [project.json](project-json.md#frameworks).

`-c|--configuration [Debug|Release]`

Define una configuración con la que se va a realizar la compilación.  Si se omite, se adopta el valor predeterminado de `Debug`.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Tiempo de ejecución de destino con el que realizar la compilación. Para obtener una lista de identificadores de tiempo de ejecución (RID) que puede usar, consulte el [catálogo de RID](../rid-catalog.md). 

`--version-suffix <VERSION_SUFFIX>`

Define con lo que se debe reemplazar `*` en el campo de versión en el archivo [project.json](project-json.md#version). El formato sigue las instrucciones de versión de NuGet. 

`--build-profile`

Imprime las comprobaciones de seguridad incrementales que los usuarios necesitan para que la compilación incremental se active automáticamente.

`--no-incremental`

Marca la compilación como no segura para la compilación incremental. Esto desactiva la compilación incremental y fuerza una recompilación limpia del gráfico de dependencias del proyecto.

`--no-dependencies`

Omite las referencias de proyecto a proyecto y solo compila el proyecto raíz especificado para compilar.

## <a name="examples"></a>Ejemplos

Creación de un proyecto y sus dependencias:

`dotnet build`

Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:

`dotnet build --configuration Release`

Compilación de un proyecto y sus dependencias para un tiempo de ejecución específico (en este ejemplo, Ubuntu 16.04):

`dotnet build --runtime ubuntu.16.04-x64`


<!--HONumber=Jan17_HO3-->


