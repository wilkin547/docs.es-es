---
title: Comando dotnet sln
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
ms.date: 06/13/2018
ms.openlocfilehash: 3f18d6a2851d955d07cecc0cbc4c161cf0ec3e08
ms.sourcegitcommit: 2d792961ed48f235cf413d6031576373c3050918
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/31/2019
ms.locfileid: "70202790"
---
# <a name="dotnet-sln"></a>dotnet sln

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>nombre

`dotnet sln`: modifica un archivo de solución de .NET Core.

## <a name="synopsis"></a>Sinopsis

```console
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a>DESCRIPCIÓN

El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.

Para usar el comando `dotnet sln`, debe existir el archivo de solución. Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:

```console
dotnet new sln
```

## <a name="commands"></a>Comandos

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

Agrega un proyecto o varios proyectos al archivo de solución. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

Quita un proyecto o varios proyectos del archivo de solución. Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.

`list`

Enumera todos los proyectos en un archivo de solución.

## <a name="arguments"></a>Argumentos

`SOLUTION_NAME`

Archivo de solución que se va a utilizar. Si no se especifica, el comando busca uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

## <a name="options"></a>Opciones

`-h|--help`

Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

Agregue un proyecto de C# a una solución:

`dotnet sln todo.sln add todo-app/todo-app.csproj`

Quite un proyecto de C# de una solución:

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

Agregue varios proyectos de C# a una solución:

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

Quite varios proyectos de C# de una solución:

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

Agregue varios proyectos de C# a una solución mediante un patrón global:

`dotnet sln todo.sln add **/*.csproj`

Quite varios proyectos de C# de una solución mediante un patrón global:

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> El uso de comodines no es una característica de la CLI, sino una característica del shell de comandos. Para expandir correctamente los archivos, debe usar un shell que admita el uso de comodines. Para más información sobre el uso de comodines, vea [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).
