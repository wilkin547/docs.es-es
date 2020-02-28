---
title: Comando dotnet sln
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
ms.date: 02/14/2020
ms.openlocfilehash: b2455c04a46b2a10b8142d8ddc2d8129f2154b27
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543487"
---
# <a name="dotnet-sln"></a><span data-ttu-id="870a7-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="870a7-103">dotnet sln</span></span>

<span data-ttu-id="870a7-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="870a7-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="870a7-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="870a7-105">Name</span></span>

<span data-ttu-id="870a7-106">`dotnet sln`: enumera o modifica los proyectos en un archivo de solución de .NET Core.</span><span class="sxs-lookup"><span data-stu-id="870a7-106">`dotnet sln` - Lists or modifies the projects in a .NET Core solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="870a7-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="870a7-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a><span data-ttu-id="870a7-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="870a7-108">Description</span></span>

<span data-ttu-id="870a7-109">El comando `dotnet sln` proporciona una opción conveniente para enumerar y modificar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="870a7-110">Para usar el comando `dotnet sln`, debe existir el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="870a7-111">Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="870a7-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="870a7-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="870a7-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="870a7-113">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="870a7-113">The solution file to use.</span></span> <span data-ttu-id="870a7-114">Si se omite este argumento, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="870a7-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="870a7-115">Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="870a7-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="870a7-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="870a7-117">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="870a7-118">Comandos</span><span class="sxs-lookup"><span data-stu-id="870a7-118">Commands</span></span>

### `list`

<span data-ttu-id="870a7-119">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="870a7-120">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="870a7-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="870a7-121">Argumentos</span><span class="sxs-lookup"><span data-stu-id="870a7-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="870a7-122">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="870a7-122">The solution file to use.</span></span> <span data-ttu-id="870a7-123">Si se omite este argumento, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="870a7-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="870a7-124">Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="870a7-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="870a7-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="870a7-126">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="870a7-127">Agrega uno o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="870a7-128">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="870a7-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="870a7-129">Argumentos</span><span class="sxs-lookup"><span data-stu-id="870a7-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="870a7-130">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="870a7-130">The solution file to use.</span></span> <span data-ttu-id="870a7-131">Si no se especifica, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="870a7-132">La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="870a7-133">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="870a7-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="870a7-134">Opciones</span><span class="sxs-lookup"><span data-stu-id="870a7-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="870a7-135">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="870a7-136">Coloca el proyecto en la raíz de la solución, en lugar de crear una carpeta de la solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="870a7-137">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="870a7-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder`**

  <span data-ttu-id="870a7-138">La ruta de acceso de la carpeta de la solución de destino a la que se van a agregar los proyectos.</span><span class="sxs-lookup"><span data-stu-id="870a7-138">The destination solution folder path to add the projects to.</span></span> <span data-ttu-id="870a7-139">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="870a7-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="870a7-140">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="870a7-141">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="870a7-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="870a7-142">Argumentos</span><span class="sxs-lookup"><span data-stu-id="870a7-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="870a7-143">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="870a7-143">The solution file to use.</span></span> <span data-ttu-id="870a7-144">Si se deja sin especificar, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="870a7-145">La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución.</span><span class="sxs-lookup"><span data-stu-id="870a7-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="870a7-146">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="870a7-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="870a7-147">Opciones</span><span class="sxs-lookup"><span data-stu-id="870a7-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="870a7-148">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="870a7-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="870a7-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="870a7-149">Examples</span></span>

- <span data-ttu-id="870a7-150">Enumere los proyectos en una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="870a7-151">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="870a7-152">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="870a7-153">Agregue varios proyectos de C# a la raíz de una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="870a7-154">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="870a7-155">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="870a7-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="870a7-156">Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="870a7-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="870a7-157">Quite varios proyectos de C# de una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="870a7-157">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
