---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 821e6d276af44bf984c8ac1b42b4e954dbe69556
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34697188"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="2fd55-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2fd55-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2fd55-104">nombre</span><span class="sxs-lookup"><span data-stu-id="2fd55-104">Name</span></span>

<span data-ttu-id="2fd55-105">`dotnet list reference`: enumera las referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="2fd55-105">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2fd55-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="2fd55-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="2fd55-107">Description</span><span class="sxs-lookup"><span data-stu-id="2fd55-107">Description</span></span>

<span data-ttu-id="2fd55-108">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.</span><span class="sxs-lookup"><span data-stu-id="2fd55-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="2fd55-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2fd55-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2fd55-110">Especifica el archivo de proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="2fd55-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="2fd55-111">Si no se especifica, el comando busca un archivo del proyecto en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2fd55-111">If not specified, the command searches the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="2fd55-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="2fd55-112">Options</span></span>

`-h|--help`

<span data-ttu-id="2fd55-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2fd55-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2fd55-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2fd55-114">Examples</span></span>

<span data-ttu-id="2fd55-115">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="2fd55-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="2fd55-116">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="2fd55-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`