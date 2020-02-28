---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: 43c4dbc94b33e717c6ba0a1c1c5317ac006f5bba
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503716"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="036d8-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="036d8-103">dotnet list reference</span></span>

<span data-ttu-id="036d8-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="036d8-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="036d8-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="036d8-105">Name</span></span>

<span data-ttu-id="036d8-106">`dotnet list reference`: enumera las referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="036d8-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="036d8-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="036d8-107">Synopsis</span></span>

`dotnet list [<PROJECT>|<SOLUTION>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="036d8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="036d8-108">Description</span></span>

<span data-ttu-id="036d8-109">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto o solución concreta.</span><span class="sxs-lookup"><span data-stu-id="036d8-109">The `dotnet list reference` command provides a convenient option to list project references for a given project or solution.</span></span>

## <a name="arguments"></a><span data-ttu-id="036d8-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="036d8-110">Arguments</span></span>

* **`PROJECT | SOLUTION`**

  <span data-ttu-id="036d8-111">Especifica el archivo de solución o proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="036d8-111">Specifies the project or solution file to use for listing references.</span></span> <span data-ttu-id="036d8-112">Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="036d8-112">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="036d8-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="036d8-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="036d8-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="036d8-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="036d8-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="036d8-115">Examples</span></span>

* <span data-ttu-id="036d8-116">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="036d8-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="036d8-117">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="036d8-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
