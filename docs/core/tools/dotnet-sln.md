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
# <a name="dotnet-sln"></a>dotnet sln

**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores

## <a name="name"></a>NOMBRE

`dotnet sln`: enumera o modifica los proyectos en un archivo de solución de .NET.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command]

dotnet sln [command] -h|--help
```

## <a name="description"></a>Descripción

El comando `dotnet sln` proporciona una opción conveniente para enumerar y modificar los proyectos en un archivo de solución.

Para usar el comando `dotnet sln`, debe existir el archivo de solución. Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si se omite este argumento, el comando busca uno en el directorio actual. Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una descripción de cómo usar el comando.

## <a name="commands"></a>Comandos

### `list`

Enumera todos los proyectos en un archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si se omite este argumento, el comando busca uno en el directorio actual. Si encuentra varios archivos de solución o no encuentra ninguno, se produce un error en el comando.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una descripción de cómo usar el comando.
  
### `add`

Agrega uno o varios proyectos al archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder <PATH>] <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si no se especifica, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.

- **`PROJECT_PATH`**

  La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución. Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una descripción de cómo usar el comando.

- **`--in-root`**

  Coloca el proyecto en la raíz de la solución, en lugar de crear una carpeta de la solución. Disponible desde el SDK de .NET Core 3.0.

- **`-s|--solution-folder <PATH>`**

  La ruta de acceso de la [carpeta de la solución](/visualstudio/ide/solutions-and-projects-in-visual-studio#solution-folder) de destino a la que se van a agregar los proyectos. Disponible desde el SDK de .NET Core 3.0.

### `remove`

Quita un proyecto o varios proyectos del archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH> [<PROJECT_PATH>...]
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si se deja sin especificar, el comando busca uno en el directorio actual y produce un error si hay varios archivos de solución.

- **`PROJECT_PATH`**

  La ruta de acceso al proyecto o los proyectos que se van a agregar a la solución. Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una descripción de cómo usar el comando.

## <a name="examples"></a>Ejemplos

- Enumere los proyectos en una solución:

  ```dotnetcli
  dotnet sln todo.sln list
  ```

- Agregue un proyecto de C# a una solución:

  ```dotnetcli
  dotnet sln add todo-app/todo-app.csproj
  ```

- Quite un proyecto de C# de una solución:

  ```dotnetcli
  dotnet sln remove todo-app/todo-app.csproj
  ```

- Agregue varios proyectos de C# a la raíz de una solución:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj --in-root
  ```

- Agregue varios proyectos de C# a una solución:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Quite varios proyectos de C# de una solución:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj back-end/back-end.csproj
  ```

- Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo para Unix y Linux):

  ```dotnetcli
  dotnet sln todo.sln add **/*.csproj
  ```

- Agregue varios proyectos de C# a una solución mediante un patrón de comodines (solo Windows PowerShell):

  ```dotnetcli
  dotnet sln todo.sln add (ls -r **/*.csproj)
  ```

- Quite varios proyectos de C# de una solución mediante un patrón de comodines (solo para Unix y Linux):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```

- Quite varios proyectos de C# a una solución mediante un patrón de comodines (solo Windows PowerShell):

  ```dotnetcli
  dotnet sln todo.sln remove (ls -r **/*.csproj)
  ```

- Cree una solución, una aplicación de consola y dos bibliotecas de clases. Agregue los proyectos a la solución y use la opción `--solution-folder` de `dotnet sln` para organizar las bibliotecas de clases en una carpeta de soluciones.

  ```dotnetcli
  dotnet new sln -n mysolution
  dotnet new console -o myapp
  dotnet new classlib -o mylib1
  dotnet new classlib -o mylib2
  dotnet sln mysolution.sln add myapp\myapp.csproj
  dotnet sln mysolution.sln add mylib1\mylib1.csproj --solution-folder mylibs
  dotnet sln mysolution.sln add mylib2\mylib2.csproj --solution-folder mylibs
  ```

  En la captura de pantalla siguiente se muestra el resultado en el **Explorador de soluciones** de Visual Studio 2019:

  :::image type="content" source="media/dotnet-sln/dotnet-sln-solution-folder.png" alt-text="Explorador de soluciones mostrando los proyectos de biblioteca de clases agrupados en una carpeta de soluciones.":::
