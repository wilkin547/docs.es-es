---
title: Comando dotnet sln
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
ms.date: 12/07/2020
ms.openlocfilehash: af502efe842e9c9610137738d86c05e00a3b37df
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633655"
---
# <a name="dotnet-sln"></a><span data-ttu-id="0aad9-103">dotnet sln</span><span class="sxs-lookup"><span data-stu-id="0aad9-103">dotnet sln</span></span>

<span data-ttu-id="0aad9-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0aad9-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="0aad9-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0aad9-105">Name</span></span>

<span data-ttu-id="0aad9-106">`dotnet sln`: enumera o modifica los proyectos en un archivo de solución de .NET.</span><span class="sxs-lookup"><span data-stu-id="0aad9-106">`dotnet sln` - Lists or modifies the projects in a .NET solution file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0aad9-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0aad9-107">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a><span data-ttu-id="0aad9-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0aad9-108">Description</span></span>

<span data-ttu-id="0aad9-109">El comando `dotnet sln` proporciona una opción conveniente para enumerar y modificar los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-109">The `dotnet sln` command provides a convenient way to list and modify projects in a solution file.</span></span>

<span data-ttu-id="0aad9-110">Para usar el comando `dotnet sln`, debe existir el archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-110">To use the `dotnet sln` command, the solution file must already exist.</span></span> <span data-ttu-id="0aad9-111">Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="0aad9-111">If you need to create one, use the [dotnet new](dotnet-new.md) command, as in the following example:</span></span>

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a><span data-ttu-id="0aad9-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0aad9-112">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0aad9-113">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0aad9-113">The solution file to use.</span></span> <span data-ttu-id="0aad9-114">Si se omite este argumento, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0aad9-114">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="0aad9-115">Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-115">If it finds no solution file or multiple solution files, the command fails.</span></span>

## <a name="options"></a><span data-ttu-id="0aad9-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="0aad9-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0aad9-117">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-117">Prints out a description of how to use the command.</span></span>

## <a name="commands"></a><span data-ttu-id="0aad9-118">Comandos</span><span class="sxs-lookup"><span data-stu-id="0aad9-118">Commands</span></span>

### `list`

<span data-ttu-id="0aad9-119">Enumera todos los proyectos en un archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-119">Lists all projects in a solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0aad9-120">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0aad9-120">Synopsis</span></span>

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0aad9-121">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0aad9-121">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0aad9-122">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0aad9-122">The solution file to use.</span></span> <span data-ttu-id="0aad9-123">Si se omite este argumento, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0aad9-123">If this argument is omitted, the command searches the current directory for one.</span></span> <span data-ttu-id="0aad9-124">Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-124">If it finds no solution file or multiple solution files, the command fails.</span></span>

#### <a name="options"></a><span data-ttu-id="0aad9-125">Opciones</span><span class="sxs-lookup"><span data-stu-id="0aad9-125">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0aad9-126">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-126">Prints out a description of how to use the command.</span></span>
  
### `add`

<span data-ttu-id="0aad9-127">Agrega uno o varios proyectos al archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-127">Adds one or more projects to the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0aad9-128">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0aad9-128">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0aad9-129">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0aad9-129">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0aad9-130">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0aad9-130">The solution file to use.</span></span> <span data-ttu-id="0aad9-131">Si no se especifica, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-131">If it is unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0aad9-132">La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-132">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="0aad9-133">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="0aad9-133">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0aad9-134">Opciones</span><span class="sxs-lookup"><span data-stu-id="0aad9-134">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0aad9-135">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-135">Prints out a description of how to use the command.</span></span>

- **`--in-root`**

  <span data-ttu-id="0aad9-136">Coloca el proyecto en la raíz de la solución, en lugar de crear una carpeta de la solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-136">Places the projects in the root of the solution, rather than creating a solution folder.</span></span> <span data-ttu-id="0aad9-137">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="0aad9-137">Available since .NET Core 3.0 SDK.</span></span>

- **`-s|--solution-folder <PATH>`**

  <span data-ttu-id="0aad9-138">La ruta de acceso de la [carpeta de la solución](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder) de destino a la que se van a agregar los proyectos.</span><span class="sxs-lookup"><span data-stu-id="0aad9-138">The destination [solution folder](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder) path to add the projects to.</span></span> <span data-ttu-id="0aad9-139">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="0aad9-139">Available since .NET Core 3.0 SDK.</span></span>

### `remove`

<span data-ttu-id="0aad9-140">Quita un proyecto o varios proyectos del archivo de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-140">Removes a project or multiple projects from the solution file.</span></span>

