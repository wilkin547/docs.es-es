---
title: Comando dotnet add reference
description: El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: 84ea25e94efc8d84aebfeccf62c30a64551c5019
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503786"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="0e049-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="0e049-103">dotnet add reference</span></span>

<span data-ttu-id="0e049-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="0e049-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="0e049-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="0e049-105">Name</span></span>

<span data-ttu-id="0e049-106">`dotnet add reference` Agrega referencias entre proyectos (P2P) .</span><span class="sxs-lookup"><span data-stu-id="0e049-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="0e049-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="0e049-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help] [--interactive]`

## <a name="description"></a><span data-ttu-id="0e049-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e049-108">Description</span></span>

<span data-ttu-id="0e049-109">El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="0e049-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="0e049-110">Después de ejecutar el comando, los elementos `<ProjectReference>` se agregan al archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0e049-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="0e049-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="0e049-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="0e049-112">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="0e049-112">Specifies the project file.</span></span> <span data-ttu-id="0e049-113">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="0e049-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="0e049-114">Referencias entre proyectos (P2P) que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="0e049-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="0e049-115">Especifique uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="0e049-115">Specify one or more projects.</span></span> <span data-ttu-id="0e049-116">[El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="0e049-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="0e049-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="0e049-117">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="0e049-118">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="0e049-118">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="0e049-119">Agrega referencias de proyecto solo cuando apunta a un[marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="0e049-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

- **`--interactive`**

  <span data-ttu-id="0e049-120">Permite que el comando se detenga y espere la entrada o acción del usuario (por ejemplo, completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="0e049-120">Allows the command to stop and wait for user input or action (for example, to complete authentication).</span></span> <span data-ttu-id="0e049-121">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="0e049-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="0e049-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="0e049-122">Examples</span></span>

- <span data-ttu-id="0e049-123">Agregar una referencia de proyecto:</span><span class="sxs-lookup"><span data-stu-id="0e049-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="0e049-124">Agregar varias referencias de proyecto al proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="0e049-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="0e049-125">Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="0e049-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
