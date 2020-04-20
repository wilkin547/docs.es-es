---
title: Comando dotnet nuget delete
description: El comando dotnet-nuget-delete elimina o quita de la lista un paquete del servidor.
author: karann-msft
ms.date: 06/26/2019
ms.openlocfilehash: 4fa4f24adba251d7872986de4a8b1a63203c36c3
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463581"
---
# <a name="dotnet-nuget-delete"></a><span data-ttu-id="c286f-103">dotnet nuget delete</span><span class="sxs-lookup"><span data-stu-id="c286f-103">dotnet nuget delete</span></span>

<span data-ttu-id="c286f-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c286f-104">**This article applies to:** ✔️ .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="c286f-105">Name</span><span class="sxs-lookup"><span data-stu-id="c286f-105">Name</span></span>

<span data-ttu-id="c286f-106">`dotnet nuget delete`: elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="c286f-106">`dotnet nuget delete` - Deletes or unlists a package from the server.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c286f-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c286f-107">Synopsis</span></span>

```dotnetcli
dotnet nuget delete [<PACKAGE_NAME> <PACKAGE_VERSION>] [--force-english-output]
    [--interactive] [-k|--api-key <API_KEY>] [--no-service-endpoint]
    [--non-interactive] [-s|--source <SOURCE>]

dotnet nuget delete -h|--help
```

## <a name="description"></a><span data-ttu-id="c286f-108">Description</span><span class="sxs-lookup"><span data-stu-id="c286f-108">Description</span></span>

<span data-ttu-id="c286f-109">El comando `dotnet nuget delete` elimina o quita de la lista un paquete del servidor.</span><span class="sxs-lookup"><span data-stu-id="c286f-109">The `dotnet nuget delete` command deletes or unlists a package from the server.</span></span> <span data-ttu-id="c286f-110">Para [nuget.org](https://www.nuget.org/), la acción es quitar de la lista el paquete.</span><span class="sxs-lookup"><span data-stu-id="c286f-110">For [nuget.org](https://www.nuget.org/), the action is to unlist the package.</span></span>

## <a name="arguments"></a><span data-ttu-id="c286f-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c286f-111">Arguments</span></span>

* **`PACKAGE_NAME`**

  <span data-ttu-id="c286f-112">Nombre o id. del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c286f-112">Name/ID of the package to delete.</span></span>

* **`PACKAGE_VERSION`**

  <span data-ttu-id="c286f-113">Versión del paquete que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c286f-113">Version of the package to delete.</span></span>

## <a name="options"></a><span data-ttu-id="c286f-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="c286f-114">Options</span></span>

* **`--force-english-output`**

  <span data-ttu-id="c286f-115">Fuerza la ejecución de la aplicación mediante una referencia cultural en inglés invariable.</span><span class="sxs-lookup"><span data-stu-id="c286f-115">Forces the application to run using an invariant, English-based culture.</span></span>

* **`-h|--help`**

  <span data-ttu-id="c286f-116">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c286f-116">Prints out a short help for the command.</span></span>

* **`--interactive`**

  <span data-ttu-id="c286f-117">Permite que el comando se bloquee y requiere una acción manual para operaciones tales como la autenticación.</span><span class="sxs-lookup"><span data-stu-id="c286f-117">Allows the command to block and requires manual action for operations like authentication.</span></span> <span data-ttu-id="c286f-118">Opción disponible a partir del SDK de .NET Core 2.2.</span><span class="sxs-lookup"><span data-stu-id="c286f-118">Option available since .NET Core 2.2 SDK.</span></span>

* **`-k|--api-key <API_KEY>`**

  <span data-ttu-id="c286f-119">La clave de API para el servidor.</span><span class="sxs-lookup"><span data-stu-id="c286f-119">The API key for the server.</span></span>

* **`--no-service-endpoint`**

  <span data-ttu-id="c286f-120">No agrega "api/v2/paquete" a la dirección URL de origen.</span><span class="sxs-lookup"><span data-stu-id="c286f-120">Doesn't append "api/v2/package" to the source URL.</span></span> <span data-ttu-id="c286f-121">Opción disponible a partir del SDK de .NET Core 2.1.</span><span class="sxs-lookup"><span data-stu-id="c286f-121">Option available since .NET Core 2.1 SDK.</span></span>

* **`--non-interactive`**

  <span data-ttu-id="c286f-122">No pide confirmaciones o entradas de usuario.</span><span class="sxs-lookup"><span data-stu-id="c286f-122">Doesn't prompt for user input or confirmations.</span></span>

* **`-s|--source <SOURCE>`**

  <span data-ttu-id="c286f-123">Especifica la dirección URL del servidor.</span><span class="sxs-lookup"><span data-stu-id="c286f-123">Specifies the server URL.</span></span> <span data-ttu-id="c286f-124">Las direcciones URL admitidas para nuget.org incluyen `https://www.nuget.org`, `https://www.nuget.org/api/v3` y `https://www.nuget.org/api/v2/package`.</span><span class="sxs-lookup"><span data-stu-id="c286f-124">Supported URLs for nuget.org include `https://www.nuget.org`, `https://www.nuget.org/api/v3`, and `https://www.nuget.org/api/v2/package`.</span></span> <span data-ttu-id="c286f-125">Para fuentes privadas, reemplace el nombre de host (por ejemplo, `%hostname%/api/v3`).</span><span class="sxs-lookup"><span data-stu-id="c286f-125">For private feeds, replace the host name (for example, `%hostname%/api/v3`).</span></span>

## <a name="examples"></a><span data-ttu-id="c286f-126">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c286f-126">Examples</span></span>

* <span data-ttu-id="c286f-127">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`:</span><span class="sxs-lookup"><span data-stu-id="c286f-127">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0
  ```

* <span data-ttu-id="c286f-128">Elimina la versión 1.0 del paquete `Microsoft.AspNetCore.Mvc`, sin pedir al usuario credenciales u otra información:</span><span class="sxs-lookup"><span data-stu-id="c286f-128">Deletes version 1.0 of package `Microsoft.AspNetCore.Mvc`, not prompting user for credentials or other input:</span></span>

  ```dotnetcli
  dotnet nuget delete Microsoft.AspNetCore.Mvc 1.0 --non-interactive
  ```
