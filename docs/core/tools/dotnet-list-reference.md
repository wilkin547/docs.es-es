---
title: 'Comando dotnet list reference: CLI de .NET Core'
description: "El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: b3e903c15a7486faa279d47ad5e2e00c090b19af
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-list-reference"></a><span data-ttu-id="2e9a5-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="2e9a5-103">dotnet list reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="2e9a5-104">Nombre</span><span class="sxs-lookup"><span data-stu-id="2e9a5-104">Name</span></span>

<span data-ttu-id="2e9a5-105">`dotnet list reference`: enumera referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="2e9a5-105">`dotnet list reference` - Lists project to project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="2e9a5-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="2e9a5-106">Synopsis</span></span>

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a><span data-ttu-id="2e9a5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e9a5-107">Description</span></span>

<span data-ttu-id="2e9a5-108">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.</span><span class="sxs-lookup"><span data-stu-id="2e9a5-108">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="2e9a5-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="2e9a5-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="2e9a5-110">Especifica el archivo de proyecto que se usará para enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="2e9a5-110">Specifies the project file to use for listing references.</span></span> <span data-ttu-id="2e9a5-111">Si no se especifica, el comando buscará uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="2e9a5-111">If not specified, the command will search the current directory for a project file.</span></span>

## <a name="options"></a><span data-ttu-id="2e9a5-112">Opciones</span><span class="sxs-lookup"><span data-stu-id="2e9a5-112">Options</span></span>

`-h|--help`

<span data-ttu-id="2e9a5-113">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="2e9a5-113">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="2e9a5-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="2e9a5-114">Examples</span></span>

<span data-ttu-id="2e9a5-115">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="2e9a5-115">List the project references for the specified project:</span></span>

`dotnet list app/app.csproj reference`

<span data-ttu-id="2e9a5-116">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="2e9a5-116">List the project references for the project in the current directory:</span></span>

`dotnet list reference`

