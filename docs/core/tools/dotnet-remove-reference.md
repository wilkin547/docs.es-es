---
title: Comando dotnet remove reference
description: El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos.
ms.date: 05/29/2018
ms.openlocfilehash: bfac4721743babcf48fd8e86a50c8df136e1bfce
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53170618"
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="3ec1c-103">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="3ec1c-103">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3ec1c-104">nombre</span><span class="sxs-lookup"><span data-stu-id="3ec1c-104">Name</span></span>

<span data-ttu-id="3ec1c-105">`dotnet remove reference`: quita las referencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-105">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3ec1c-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3ec1c-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="3ec1c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ec1c-107">Description</span></span>

<span data-ttu-id="3ec1c-108">El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-108">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="3ec1c-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="3ec1c-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="3ec1c-110">Archivo de proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-110">Target project file.</span></span> <span data-ttu-id="3ec1c-111">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-111">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="3ec1c-112">Referencias de proyecto a proyecto (P2P) que se van a quitar.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-112">Project-to-project (P2P) references to remove.</span></span> <span data-ttu-id="3ec1c-113">Puede especificar uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-113">You can specify one or multiple projects.</span></span> <span data-ttu-id="3ec1c-114">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-114">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="3ec1c-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="3ec1c-115">Options</span></span>

`-h|--help`

<span data-ttu-id="3ec1c-116">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-116">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="3ec1c-117">Quita la referencia solo cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="3ec1c-117">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="3ec1c-118">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3ec1c-118">Examples</span></span>

<span data-ttu-id="3ec1c-119">Quitar una referencia de proyecto del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="3ec1c-119">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="3ec1c-120">Quitar varias referencias de proyecto del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="3ec1c-120">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="3ec1c-121">Quitar varias referencias de proyecto con un patrón global en Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="3ec1c-121">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
