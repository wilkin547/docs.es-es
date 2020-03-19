---
title: Comando dotnet tool list
description: El comando dotnet tool list enumera las herramientas de .NET Core que están instaladas en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: def3c345a775e5a65ec3d37718d207c80ca7ceee
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78847877"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="96a3d-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="96a3d-103">dotnet tool list</span></span>

<span data-ttu-id="96a3d-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="96a3d-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="96a3d-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="96a3d-105">Name</span></span>

<span data-ttu-id="96a3d-106">`dotnet tool list`: enumera todas las [herramientas de .NET Core](global-tools.md) del tipo especificado actualmente instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="96a3d-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="96a3d-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="96a3d-107">Synopsis</span></span>

```dotnetcli
dotnet tool list <-g|--global>

dotnet tool list <--tool-path>

dotnet tool list

dotnet tool list <-h|--help>
```

## <a name="description"></a><span data-ttu-id="96a3d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="96a3d-108">Description</span></span>

<span data-ttu-id="96a3d-109">El comando `dotnet tool list` permite enumerar todas las herramientas locales, de ruta de acceso de herramientas y globales de .NET Core que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="96a3d-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="96a3d-110">El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="96a3d-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="96a3d-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="96a3d-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="96a3d-112">Una herramienta global instalada en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="96a3d-112">A global tool installed in the default location.</span></span> <span data-ttu-id="96a3d-113">Use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="96a3d-113">Use the `--global` option</span></span>
* <span data-ttu-id="96a3d-114">Una herramienta global instalada en una ubicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="96a3d-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="96a3d-115">Use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="96a3d-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="96a3d-116">Una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="96a3d-116">A local tool.</span></span> <span data-ttu-id="96a3d-117">Omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="96a3d-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="96a3d-118">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="96a3d-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="96a3d-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="96a3d-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="96a3d-120">Enumera las herramientas globales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="96a3d-120">Lists user-wide global tools.</span></span> <span data-ttu-id="96a3d-121">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="96a3d-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="96a3d-122">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="96a3d-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="96a3d-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="96a3d-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="96a3d-124">Especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="96a3d-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="96a3d-125">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="96a3d-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="96a3d-126">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="96a3d-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="96a3d-127">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="96a3d-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="96a3d-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="96a3d-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="96a3d-129">Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual).</span><span class="sxs-lookup"><span data-stu-id="96a3d-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="96a3d-130">Enumera las herramientas globales de un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="96a3d-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="96a3d-131">Enumera las herramientas globales de un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="96a3d-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="96a3d-132">Enumera todas las herramientas locales disponibles en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="96a3d-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="96a3d-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="96a3d-133">See also</span></span>

- [<span data-ttu-id="96a3d-134">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96a3d-134">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="96a3d-135">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96a3d-135">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="96a3d-136">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="96a3d-136">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
