---
title: 'Comando dotnet remove reference: CLI de .NET Core'
description: "El comando dotnet remove reference constituye una opción práctica para quitar las referencias entre proyectos."
keywords: dotnet-remove, CLI, comando de la CLI, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.workload: dotnetcore
ms.openlocfilehash: 691fd77c7605b6476adc764f20e59b51abd7d914
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="dotnet-remove-reference"></a><span data-ttu-id="67512-104">dotnet remove reference</span><span class="sxs-lookup"><span data-stu-id="67512-104">dotnet remove reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="67512-105">nombre</span><span class="sxs-lookup"><span data-stu-id="67512-105">Name</span></span>

<span data-ttu-id="67512-106">`dotnet remove reference`: quita las referencias de proyecto a proyecto.</span><span class="sxs-lookup"><span data-stu-id="67512-106">`dotnet remove reference` - Removes project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="67512-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="67512-107">Synopsis</span></span>

`dotnet remove [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="67512-108">Description</span><span class="sxs-lookup"><span data-stu-id="67512-108">Description</span></span>

<span data-ttu-id="67512-109">El comando `dotnet remove reference` constituye una opción práctica para quitar referencias de proyecto de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="67512-109">The `dotnet remove reference` command provides a convenient option to remove project references from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="67512-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="67512-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="67512-111">Archivo de proyecto de destino.</span><span class="sxs-lookup"><span data-stu-id="67512-111">Target project file.</span></span> <span data-ttu-id="67512-112">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="67512-112">If not specified, the command searches the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="67512-113">Referencias de proyecto a proyecto (P2P) para quitar.</span><span class="sxs-lookup"><span data-stu-id="67512-113">Project to project (P2P references to remove.</span></span> <span data-ttu-id="67512-114">Puede especificar uno o varios proyectos.</span><span class="sxs-lookup"><span data-stu-id="67512-114">You can specify one or multiple projects.</span></span> <span data-ttu-id="67512-115">Se admiten [patrones globales](https://en.wikipedia.org/wiki/Glob_(programming)) en terminales basados en Unix o Linux.</span><span class="sxs-lookup"><span data-stu-id="67512-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux based terminals.</span></span>

## <a name="options"></a><span data-ttu-id="67512-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="67512-116">Options</span></span>

`-h|--help`

<span data-ttu-id="67512-117">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="67512-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="67512-118">Quita la referencia solo cuando el destino es un [marco de trabajo](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="67512-118">Removes the reference only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="67512-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="67512-119">Examples</span></span>

<span data-ttu-id="67512-120">Quitar una referencia de proyecto del proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="67512-120">Remove a project reference from the specified project:</span></span>

`dotnet remove app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="67512-121">Quitar varias referencias de proyecto del proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="67512-121">Remove multiple project references from the project in the current directory:</span></span>

`dotnet remove reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="67512-122">Quitar varias referencias de proyecto con un patrón global en Unix/Linux:</span><span class="sxs-lookup"><span data-stu-id="67512-122">Remove multiple project references using a glob pattern on Unix/Linux:</span></span>

`dotnet remove app/app.csproj reference **/*.csproj`
