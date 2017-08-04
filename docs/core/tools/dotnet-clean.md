---
title: 'Comando dotnet-clean: CLI de .NET Core'
description: El comando dotnet-clean limpia el directorio actual.
keywords: dotnet-clean, CLI, comando de la CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 03/15/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: eff65fa1-bab4-4421-8260-d0a284b690b2
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 10222781d5bff596d1b7883bc73097758e878235
ms.contentlocale: es-es
ms.lasthandoff: 07/28/2017

---

# <a name="dotnet-clean"></a>dotnet-clean

## <a name="name"></a>Name

`dotnet-clean`: limpia la salida de un proyecto. 

## <a name="synopsis"></a>Sinopsis

`dotnet clean [<PROJECT>] [-o|--output] [-f|--framework] [-c|--configuration] [-v|--verbosity] [-h|--help]`

## <a name="description"></a>Descripción

El comando `dotnet clean` limpia la salida de la compilación anterior. Se implementa como un [destino MSBuild](/visualstudio/msbuild/msbuild-targets), por lo que el proyecto se evalúa cuando se ejecuta el comando. Solo se limpian las salidas que se crearon durante la compilación. Se limpian las carpetas intermedias (*obj*) y de la salida final (*bin*).

## <a name="arguments"></a>Argumentos

`PROJECT`

El proyecto de MSBuild para limpiar. Si no se especifica un archivo de proyecto, MSBuild busca en el directorio de trabajo actual un archivo que tenga una extensión de archivo que termine en *proj* y usa ese archivo.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

`-o|--output <OUTPUT_DIRECTORY>`

Directorio en el que se colocan las salidas de compilación. Especifique el modificador `-f|--framework <FRAMEWORK>` con el modificador del directorio de salida si especificó el marco cuando se compiló el proyecto.

`-f|--framework <FRAMEWORK>`

El [marco](../../standard/frameworks.md) que se especificó en tiempo de compilación. El marco se debe definir en el [archivo de proyecto](csproj.md). Si especificó el marco en tiempo de compilación, debe especificar el marco al realizar la limpieza.

`-c|--configuration <CONFIGURATION>`

Define la configuración. Si se omite, se adopta el valor predeterminado de `Debug`. Esta propiedad solo es necesaria al realizar la limpieza si la especificó durante el tiempo de compilación.

`-v|--verbosity <LEVEL>`

Establece el nivel de detalle del comando. Niveles permitidos son q[uiet], m[inimal], n[ormal], d[etailed] y diag[nostic].

## <a name="examples"></a>Ejemplos

Limpie una compilación predeterminada del proyecto:

`dotnet clean`

Limpie un proyecto creado con la configuración de lanzamiento:

`dotnet clean --configuration Release`

