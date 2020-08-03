---
title: Comando dotnet tool list
description: El comando dotnet tool list enumera las herramientas de .NET Core que están instaladas en el equipo.
ms.date: 02/14/2020
ms.openlocfilehash: 4035c5be233232e53c6d7150485f737108c1e18d
ms.sourcegitcommit: 40de8df14289e1e05b40d6e5c1daabd3c286d70c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/22/2020
ms.locfileid: "86925467"
---
# <a name="dotnet-tool-list"></a><span data-ttu-id="3b688-103">dotnet tool list</span><span class="sxs-lookup"><span data-stu-id="3b688-103">dotnet tool list</span></span>

<span data-ttu-id="3b688-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.1 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="3b688-104">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="3b688-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="3b688-105">Name</span></span>

<span data-ttu-id="3b688-106">`dotnet tool list`: enumera todas las [herramientas de .NET Core](global-tools.md) del tipo especificado actualmente instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3b688-106">`dotnet tool list` - Lists all [.NET Core tools](global-tools.md) of the specified type currently installed on your machine.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3b688-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3b688-107">Synopsis</span></span>

```dotnetcli
dotnet tool list -g|--global

dotnet tool list --tool-path <PATH>

dotnet tool list --local

dotnet tool list

dotnet tool list -h|--help
```

## <a name="description"></a><span data-ttu-id="3b688-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b688-108">Description</span></span>

<span data-ttu-id="3b688-109">El comando `dotnet tool list` permite enumerar todas las herramientas locales, de ruta de acceso de herramientas y globales de .NET Core instaladas en el equipo.</span><span class="sxs-lookup"><span data-stu-id="3b688-109">The `dotnet tool list` command provides a way for you to list all .NET Core global, tool-path, or local tools installed on your machine.</span></span> <span data-ttu-id="3b688-110">El comando enumera el nombre del paquete, la versión instalada y el comando de la herramienta.</span><span class="sxs-lookup"><span data-stu-id="3b688-110">The command lists the package name, version installed, and the tool command.</span></span>  <span data-ttu-id="3b688-111">Para usar el comando, especifique una de las siguientes opciones:</span><span class="sxs-lookup"><span data-stu-id="3b688-111">To use the command, you specify one of the following:</span></span>

* <span data-ttu-id="3b688-112">Para enumerar las herramientas globales instaladas en la ubicación predeterminada, use la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="3b688-112">To list global tools installed in the default location, use the `--global` option</span></span>
* <span data-ttu-id="3b688-113">Para enumerar las herramientas globales instaladas en la ubicación personalizada, use la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="3b688-113">To list global tools installed in a custom location, use the `--tool-path` option.</span></span>
* <span data-ttu-id="3b688-114">Para enumerar las herramientas locales, use la opción `--local` u omita las opciones `--global`, `--tool-path` y `--local`.</span><span class="sxs-lookup"><span data-stu-id="3b688-114">To list local tools, use the `--local` option or omit the `--global`, `--tool-path`, and `--local` options.</span></span>

<span data-ttu-id="3b688-115">**Las herramientas locales están disponibles a partir del SDK de .NET Core 3.0.**</span><span class="sxs-lookup"><span data-stu-id="3b688-115">**Local tools are available starting with .NET Core SDK 3.0.**</span></span>

## <a name="options"></a><span data-ttu-id="3b688-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="3b688-116">Options</span></span>