#### <a name="synopsis"></a><span data-ttu-id="0aad9-141">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0aad9-141">Synopsis</span></span>

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a><span data-ttu-id="0aad9-142">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0aad9-142">Arguments</span></span>

- **`SOLUTION_FILE`**

  <span data-ttu-id="0aad9-143">El archivo de solución que se va a usar.</span><span class="sxs-lookup"><span data-stu-id="0aad9-143">The solution file to use.</span></span> <span data-ttu-id="0aad9-144">Si se deja sin especificar, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-144">If is left unspecified, the command searches the current directory for one and fails if there are multiple solution files.</span></span>

- **`PROJECT_PATH`**

  <span data-ttu-id="0aad9-145">La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución.</span><span class="sxs-lookup"><span data-stu-id="0aad9-145">The path to the project or projects to add to the solution.</span></span> <span data-ttu-id="0aad9-146">Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.</span><span class="sxs-lookup"><span data-stu-id="0aad9-146">Unix/Linux shell [globbing pattern](https://en.wikipedia.org/wiki/Glob_(programming)) expansions are processed correctly by the `dotnet sln` command.</span></span>

#### <a name="options"></a><span data-ttu-id="0aad9-147">Opciones</span><span class="sxs-lookup"><span data-stu-id="0aad9-147">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0aad9-148">Imprime una descripción de cómo usar el comando.</span><span class="sxs-lookup"><span data-stu-id="0aad9-148">Prints out a description of how to use the command.</span></span>

## <a name="examples"></a><span data-ttu-id="0aad9-149">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0aad9-149">Examples</span></span>

- <span data-ttu-id="0aad9-150">Enumere los proyectos en una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-150">List the projects in a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- <span data-ttu-id="0aad9-151">Agregue un proyecto de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-151">Add a C# project to a solution:</span></span>

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- <span data-ttu-id="0aad9-152">Quite un proyecto de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-152">Remove a C# project from a solution:</span></span>

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- <span data-ttu-id="0aad9-153">Agregue varios proyectos de C# a la raíz de una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-153">Add multiple C# projects to the root of a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- <span data-ttu-id="0aad9-154">Agregue varios proyectos de C# a una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-154">Add multiple C# projects to a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="0aad9-155">Quite varios proyectos de C# de una solución:</span><span class="sxs-lookup"><span data-stu-id="0aad9-155">Remove multiple C# projects from a solution:</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- <span data-ttu-id="0aad9-156">Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="0aad9-156">Add multiple C# projects to a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- <span data-ttu-id="0aad9-157">Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="0aad9-157">Add multiple C# projects to a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- <span data-ttu-id="0aad9-158">Quite varios proyectos de C# de una solución mediante un patrón de comodines (solo para Unix y Linux):</span><span class="sxs-lookup"><span data-stu-id="0aad9-158">Remove multiple C# projects from a solution using a globbing pattern (Unix/Linux only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- <span data-ttu-id="0aad9-159">Quite varios proyectos de C# a una solución mediante un patrón de comodines (solo Windows PowerShell):</span><span class="sxs-lookup"><span data-stu-id="0aad9-159">Remove multiple C# projects from a solution using a globbing pattern (Windows PowerShell only):</span></span>

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```

- <span data-ttu-id="0aad9-160">Cree una solución, una aplicación de consola y dos bibliotecas de clases.</span><span class="sxs-lookup"><span data-stu-id="0aad9-160">Create a solution, a console app, and two class libraries.</span></span> <span data-ttu-id="0aad9-161">Agregue los proyectos a la solución y use la opción `--solution-folder` de `dotnet sln` para organizar las bibliotecas de clases en una carpeta de soluciones.</span><span class="sxs-lookup"><span data-stu-id="0aad9-161">Add the projects to the solution, and use the `--solution-folder` option of `dotnet sln` to organize the class libraries into a solution folder.</span></span>

  ```dotnetcli
  dotnet new sln -n mysolution
  dotnet new console -o myapp
  dotnet new classlib -o mylib1
  dotnet new classlib -o mylib2
  dotnet sln mysolution.sln add myapp\myapp.csproj
  dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
  dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs
  ```

  <span data-ttu-id="0aad9-162">En la captura de pantalla siguiente se muestra el resultado en el **Explorador de soluciones** de Visual Studio 2019:</span><span class="sxs-lookup"><span data-stu-id="0aad9-162">The following screenshot shows the result in Visual Studio 2019 **Solution Explorer**:</span></span>

  :::image type="content" source="media/dotnet-sln/dotnet-sln-solution-folder.png" alt-text="Explorador de soluciones mostrando los proyectos de biblioteca de clases agrupados en una carpeta de soluciones.":::
