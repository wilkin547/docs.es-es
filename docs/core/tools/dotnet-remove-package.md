---
title: Comando dotnet remove package
description: El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto.
ms.date: 05/29/2018
ms.openlocfilehash: 4cc8ac927b761547dc5e53be9abeba827bf1e1d9
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168733"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="8d022-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="8d022-103">dotnet remove package</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="8d022-104">nombre</span><span class="sxs-lookup"><span data-stu-id="8d022-104">Name</span></span>

<span data-ttu-id="8d022-105">`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d022-105">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="8d022-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="8d022-106">Synopsis</span></span>

`dotnet remove [<PROJECT>] package <PACKAGE_NAME> [-h|--help]`

## <a name="description"></a><span data-ttu-id="8d022-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d022-107">Description</span></span>

<span data-ttu-id="8d022-108">El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d022-108">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="8d022-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="8d022-109">Arguments</span></span>

`PROJECT`

<span data-ttu-id="8d022-110">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="8d022-110">Specifies the project file.</span></span> <span data-ttu-id="8d022-111">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="8d022-111">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="8d022-112">La referencia de paquete que hay que quitar.</span><span class="sxs-lookup"><span data-stu-id="8d022-112">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="8d022-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="8d022-113">Options</span></span>

`-h|--help`

<span data-ttu-id="8d022-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="8d022-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="8d022-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="8d022-115">Examples</span></span>

<span data-ttu-id="8d022-116">Quita el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="8d022-116">Removes `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

`dotnet remove package Newtonsoft.Json`