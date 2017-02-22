---
title: Comando dotnet-new | Microsoft Docs
description: El comando dotnet-new crea nuevos proyectos de .NET Core en el directorio actual.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 263c3d05-3a47-46a6-8023-3ca16b488410
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: a49fe94ca8f678c614fb7f58767693c73e34c737

---

#<a name="dotnet-new"></a>dotnet-new

> [!WARNING]
> Este tema se aplica a .NET Core Tools Preview 2. Para más información sobre la versión de .NET Core Tools RC4, consulte el tema [dotnet-new (.NET Core Tools RC4)](../preview3/tools/dotnet-new.md).

## <a name="name"></a>Nombre
`dotnet-new`: crea un nuevo proyecto de .NET Core en el directorio actual.

## <a name="synopsis"></a>Sinopsis
`dotnet new [--help] [--type] [--lang]`

## <a name="description"></a>Descripción
El comando `dotnet new` proporciona una manera cómoda de inicializar un proyecto de .NET Core válido, junto con código fuente de ejemplo para probar el conjunto de herramientas de la interfaz de línea de comandos (CLI). 

Este comando se invoca en el contexto de un directorio. Cuando se invoca, el comando produce dos artefactos principales que se entregan en el directorio actual: 

1. Un archivo `Program.cs` (o `Program.fs`) que contiene un programa de ejemplo "Hello World".
2. Un archivo `project.json` válido.

Después de esto, el proyecto está listo para ser compilado o editarse adicionalmente. 

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.  

`-l|--lang <C#|F#>`

Lenguaje del proyecto. Tiene como valor predeterminado `C#`. Otros valores válidos son `csharp`, `fsharp`, `cs` y `fs`.

`-t|--type`

Tipo del proyecto. Valores válidos para C# son `console`, `web`, `lib` y `xunittest`, y para F # solo es válido `console`. 

## <a name="examples"></a>Ejemplos

Creación de un proyecto de aplicación de consola con C# en el directorio actual:

`dotnet new` o `dotnet new --lang c#` 
   
Creación de un proyecto de aplicación de consola con F# en el directorio actual:

`dotnet new --lang f#`
  
Creación de un nuevo proyecto de aplicación con C# de ASP.NET Core en el directorio actual:

`dotnet new -t web`


<!--HONumber=Feb17_HO2-->


