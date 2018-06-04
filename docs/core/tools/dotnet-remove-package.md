---
title: 'Comando dotnet remove package: CLI de .NET Core'
description: El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: ed6086bfdfadaa06494c857fc74687f1273af971
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696863"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="afb4e-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="afb4e-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="afb4e-104">nombre</span><span class="sxs-lookup"><span data-stu-id="afb4e-104">Name</span></span>

<span data-ttu-id="afb4e-105">`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="afb4e-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="afb4e-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="afb4e-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="afb4e-107">Description</span><span class="sxs-lookup"><span data-stu-id="afb4e-107">Description</span></span>

<span data-ttu-id="afb4e-108">El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="afb4e-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="afb4e-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="afb4e-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="afb4e-110">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="afb4e-110">Specifies the project file.</span></span> <span data-ttu-id="afb4e-111">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="afb4e-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="afb4e-112">La referencia de paquete que hay que quitar.</span><span class="sxs-lookup"><span data-stu-id="afb4e-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="afb4e-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="afb4e-113">Options</span></span>

`-h|--help`

<span data-ttu-id="afb4e-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="afb4e-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="afb4e-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="afb4e-115">Examples</span></span>

<span data-ttu-id="afb4e-116">Quita el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="afb4e-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`