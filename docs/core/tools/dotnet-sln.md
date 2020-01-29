---
title: Comando dotnet sln
description: El comando dotnet-sln proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.
ms.date: 10/29/2019
ms.openlocfilehash: e344deaae0867202a79a3c38df48a2be8d4d7d13
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733073"
---
# <a name="dotnet-sln"></a>dotnet sln

**Este artículo se aplica a:** ✔️ SDK de .NET Core 1.x y versiones posteriores

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a>NOMBRE

`dotnet sln`: modifica un archivo de solución de .NET Core.

## <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] [command] [-h|--help]
```

## <a name="description"></a>Descripción

El comando `dotnet sln` proporciona una opción conveniente para agregar, quitar y enumerar los proyectos en un archivo de solución.

Para usar el comando `dotnet sln`, debe existir el archivo de solución. Si necesita crear uno, use el comando [dotnet new](dotnet-new.md), como en el ejemplo siguiente:

```dotnetcli
dotnet new sln
```

## <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si no se especifica, el comando busca uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

## <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="commands"></a>Comandos

### `add`

Agrega un proyecto o varios proyectos al archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] add [--in-root] [-s|--solution-folder] <PROJECT_PATH>
dotnet sln add [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si no se especifica, el comando busca uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

- **`PROJECT_PATH`**

  La ruta de acceso al proyecto que se va a agregar a la solución. Para agregar varios proyectos, agregue uno detrás de otro separados por espacios. Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

- **`--in-root`**

  Coloca el proyecto en la raíz de la solución, en lugar de crear una carpeta de la solución. Disponible desde el SDK de .NET Core 3.0.

- **`-s|--solution-folder`**

  La ruta de acceso de la carpeta de la solución de destino a la que se van a agregar los proyectos. Disponible desde el SDK de .NET Core 3.0.

### `remove`

Quita un proyecto o varios proyectos del archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln [<SOLUTION_FILE>] remove <PROJECT_PATH>
dotnet sln [<SOLUTION_FILE>] remove [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si no se especifica, el comando busca uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

- **`PROJECT_PATH`**

  La ruta de acceso al proyecto que se va a quitar de la solución. Para quitar varios proyectos, agregue uno detrás de otro separados por espacios. Las expansiones del [patrón comodines](https://en.wikipedia.org/wiki/Glob_(programming)) de shell de Unix y Linux se procesan correctamente mediante el comando `dotnet sln`.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

### `list`

Enumera todos los proyectos en un archivo de solución.

#### <a name="synopsis"></a>Sinopsis

```dotnetcli
dotnet sln list [-h|--help]
```

#### <a name="arguments"></a>Argumentos

- **`SOLUTION_FILE`**

  El archivo de solución que se va a usar. Si no se especifica, el comando busca uno en el directorio actual. Si hay varios archivos de solución en el directorio, se debe especificar uno.

#### <a name="options"></a>Opciones

- **`-h|--help`**

  Imprime una corta ayuda para el comando.

## <a name="examples"></a>Ejemplos

- Agregue un proyecto de C# a una solución:

  ```dotnetcli
  dotnet sln todo.sln add todo-app/todo-app.csproj
  ```

- Quite un proyecto de C# de una solución:

  ```dotnetcli
  dotnet sln todo.sln remove todo-app/todo-app.csproj
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

- Quite varios proyectos de C# de una solución mediante un patrón de comodines (solo para Unix y Linux):

  ```dotnetcli
  dotnet sln todo.sln remove **/*.csproj
  ```
