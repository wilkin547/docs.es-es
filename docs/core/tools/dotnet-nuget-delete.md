---
title: 'Comando dotnet nuget delete: CLI de .NET Core'
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 65fe52f07ed823b4f7518c5b1f2da1f7a61b0371
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="ffe1d-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="ffe1d-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="ffe1d-104">Name</span><span class="sxs-lookup"><span data-stu-id="ffe1d-104">Name</span></span>

<span data-ttu-id="ffe1d-105">`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="ffe1d-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="ffe1d-106">Synopsis</span></span>

`dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [-s|--source] [--non-interactive] [-k|--api-key] [--force-english-output] [-h|--help]`

## <a name="description"></a><span data-ttu-id="ffe1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffe1d-107">Description</span></span>

<span data-ttu-id="ffe1d-108">El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-108">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="ffe1d-109">Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-109">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="ffe1d-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="ffe1d-110">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="ffe1d-111">Paquete para eliminar.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-111">Package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="ffe1d-112">Versión del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-112">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="ffe1d-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="ffe1d-113">Options</span></span>

`-h|--help`

<span data-ttu-id="ffe1d-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-114">Prints out a short help for the command.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="ffe1d-115">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-115">Specifies the server URL.</span></span> <span data-ttu-id="ffe1d-116">Las direcciones URL admitidas para nuget.org incluyen `http://www.nuget.org`, `http://www.nuget.org/api/v3` y `http://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-116">Supported URLs for nuget.org include `http://www.nuget.org`, `http://www.nuget.org/api/v3`, and `http://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="ffe1d-117">Para fuentes privadas, sustituya el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="ffe1d-117">For private feeds, substitute the host name (for example, `%hostname%/api/v3`).</span></span>

`--non-interactive`

<span data-ttu-id="ffe1d-118">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-118">Doesn't prompt for user input or confirmations.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="ffe1d-119">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-119">The API key for the server.</span></span>

`--force-english-output`

<span data-ttu-id="ffe1d-120">Fuerza la salida de la línea de comandos en inglés.</span><span class="sxs-lookup"><span data-stu-id="ffe1d-120">Forces command-line output in English.</span></span>

## <a name="examples"></a><span data-ttu-id="ffe1d-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="ffe1d-121">Examples</span></span>

<span data-ttu-id="ffe1d-122">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="ffe1d-122">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0` 

<span data-ttu-id="ffe1d-123">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:</span><span class="sxs-lookup"><span data-stu-id="ffe1d-123">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`