---
title: Comando dotnet nuget delete
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.date: 12/04/2018
ms.openlocfilehash: 827d295d7a52b6c9c82adbcf3d25281bd1cc98fd
ms.sourcegitcommit: e6ad58812807937b03f5c581a219dcd7d1726b1d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/10/2018
ms.locfileid: "53168317"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="28f36-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="28f36-103">dotnet nuget delete</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="28f36-104">nombre</span><span class="sxs-lookup"><span data-stu-id="28f36-104">Name</span></span>

<span data-ttu-id="28f36-105">`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-105">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="28f36-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="28f36-106">Synopsis</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="28f36-107">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="28f36-107">.NET Core 2.x</span></span>](#tab/netcore2x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [--interactive] [-k|--api-key] [--no-service-endpoint]
    [--non-interactive] [-s|--source]
dotnet nuget delete [-h|--help]
```
# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="28f36-108">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="28f36-108">.NET Core 1.x</span></span>](#tab/netcore1x)
```
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output] [-k|--api-key] [--non-interactive]
    [-s|--source]
dotnet nuget delete [-h|--help]
```
---

## <a name="description"></a><span data-ttu-id="28f36-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="28f36-109">Description</span></span>

<span data-ttu-id="28f36-110">El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-110">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="28f36-111">Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.</span><span class="sxs-lookup"><span data-stu-id="28f36-111">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="28f36-112">Argumentos</span><span class="sxs-lookup"><span data-stu-id="28f36-112">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="28f36-113">Nombre o id. del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="28f36-113">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="28f36-114">Versión del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="28f36-114">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="28f36-115">Opciones</span><span class="sxs-lookup"><span data-stu-id="28f36-115">Options</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="28f36-116">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="28f36-116">.NET Core 2.x</span></span>](#tab/netcore2x)

* **`--force-english-output`**

  <span data-ttu-id="28f36-117">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="28f36-117">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="28f36-118">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="28f36-118">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="28f36-119">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="28f36-119">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="28f36-120">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="28f36-120">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="28f36-121">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-121">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="28f36-122">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="28f36-122">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="28f36-123">Opción disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="28f36-123">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="28f36-124">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="28f36-124">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="28f36-125">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-125">Specifies the server URL.</span></span> <span data-ttu-id="28f36-126">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="28f36-126">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="28f36-127">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="28f36-127">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

# <a name="net-core-1xtabnetcore1x"></a>[<span data-ttu-id="28f36-128">.NET Core 1.x</span><span class="sxs-lookup"><span data-stu-id="28f36-128">.NET Core 1.x</span></span>](#tab/netcore1x)

* **`--force-english-output`**

  <span data-ttu-id="28f36-129">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="28f36-129">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="28f36-130">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="28f36-130">Prints out a short help for the command.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="28f36-131">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-131">The API key for the server.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="28f36-132">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="28f36-132">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="28f36-133">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="28f36-133">Specifies the server URL.</span></span> <span data-ttu-id="28f36-134">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="28f36-134">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="28f36-135">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="28f36-135">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

---

## <a name="examples"></a><span data-ttu-id="28f36-136">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="28f36-136">Examples</span></span>

* <span data-ttu-id="28f36-137">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="28f36-137">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="28f36-138">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:</span><span class="sxs-lookup"><span data-stu-id="28f36-138">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```console
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```