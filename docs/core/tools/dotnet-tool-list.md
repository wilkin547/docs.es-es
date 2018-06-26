---
title: Comando dotnet tool list - CLI de .NET Core
description: El comando dotnet tool list muestra la herramienta global especificada de .NET Core que hay instalada en el equipo.
author: mairaw
ms.author: mairaw
ms.date: 05/29/2018
ms.openlocfilehash: 5f4793cd37c3a8df06eb6930ad9f381ac70d4e67
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2018
ms.locfileid: "34696730"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="6f50f-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="6f50f-103">dotnet tool list</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="name"></a><span data-ttu-id="6f50f-104">nombre</span><span class="sxs-lookup"><span data-stu-id="6f50f-104">Name</span></span>

<span data-ttu-id="6f50f-105">`dotnet tool list`: enumera todas las [herramientas globales de .NET Core](global-tools.md) instaladas actualmente en el directorio predeterminado de la máquina o en la ruta especificada.</span><span class="sxs-lookup"><span data-stu-id="6f50f-105">`dotnet tool list` - Lists all [.NET Core Global Tools](global-tools.md) currently installed in the default directory on your machine or in the specified path.</span></span>

## <a name="synopsis"></a><span data-ttu-id="6f50f-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="6f50f-106">Synopsis</span></span>

```
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="6f50f-107">Description</span><span class="sxs-lookup"><span data-stu-id="6f50f-107">Description</span></span>

<span data-ttu-id="6f50f-108">El comando `dotnet tool list` muestra todas las herramientas globales de .NET Core instaladas para los usuarios en el equipo (perfil de usuario actual) o en la ruta de acceso especificada.</span><span class="sxs-lookup"><span data-stu-id="6f50f-108">The `dotnet tool list` command provides a way for you to list all .NET Core Global Tools installed user-wide on your machine (current user profile) or in the specified path.</span></span> <span data-ttu-id="6f50f-109">El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta global.</span><span class="sxs-lookup"><span data-stu-id="6f50f-109">The command lists the package name, version installed, and the Global Tool command.</span></span> <span data-ttu-id="6f50f-110">Para utilizar el comando list, especifique que quiere ver las herramientas de los usuarios con la opción `--global`, o bien especifique una ruta de acceso personalizada con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6f50f-110">To use the list command, you either have to specify that you want to see all user-wide tools using the `--global` option or specify a custom path using the `--tool-path` option.</span></span>

## <a name="options"></a><span data-ttu-id="6f50f-111">Opciones</span><span class="sxs-lookup"><span data-stu-id="6f50f-111">Options</span></span>

`-g|--global`

<span data-ttu-id="6f50f-112">Enumera las herramientas globales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="6f50f-112">Lists user-wide Global Tools.</span></span> <span data-ttu-id="6f50f-113">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6f50f-113">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="6f50f-114">Si no especifica esta opción, debe especificar la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="6f50f-114">If you don't specify this option, you must specify the `--tool-path` option.</span></span>

`-h|--help`

<span data-ttu-id="6f50f-115">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="6f50f-115">Prints out a short help for the command.</span></span>

`--tool-path <PATH>`

<span data-ttu-id="6f50f-116">Especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="6f50f-116">Specifies a custom location where to find Global Tools.</span></span> <span data-ttu-id="6f50f-117">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="6f50f-117">PATH can be absolute or relative.</span></span> <span data-ttu-id="6f50f-118">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="6f50f-118">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="6f50f-119">Si no especifica esta opción, debe especificar la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="6f50f-119">If you don't specify this option, you must specify the `--global` option.</span></span>

## <a name="examples"></a><span data-ttu-id="6f50f-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="6f50f-120">Examples</span></span>

<span data-ttu-id="6f50f-121">Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual):</span><span class="sxs-lookup"><span data-stu-id="6f50f-121">Lists all Global Tools installed user-wide on your machine (current user profile):</span></span>

`dotnet tool list -g`

<span data-ttu-id="6f50f-122">Enumera las herramientas globales de una carpeta específica de Windows:</span><span class="sxs-lookup"><span data-stu-id="6f50f-122">Lists the Global Tools from a specific Windows folder:</span></span>

`dotnet tool list --tool-path c:\global-tools`

<span data-ttu-id="6f50f-123">Enumera las herramientas globales de una carpeta específica de Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="6f50f-123">Lists the Global Tools from a specific Linux/macOS folder:</span></span>

`dotnet tool list --tool-path ~/bin`

## <a name="see-also"></a><span data-ttu-id="6f50f-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f50f-124">See also</span></span>

[<span data-ttu-id="6f50f-125">Herramientas globales de .NET Core</span><span class="sxs-lookup"><span data-stu-id="6f50f-125">.NET Core Global Tools</span></span>](global-tools.md)