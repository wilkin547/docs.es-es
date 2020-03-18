---
title: Comando dotnet remove reference
description: El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: fcadf677faaf9281fb019c3c4bb16efc906b1aa1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "77503622"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="ddb8b-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="ddb8b-103">dotnet remove reference</span></span>

<span data-ttu-id="ddb8b-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="ddb8b-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="ddb8b-105">Name</span><span class="sxs-lookup"><span data-stu-id="ddb8b-105">Name</span></span>

<span data-ttu-id="ddb8b-106">`dotnet remove reference`: quita las referencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ddb8b-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ddb8b-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]
```

## <a name="description"></a><span data-ttu-id="ddb8b-108">Description</span><span class="sxs-lookup"><span data-stu-id="ddb8b-108">Description</span></span>

<span data-ttu-id="ddb8b-109">El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="ddb8b-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ddb8b-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="ddb8b-111">Archivo de proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-111">Target project file.</span></span> <span data-ttu-id="ddb8b-112">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="ddb8b-113">Referencias de proyecto a proyecto (P2P) que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-113">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="ddb8b-114">Puede especificar uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="ddb8b-115">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="ddb8b-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="ddb8b-116">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="ddb8b-117">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-117">Prints out a short help for the command.</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="ddb8b-118">Quita la referencia solo cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="ddb8b-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="ddb8b-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ddb8b-119">Examples</span></span>

- <span data-ttu-id="ddb8b-120">Quitar una referencia de proyecto del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="ddb8b-120">Remove a project reference from the specified project:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="ddb8b-121">Quitar varias referencias de proyecto del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="ddb8b-121">Remove multiple project references from the project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="ddb8b-122">Quitar varias referencias de proyecto con un patrón global en Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="ddb8b-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

  ```dotnetcli
  dotnet remove app/app.csproj reference **/*.csproj`
  ```
