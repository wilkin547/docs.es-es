---
title: Comando dotnet-clean | Microsoft Docs
description: El comando dotnet-clean limpia el directorio actual.
keywords: dotnet-clean, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 01/31/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: 12144def2095246bb6611522b3dbc2d7e441135a

---

#<a name="dotnet-clean"></a>dotnet-clean

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Nombre 
`dotnet-clean`: limpia la salida de un proyecto. 

## <a name="synopsis"></a>Sinopsis

`dotnet clean [--help] [--output]  [--framework]  
    [--configuration]  [--verbosity]
    [<project>]`

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

`-v|--verbosity [Quiet|Minimal|Normal|Diag]`

Define el nivel de detalle que se utilizará para la invocación del comando `dotnet clean`. Los niveles de detalle son los [niveles de detalle de MSBuild](https://msdn.microsoft.com/en-us/library/ms164311.aspx) estándar. 


## <a name="examples"></a>Ejemplos

Limpie una compilación predeterminada del proyecto:

`dotnet clean`

Limpie un proyecto creado con la configuración de lanzamiento:

`dotnet clean --configuration Release`



<!--HONumber=Feb17_HO2-->


