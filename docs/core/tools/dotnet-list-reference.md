---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 12/03/2018
ms.openlocfilehash: c0b88c4a0af4469d7ddc9e0a9368bb1b2d9d20b6
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65632410"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="c8d4c-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="c8d4c-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="c8d4c-104">nombre</span><span class="sxs-lookup"><span data-stu-id="c8d4c-104">Name</span></span>

<span data-ttu-id="c8d4c-105">`dotnet list reference`: enumera las referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="c8d4c-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c8d4c-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c8d4c-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="c8d4c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8d4c-107">Description</span></span>

<span data-ttu-id="c8d4c-108">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.</span><span class="sxs-lookup"><span data-stu-id="c8d4c-108">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="c8d4c-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c8d4c-109">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="c8d4c-110">Especifica el archivo de proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="c8d4c-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="c8d4c-111">Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c8d4c-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="c8d4c-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="c8d4c-112">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c8d4c-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c8d4c-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="c8d4c-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c8d4c-114">Examples</span></span>

* <span data-ttu-id="c8d4c-115">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="c8d4c-115">List the project references for the specified project:</span></span>

  ```console
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="c8d4c-116">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c8d4c-116">List the project references for the project in the current directory:</span></span>

  ```console
  dotnet list reference
  ```
