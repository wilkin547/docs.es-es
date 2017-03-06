---
title: Comando dotnet-sln | Microsoft Docs
description: "El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución."
keywords: dotnet-run, CLI, comando de la CLI, .NET Core
author: spboyer
ms.author: mairaw
ms.date: 02/06/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: e5a72d3e-c14b-4b0a-a978-c5e54a0988c6
translationtype: Human Translation
ms.sourcegitcommit: 6c0474e2964043b6c090ecb4e68b46ff42ca670c
ms.openlocfilehash: c5ed2482222b02b8b50599b48a28afa5922e0135

---
# <a name="dotnet-sln"></a>dotnet-sln

[!INCLUDE[preview-warning](../../../includes/warning.md)]

## <a name="name"></a>Nombre

`dotnet-sln`: modifica un archivo de solución de .NET Core.

## <a name="synopsis"></a>Sinopsis

```
dotnet sln [<SLN_NAME>] add <project> <project>
dotnet sln [<SLN_NAME>] add **/**
dotnet sln [<SLN_NAME>] remove <project> <project>
dotnet sln [<SLN_NAME>] remove **/**
dotnet sln [<SLN_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.

## <a name="commands"></a>Comandos

`add <project>`

`add **/*`

Agrega un proyecto o varios proyectos al archivo de solución. El patrón Glob se admite en terminales basados en Unix/Linux.

`remove <project>`

`remove **/*`

Quita un proyecto o varios proyectos del archivo de solución. El patrón Glob se admite en terminales basados en Unix/Linux.

`list`

Lista todos los proyectos de un archivo de solución.

## <a name="arguments"></a>Argumentos

`SLN_NAME`

Archivo de solución que se va a utilizar. Si no se especifica, el comando buscará uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Agregue un proyecto a una solución:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Agregue un proyecto a la solución en el directorio actual:

`dotnet sln add todo-app.csproj`

Quite un proyecto de una solución:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Agregue varios proyectos a una solución mediante el patrón de uso de comodines:

`dotnet sln add **/**/*.fsproj`



<!--HONumber=Feb17_HO2-->


