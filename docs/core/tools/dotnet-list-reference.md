---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 06/26/2019
ms.openlocfilehash: b4b82ca1e7aeb2b73d9f99aff1c97452b2166770
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117675"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="9c1f9-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="9c1f9-103">dotnet list reference</span></span>

<span data-ttu-id="9c1f9-104">**Este tema se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9c1f9-104">**This topic applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="9c1f9-105">Name</span><span class="sxs-lookup"><span data-stu-id="9c1f9-105">Name</span></span>

<span data-ttu-id="9c1f9-106">`dotnet list reference`: enumera las referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="9c1f9-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9c1f9-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9c1f9-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="9c1f9-108">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="9c1f9-108">Description</span></span>

<span data-ttu-id="9c1f9-109">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.</span><span class="sxs-lookup"><span data-stu-id="9c1f9-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="9c1f9-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c1f9-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="9c1f9-111">Especifica el archivo de solución o proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="9c1f9-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="9c1f9-112">Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9c1f9-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="9c1f9-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="9c1f9-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="9c1f9-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9c1f9-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="9c1f9-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9c1f9-115">Examples</span></span>

* <span data-ttu-id="9c1f9-116">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="9c1f9-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="9c1f9-117">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="9c1f9-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
