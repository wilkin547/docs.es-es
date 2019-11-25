---
title: Comando dotnet sln
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
ms.date: 10/29/2019
ms.openlocfilehash: 18702c7638798117bd04d5c6a829d64cc6bf18a8
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/31/2019
ms.locfileid: "73191826"
---
# <a name="dotnet-sln"></a><span data-ttu-id="68c43-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="68c43-103">dotnet sln</span></span>

<span data-ttu-id="68c43-104">**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="68c43-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="68c43-105">Name</span><span class="sxs-lookup"><span data-stu-id="68c43-105">Name</span></span>

<span data-ttu-id="68c43-106">`dotnet sln`: modifica un archivo de solución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="68c43-106">`dotnet sln` - Modifies a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="68c43-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="68c43-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="68c43-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="68c43-108">Description</span></span>

<span data-ttu-id="68c43-109">El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-109">The `dotnet sln` command provides a convenient way to add, remove, and list projects in a solution file.</span></span>

<span data-ttu-id="68c43-110">Para usar el comando `dotnet sln`, debe existir el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="68c43-111">Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="68c43-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, like in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="68c43-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68c43-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="68c43-113">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c43-113">The solution file to use.</span></span> <span data-ttu-id="68c43-114">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c43-114">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="68c43-115">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="68c43-115">If there are multiple solution files in the directory, one must be specified.</span></span>

## <a name="options"></a><span data-ttu-id="68c43-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="68c43-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="68c43-117">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="68c43-117">Prints out a short help for the command.</span></span>

## <a name="commands"></a><span data-ttu-id="68c43-118">Comandos</span><span class="sxs-lookup"><span data-stu-id="68c43-118">Commands</span></span>

### `add`

<span data-ttu-id="68c43-119">Agrega un proyecto o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-119">Adds a project or multiple projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="68c43-120">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="68c43-120">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="68c43-121">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68c43-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="68c43-122">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c43-122">The solution file to use.</span></span> <span data-ttu-id="68c43-123">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c43-123">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="68c43-124">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="68c43-124">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="68c43-125">La ruta de acceso al proyecto que se va a agregar a la solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-125">The path to the project to add to the solution.</span></span> <span data-ttu-id="68c43-126">Para agregar varios proyectos, agregue uno detrás de otro separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="68c43-126">Add multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="68c43-127">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="68c43-127">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="68c43-128">Opciones</span><span class="sxs-lookup"><span data-stu-id="68c43-128">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="68c43-129">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="68c43-129">Prints out a short help for the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="68c43-130">Coloca el proyecto en la raíz de la solución, en lugar de crear una carpeta de la solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-130">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="68c43-131">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c43-131">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="68c43-132">La ruta de acceso de la carpeta de la solución de destino a la que se van a agregar los proyectos.</span><span class="sxs-lookup"><span data-stu-id="68c43-132">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="68c43-133">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="68c43-133">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="68c43-134">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-134">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="68c43-135">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="68c43-135">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="68c43-136">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68c43-136">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="68c43-137">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c43-137">The solution file to use.</span></span> <span data-ttu-id="68c43-138">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c43-138">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="68c43-139">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="68c43-139">If there are multiple solution files in the directory, one must be specified.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="68c43-140">La ruta de acceso al proyecto que se va a quitar de la solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-140">The path to the project to remove from the solution.</span></span> <span data-ttu-id="68c43-141">Para quitar varios proyectos, agregue uno detrás de otro separados por espacios.</span><span class="sxs-lookup"><span data-stu-id="68c43-141">Remove multiple projects by adding one after the other separated by spaces.</span></span> <span data-ttu-id="68c43-142">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="68c43-142">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="68c43-143">Opciones</span><span class="sxs-lookup"><span data-stu-id="68c43-143">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="68c43-144">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="68c43-144">Prints out a short help for the command.</span></span>

### `list`

<span data-ttu-id="68c43-145">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="68c43-145">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="68c43-146">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="68c43-146">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```
  
#### <a name="arguments"></a><span data-ttu-id="68c43-147">Argumentos</span><span class="sxs-lookup"><span data-stu-id="68c43-147">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="68c43-148">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="68c43-148">The solution file to use.</span></span> <span data-ttu-id="68c43-149">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="68c43-149">If not specified, the command searches the current directory for one.</span></span> <span data-ttu-id="68c43-150">Si hay varios archivos de solución en el directorio, se debe especificar uno.</span><span class="sxs-lookup"><span data-stu-id="68c43-150">If there are multiple solution files in the directory, one must be specified.</span></span>

#### <a name="options"></a><span data-ttu-id="68c43-151">Opciones</span><span class="sxs-lookup"><span data-stu-id="68c43-151">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="68c43-152">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="68c43-152">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="68c43-153">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="68c43-153">Examples</span></span>

<span data-ttu-id="68c43-154">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="68c43-154">Add a C# project to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj
```

<span data-ttu-id="68c43-155">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="68c43-155">Remove a C# project from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj
```

<span data-ttu-id="68c43-156">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="68c43-156">Add multiple C# projects to a solution:</span></span>

```dotnetcli
dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="68c43-157">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="68c43-157">Remove multiple C# projects from a solution:</span></span>

```dotnetcli
dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
```

<span data-ttu-id="68c43-158">Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="68c43-158">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln add **/*.csproj
```

<span data-ttu-id="68c43-159">Quite varios proyectos de C# de una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="68c43-159">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

```dotnetcli
dotnet sln todo.sln remove **/*.csproj
```
