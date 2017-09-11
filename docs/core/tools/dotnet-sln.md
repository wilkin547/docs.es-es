---
title: 'Comando dotnet sln: CLI de .NET Core'
description: "El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 5071cb80be0fb14829a0fdffd0f5a2d2371b6ba8
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-sln"></a><span data-ttu-id="94c2b-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="94c2b-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="94c2b-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="94c2b-104">Name</span></span>

<span data-ttu-id="94c2b-105">`dotnet-sln`: modifica un archivo de solución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="94c2b-105">`dotnet-sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="94c2b-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="94c2b-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="94c2b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="94c2b-107">Description</span></span>

<span data-ttu-id="94c2b-108">El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="94c2b-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

## <a name="commands"></a><span data-ttu-id="94c2b-109">Comandos</span><span class="sxs-lookup"><span data-stu-id="94c2b-109">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="94c2b-110">Agrega un proyecto o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="94c2b-110">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="94c2b-111">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="94c2b-111">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="94c2b-112">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="94c2b-112">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="94c2b-113">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="94c2b-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="94c2b-114">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="94c2b-114">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="94c2b-115">Argumentos</span><span class="sxs-lookup"><span data-stu-id="94c2b-115">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="94c2b-116">Archivo de solución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="94c2b-116">Solution file to use.</span></span> <span data-ttu-id="94c2b-117">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="94c2b-117">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="94c2b-118">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="94c2b-118">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="94c2b-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="94c2b-119">Options</span></span>

`-h|--help`

<span data-ttu-id="94c2b-120">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="94c2b-120">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="94c2b-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="94c2b-121">Examples</span></span>

<span data-ttu-id="94c2b-122">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="94c2b-122">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="94c2b-123">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="94c2b-123">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="94c2b-124">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="94c2b-124">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="94c2b-125">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="94c2b-125">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="94c2b-126">Agregue varios proyectos de C# a una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="94c2b-126">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="94c2b-127">Quite varios proyectos de C# de una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="94c2b-127">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
