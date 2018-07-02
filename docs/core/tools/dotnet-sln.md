---
title: 'Comando dotnet sln: CLI de .NET Core'
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 65ae402ef5519863886c8cf833598f5314b4bdad
ms.sourcegitcommit: 6bc4efca63e526ce6f2d257fa870f01f8c459ae4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/19/2018
ms.locfileid: "36207819"
---
# <a name="dotnet-sln"></a><span data-ttu-id="f223f-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="f223f-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="f223f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="f223f-104">Name</span></span>

<span data-ttu-id="f223f-105">`dotnet sln`: modifica un archivo de solución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="f223f-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="f223f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="f223f-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="f223f-107">Description</span><span class="sxs-lookup"><span data-stu-id="f223f-107">Description</span></span>

<span data-ttu-id="f223f-108">El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f223f-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="f223f-109">Para usar el comando `dotnet sln`, debe existir el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f223f-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="f223f-110">Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="f223f-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="f223f-111">Comandos</span><span class="sxs-lookup"><span data-stu-id="f223f-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="f223f-112">Agrega un proyecto o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f223f-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="f223f-113">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="f223f-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="f223f-114">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f223f-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="f223f-115">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="f223f-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="f223f-116">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="f223f-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="f223f-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="f223f-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="f223f-118">Archivo de solución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="f223f-118">Solution file to use.</span></span> <span data-ttu-id="f223f-119">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="f223f-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="f223f-120">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="f223f-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="f223f-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="f223f-121">Options</span></span>

`-h|--help`

<span data-ttu-id="f223f-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="f223f-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="f223f-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f223f-123">Examples</span></span>

<span data-ttu-id="f223f-124">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="f223f-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="f223f-125">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="f223f-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="f223f-126">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="f223f-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="f223f-127">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="f223f-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="f223f-128">Agregue varios proyectos de C# a una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="f223f-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="f223f-129">Quite varios proyectos de C# de una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="f223f-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`
