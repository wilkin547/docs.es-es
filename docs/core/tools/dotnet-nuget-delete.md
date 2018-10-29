---
title: 'Comando dotnet nuget delete: CLI de .NET Core'
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.author: mairaw
ms.date: 06/01/2018
ms.openlocfilehash: f4aa027a465c4adea1de13853063d03e8e295411
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/27/2018
ms.locfileid: "50180887"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="467ed-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="467ed-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="467ed-104">nombre</span><span class="sxs-lookup"><span data-stu-id="467ed-104">Name</span></span>

<span data-ttu-id="467ed-105">`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="467ed-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="467ed-106">Synopsis</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="467ed-107">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="467ed-107">.NET Core 2.1</span></span>](#tab/netcore21)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="467ed-108">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="467ed-108">.NET Core 2.0</span></span>](#tab/netcore20)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="467ed-109">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="467ed-109">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="467ed-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="467ed-110">Description</span></span>

<span data-ttu-id="467ed-111">El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-111">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="467ed-112">Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.</span><span class="sxs-lookup"><span data-stu-id="467ed-112">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="467ed-113">Argumentos</span><span class="sxs-lookup"><span data-stu-id="467ed-113">Arguments</span></span>

`PACKAGE_NAME`

<span data-ttu-id="467ed-114">Nombre o id. del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="467ed-114">Name/ID of the package to delete.</span></span>

`PACKAGE_VERSION`

<span data-ttu-id="467ed-115">Versión del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="467ed-115">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="467ed-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="467ed-116">Options</span></span>

# <a name="net-core-21tabnetcore21"></a>[<span data-ttu-id="467ed-117">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="467ed-117">.NET Core 2.1</span></span>](#tab/netcore21)

`--force-english-output`

 <span data-ttu-id="467ed-118">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="467ed-118">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="467ed-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="467ed-119">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="467ed-120">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-120">The API key for the server.</span></span>

<span data-ttu-id="467ed-121">`--no-service-endpoint` No agregue "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="467ed-121">`--no-service-endpoint` Doesn't append "api/v2/package" to the source URL.</span></span>

`--non-interactive`

<span data-ttu-id="467ed-122">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="467ed-122">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="467ed-123">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-123">Specifies the server URL.</span></span> <span data-ttu-id="467ed-124">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="467ed-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="467ed-125">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="467ed-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-20tabnetcore20"></a>[<span data-ttu-id="467ed-126">.NET Core 2.0</span><span class="sxs-lookup"><span data-stu-id="467ed-126">.NET Core 2.0</span></span>](#tab/netcore20)

`--force-english-output`

 <span data-ttu-id="467ed-127">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="467ed-127">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="467ed-128">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="467ed-128">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="467ed-129">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-129">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="467ed-130">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="467ed-130">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="467ed-131">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-131">Specifies the server URL.</span></span> <span data-ttu-id="467ed-132">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="467ed-132">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="467ed-133">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="467ed-133">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="467ed-134">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="467ed-134">.NET Core 1.x</span></span>](#tab/netcore1x)

`--force-english-output`

 <span data-ttu-id="467ed-135">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="467ed-135">Forces the application to run using an invariant, English-based culture.</span></span>

`-h|--help`

<span data-ttu-id="467ed-136">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="467ed-136">Prints out a short help for the command.</span></span>

`-k|--api-key <API_KEY>`

<span data-ttu-id="467ed-137">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-137">The API key for the server.</span></span>

`--non-interactive`

<span data-ttu-id="467ed-138">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="467ed-138">Doesn't prompt for user input or confirmations.</span></span>

`-s|--source <SOURCE>`

<span data-ttu-id="467ed-139">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="467ed-139">Specifies the server URL.</span></span> <span data-ttu-id="467ed-140">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="467ed-140">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="467ed-141">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="467ed-141">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="467ed-142">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="467ed-142">Examples</span></span>

<span data-ttu-id="467ed-143">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="467ed-143">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0`

<span data-ttu-id="467ed-144">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:</span><span class="sxs-lookup"><span data-stu-id="467ed-144">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

`dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive`
