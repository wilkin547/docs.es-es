---
title: Comando dotnet tool list
description: El comando dotnet tool list enumera las herramientas de .NET Core que están instaladas en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: bb74cfeaf441cf8a1a030d97d16655f85d8267d1
ms.sourcegitcommit: 771c554c84ba38cbd4ac0578324ec4cfc979cf2e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2020
ms.locfileid: "77543461"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="e553a-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="e553a-103">dotnet tool list</span></span>

<span data-ttu-id="e553a-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="e553a-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="e553a-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="e553a-105">Name</span></span>

<span data-ttu-id="e553a-106">`dotnet tool list`: enumera todas las [herramientas de .NET Core](global-tools.md) del tipo especificado actualmente instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e553a-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e553a-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="e553a-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>
dotnet tool list <--tool-path>
dotnet tool list
dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="e553a-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e553a-108">Description</span></span>

<span data-ttu-id="e553a-109">El comando `dotnet tool list` permite enumerar todas las herramientas locales, de ruta de acceso de herramientas y globales de .NET Core que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="e553a-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="e553a-110">El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="e553a-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="e553a-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="e553a-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="e553a-112">Una herramienta global instalada en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="e553a-112">A global tool installed in the default location.</span></span> <span data-ttu-id="e553a-113">Use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="e553a-113">Use the `--global` option</span></span>
* <span data-ttu-id="e553a-114">Una herramienta global instalada en una ubicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="e553a-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="e553a-115">Use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e553a-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="e553a-116">Una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="e553a-116">A local tool.</span></span> <span data-ttu-id="e553a-117">Omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e553a-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="e553a-118">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="e553a-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="e553a-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="e553a-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="e553a-120">Enumera las herramientas globales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="e553a-120">Lists user-wide global tools.</span></span> <span data-ttu-id="e553a-121">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="e553a-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="e553a-122">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="e553a-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span> 

- **`-h|--help`**

  <span data-ttu-id="e553a-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="e553a-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="e553a-124">Especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="e553a-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="e553a-125">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="e553a-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="e553a-126">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="e553a-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="e553a-127">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="e553a-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span> 

## <a name="examples"></a><span data-ttu-id="e553a-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="e553a-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="e553a-129">Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual).</span><span class="sxs-lookup"><span data-stu-id="e553a-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="e553a-130">Enumera las herramientas globales de un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="e553a-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="e553a-131">Enumera las herramientas globales de un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="e553a-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="e553a-132">Enumera todas las herramientas locales disponibles en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="e553a-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="e553a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="e553a-133">See also</span></span>

- [<span data-ttu-id="e553a-134">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="e553a-134">.NET Core tools</span></span>](global-tools.md)
