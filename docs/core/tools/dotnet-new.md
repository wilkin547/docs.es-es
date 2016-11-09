---
title: Comando dotnet-new | .NET Core
description: El comando dotnet-new crea nuevos proyectos de .NET Core en el directorio actual.
keywords: dotnet-new, CLI, comando de CLI, .NET Core
author: mairaw
manager: wpickett
ms.date: 10/12/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: 263c3d05-3a47-46a6-8023-3ca16b488410
translationtype: Human Translation
ms.sourcegitcommit: c6ee3f5663d0a3f62914e8de474cca4d15340c9d
ms.openlocfilehash: 29ccc12ff893d316c816d22da862f90bfc9334ff

---

#<a name="dotnetnew"></a>dotnet-new

## <a name="name"></a>Nombre
dotnet-new: crea un nuevo proyecto de .NET Core en el directorio actual.

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


<!--HONumber=Nov16_HO1-->


