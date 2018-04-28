---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.workload:
- dotnetcore
ms.openlocfilehash: 946d3d523443fbe673b95dba95dbca327fde1699
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="4c0ce-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="4c0ce-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="4c0ce-104">nombre</span><span class="sxs-lookup"><span data-stu-id="4c0ce-104">Name</span></span>

<span data-ttu-id="4c0ce-105">`dotnet list reference`: enumera referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="4c0ce-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="4c0ce-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="4c0ce-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="4c0ce-107">Description</span><span class="sxs-lookup"><span data-stu-id="4c0ce-107">Description</span></span>

<span data-ttu-id="4c0ce-108">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.</span><span class="sxs-lookup"><span data-stu-id="4c0ce-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="4c0ce-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="4c0ce-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="4c0ce-110">Especifica el archivo de proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="4c0ce-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="4c0ce-111">Si no se especifica, el comando buscará uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="4c0ce-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="4c0ce-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="4c0ce-112">Options</span></span>

`-h|--help`

<span data-ttu-id="4c0ce-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="4c0ce-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="4c0ce-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="4c0ce-114">Examples</span></span>

<span data-ttu-id="4c0ce-115">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="4c0ce-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="4c0ce-116">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="4c0ce-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`