- **`-g|--global`**

  <span data-ttu-id="3b688-117">Enumera las herramientas globales de los usuarios.</span><span class="sxs-lookup"><span data-stu-id="3b688-117">Lists user-wide global tools.</span></span> <span data-ttu-id="3b688-118">No se puede combinar con la opción `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="3b688-118">Can't be combined with the `--tool-path` option.</span></span> <span data-ttu-id="3b688-119">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="3b688-119">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

- **`-h|--help`**

  <span data-ttu-id="3b688-120">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="3b688-120">Prints out a short help for the command.</span></span>

- **`--local`**

  <span data-ttu-id="3b688-121">Enumera las herramientas locales del directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3b688-121">Lists local tools for the current directory.</span></span> <span data-ttu-id="3b688-122">No se puede combinar con las opciones `--global` o `--tool-path`.</span><span class="sxs-lookup"><span data-stu-id="3b688-122">Can't be combined with the `--global` or `--tool-path` options.</span></span> <span data-ttu-id="3b688-123">Al omitir `--global` y `--tool-path`, se enumeran las herramientas locales, aunque no se haya especificado `--local`.</span><span class="sxs-lookup"><span data-stu-id="3b688-123">Omitting both `--global` and `--tool-path` lists local tools even if `--local` is not specified.</span></span>

- **`--tool-path <PATH>`**

  <span data-ttu-id="3b688-124">Especifica una ubicación personalizada para las herramientas globales.</span><span class="sxs-lookup"><span data-stu-id="3b688-124">Specifies a custom location where to find global tools.</span></span> <span data-ttu-id="3b688-125">PATH puede ser una ruta absoluta o relativa.</span><span class="sxs-lookup"><span data-stu-id="3b688-125">PATH can be absolute or relative.</span></span> <span data-ttu-id="3b688-126">No se puede combinar con la opción `--global`.</span><span class="sxs-lookup"><span data-stu-id="3b688-126">Can't be combined with the `--global` option.</span></span> <span data-ttu-id="3b688-127">Al omitir `--global` y `--tool-path`, se muestran las herramientas locales.</span><span class="sxs-lookup"><span data-stu-id="3b688-127">Omitting both `--global` and `--tool-path` lists local tools.</span></span>

## <a name="examples"></a><span data-ttu-id="3b688-128">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3b688-128">Examples</span></span>

- **`dotnet tool list -g`**

  <span data-ttu-id="3b688-129">Enumera todas las herramientas globales instaladas para todos los usuarios en su equipo (perfil de usuario actual).</span><span class="sxs-lookup"><span data-stu-id="3b688-129">Lists all global tools installed user-wide on your machine (current user profile).</span></span>

- **`dotnet tool list --tool-path c:\global-tools`**

  <span data-ttu-id="3b688-130">Enumera las herramientas globales de un directorio específico de Windows.</span><span class="sxs-lookup"><span data-stu-id="3b688-130">Lists the global tools from a specific Windows directory.</span></span>

- **`dotnet tool list --tool-path ~/bin`**

  <span data-ttu-id="3b688-131">Enumera las herramientas globales de un directorio específico de Linux/macOS.</span><span class="sxs-lookup"><span data-stu-id="3b688-131">Lists the global tools from a specific Linux/macOS directory.</span></span>

- <span data-ttu-id="3b688-132">**`dotnet tool list`** o **`dotnet tool list --local`**</span><span class="sxs-lookup"><span data-stu-id="3b688-132">**`dotnet tool list`** or **`dotnet tool list --local`**</span></span>

  <span data-ttu-id="3b688-133">Enumera todas las herramientas locales disponibles en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="3b688-133">Lists all local tools available in the current directory.</span></span>

## <a name="see-also"></a><span data-ttu-id="3b688-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b688-134">See also</span></span>

- [<span data-ttu-id="3b688-135">Herramientas de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3b688-135">.NET Core tools</span></span>](global-tools.md)
- [<span data-ttu-id="3b688-136">Tutorial: Instalación y uso de una herramienta global de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3b688-136">Tutorial: Install and use a .NET Core global tool using the .NET Core CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="3b688-137">Tutorial: Instalación y uso de una herramienta local de .NET Core mediante la CLI de .NET Core</span><span class="sxs-lookup"><span data-stu-id="3b688-137">Tutorial: Install and use a .NET Core local tool using the .NET Core CLI</span></span>](local-tools-how-to-use.md)
