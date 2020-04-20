---
title: Comando dotnet tool list
description: El comando dotnet tool list enumera las herramientas de .NET Core que están instaladas en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 28f9155407d1238f8b0960b69b34ea329ca0e8e6
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463350"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="104e1-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="104e1-103">dotnet tool list</span></span>

<span data-ttu-id="104e1-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="104e1-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="104e1-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="104e1-105">Name</span></span>

<span data-ttu-id="104e1-106">`dotnet tool list`: enumera todas las [herramientas de .NET Core](global-tools.md) del tipo especificado actualmente instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="104e1-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="104e1-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="104e1-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="104e1-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="104e1-108">Description</span></span>

<span data-ttu-id="104e1-109">El comando `dotnet tool list` permite enumerar todas las herramientas locales, de ruta de acceso de herramientas y globales de .NET Core que están instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="104e1-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local Tools installed on your machine.</span></span> <span data-ttu-id="104e1-110">El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="104e1-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="104e1-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="104e1-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="104e1-112">Una herramienta global instalada en la ubicación predeterminada.</span><span class="sxs-lookup"><span data-stu-id="104e1-112">A global tool installed in the default location.</span></span> <span data-ttu-id="104e1-113">Use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="104e1-113">Use the `--global` option</span></span>
* <span data-ttu-id="104e1-114">Una herramienta global instalada en una ubicación personalizada.</span><span class="sxs-lookup"><span data-stu-id="104e1-114">A global tool installed in a custom location.</span></span> <span data-ttu-id="104e1-115">Use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="104e1-115">Use the `--tool-path` option.</span></span>
* <span data-ttu-id="104e1-116">Una herramienta local.</span><span class="sxs-lookup"><span data-stu-id="104e1-116">A local tool.</span></span> <span data-ttu-id="104e1-117">Omita las opciones `--global` y `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="104e1-117">Omit the `--global` and `--tool-path` options.</span></span>

<span data-ttu-id="104e1-118">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="104e1-118">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="104e1-119">Opciones</span><span class="sxs-lookup"><span data-stu-id="104e1-119">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="104e1-120">Enumera las herramientas globales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="104e1-120">Lists user-wide global tools.</span></span> <span data-ttu-id="104e1-121">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="104e1-121">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="104e1-122">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="104e1-122">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="104e1-123">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="104e1-123">Prints out a short help for the command.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="104e1-124">Especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="104e1-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="104e1-125">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="104e1-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="104e1-126">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="104e1-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="104e1-127">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="104e1-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="104e1-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="104e1-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="104e1-129">Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual).</span><span class="sxs-lookup"><span data-stu-id="104e1-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="104e1-130">Enumera las herramientas globales de un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="104e1-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="104e1-131">Enumera las herramientas globales de un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="104e1-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- **`dotnet tool list`**

  <span data-ttu-id="104e1-132">Enumera todas las herramientas locales disponibles en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="104e1-132">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="104e1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="104e1-133">See also</span></span>

- [<span data-ttu-id="104e1-134">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="104e1-134">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="104e1-135">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="104e1-135">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="104e1-136">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="104e1-136">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
