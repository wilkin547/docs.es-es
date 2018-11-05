---
title: 'Comando dotnet sln: CLI de .NET Core'
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
author: mairaw
ms.author: mairaw
ms.date: 06/13/2018
ms.openlocfilehash: 2651e8e14ad43f41354b8165179f95f65e732f4c
ms.sourcegitcommit: 15d99019aea4a5c3c91ddc9ba23692284a7f61f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/12/2018
ms.locfileid: "49121226"
---
# <a name="dotnet-sln"></a><span data-ttu-id="ab6bd-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="ab6bd-103">dotnet sln</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ab6bd-104">nombre</span><span class="sxs-lookup"><span data-stu-id="ab6bd-104">Name</span></span>

<span data-ttu-id="ab6bd-105">`dotnet sln`: modifica un archivo de solución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-105">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ab6bd-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ab6bd-106">Synopsis</span></span>

```
dotnet sln [<SOLUTION_NAME>] add <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] add <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] remove <PROJECT> <PROJECT> ...
dotnet sln [<SOLUTION_NAME>] remove <GLOBBING_PATTERN>
dotnet sln [<SOLUTION_NAME>] list
dotnet sln [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ab6bd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ab6bd-107">Description</span></span>

<span data-ttu-id="ab6bd-108">El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-108">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="ab6bd-109">Para usar el comando `dotnet sln`, debe existir el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-109">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="ab6bd-110">Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-110">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```
dotnet new sln
```

## <a name="commands"></a><span data-ttu-id="ab6bd-111">Comandos</span><span class="sxs-lookup"><span data-stu-id="ab6bd-111">Commands</span></span>

`add <PROJECT> ...`

`add <GLOBBING_PATTERN>`

<span data-ttu-id="ab6bd-112">Agrega un proyecto o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-112">Adds a project or multiple projects to the solution file.</span></span> <span data-ttu-id="ab6bd-113">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-113">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`remove <PROJECT> ...`

`remove <GLOBBING_PATTERN>`

<span data-ttu-id="ab6bd-114">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-114">Removes a project or multiple projects from the solution file.</span></span> <span data-ttu-id="ab6bd-115">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-115">[Globbing patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

`list`

<span data-ttu-id="ab6bd-116">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-116">Lists all projects in a solution file.</span></span>

## <a name="arguments"></a><span data-ttu-id="ab6bd-117">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ab6bd-117">Arguments</span></span>

`SOLUTION_NAME`

<span data-ttu-id="ab6bd-118">Archivo de solución que se va a utilizar.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-118">Solution file to use.</span></span> <span data-ttu-id="ab6bd-119">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-119">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="ab6bd-120">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-120">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="ab6bd-121">Opciones</span><span class="sxs-lookup"><span data-stu-id="ab6bd-121">Options</span></span>

`-h|--help`

<span data-ttu-id="ab6bd-122">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-122">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="ab6bd-123">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ab6bd-123">Examples</span></span>

<span data-ttu-id="ab6bd-124">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-124">Add a C# project to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj`

<span data-ttu-id="ab6bd-125">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-125">Remove a C# project from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj`

<span data-ttu-id="ab6bd-126">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-126">Add multiple C# projects to a solution:</span></span>

`dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="ab6bd-127">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-127">Remove multiple C# projects from a solution:</span></span>

`dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj`

<span data-ttu-id="ab6bd-128">Agregue varios proyectos de C# a una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-128">Add multiple C# projects to a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln add **/*.csproj`

<span data-ttu-id="ab6bd-129">Quite varios proyectos de C# de una solución mediante un patrón global:</span><span class="sxs-lookup"><span data-stu-id="ab6bd-129">Remove multiple C# projects from a solution using a globbing pattern:</span></span>

`dotnet sln todo.sln remove **/*.csproj`

> [!NOTE]
> <span data-ttu-id="ab6bd-130">El uso de comodines no es una característica de la CLI, sino una característica del shell de comandos.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-130">Globbing is not a CLI feature but rather a feature of the command shell.</span></span> <span data-ttu-id="ab6bd-131">Para expandir correctamente los archivos, debe usar un shell que admita el uso de comodines.</span><span class="sxs-lookup"><span data-stu-id="ab6bd-131">To successfully expand the files, you must use a shell that supports globbing.</span></span> <span data-ttu-id="ab6bd-132">Para más información sobre el uso de comodines, vea [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span><span class="sxs-lookup"><span data-stu-id="ab6bd-132">For more information about globbing, see [Wikipedia](https://en.wikipedia.org/wiki/Glob_(programming)).</span></span>
