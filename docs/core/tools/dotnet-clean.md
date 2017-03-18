---
title: Comando dotnet-clean | Microsoft Docs
description: El comando dotnet-clean limpia el directorio actual.
keywords: dotnet-clean, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 195664ae6409be02ca132900d9c513a7b412acd4
ms.openlocfilehash: 3c00f4616932318b5dc5d77cbdf6c645696a4226
ms.lasthandoff: 03/07/2017

---
#<a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Name

`dotnet-clean`: limpia la salida de un proyecto. 

## <a name="synopsis"></a>Sinopsis

```
dotnet clean [project] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity]
dotnet clean [--help] 
```

## <a name="description"></a>Descripción

El comando `dotnet clean` limpiará la salida de la compilación anterior. Se implementa como un destino de MSBuild, por lo que se evaluará el proyecto. Solo se limpian las salidas que se crearon durante la compilación. Se limpian las carpetas de salida intermedia (`obj`) y final (`bin`). 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-o|--output <OUTPUT_DIRECTORY>`

Directorio donde se colocan los archivos binarios compilados. También debe definir `--framework` cuando se especifica esta opción. Si no especificó esta propiedad durante el tiempo de compilación, no tiene que especificarla para limpiar.

`-f|--framework <FRAMEWORK>`

El marco de trabajo que se especificó en el tiempo de compilación. Si no especificó esta propiedad durante el tiempo de compilación, no tiene que especificarla para limpiar. El marco debe definirse en el [archivo de proyecto](csproj.md).

`-c|--configuration [Debug|Release]`

Define una configuración en la que se va a ejecutar la compilación.  Si se omite, se adopta el valor predeterminado de `Debug`. Si no especificó esta propiedad durante el tiempo de compilación, no tiene que especificarla para limpiar.

`-v|--verbosity <Quiet|Minimal|Normal|Diag>`

Define el nivel de detalle que se utilizará para la invocación del comando `dotnet clean`. Los niveles de detalle son los [niveles de detalle de MSBuild](https://docs.microsoft.com/visualstudio/msbuild/msbuild-command-line-reference) estándar. 

## <a name="examples"></a>Ejemplos

Limpie una compilación predeterminada del proyecto:

`dotnet clean`

Limpie un proyecto creado con la configuración de lanzamiento:

`dotnet clean --configuration Release`

