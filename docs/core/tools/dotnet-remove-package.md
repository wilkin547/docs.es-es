---
title: Comando dotnet remove package
description: El comando dotnet remove package constituye una opción práctica para quitar la referencia de paquete NuGet de un proyecto.
ms.date: 02/14/2020
ms.openlocfilehash: fc74ac1364a0ed027b83dab270d382f238dc00e5
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/29/2020
ms.locfileid: "81463451"
---
# <a name="dotnet-remove-package"></a><span data-ttu-id="9c9b0-103">dotnet remove package</span><span class="sxs-lookup"><span data-stu-id="9c9b0-103">dotnet remove package</span></span>

<span data-ttu-id="9c9b0-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="9c9b0-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="9c9b0-105">Name</span><span class="sxs-lookup"><span data-stu-id="9c9b0-105">Name</span></span>

<span data-ttu-id="9c9b0-106">`dotnet remove package`: quita la referencia de paquete de un archivo de proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-106">`dotnet remove package` - Removes package reference from a project file.</span></span>

## <a name="synopsis"></a><span data-ttu-id="9c9b0-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="9c9b0-107">Synopsis</span></span>

```dotnetcli
dotnet remove [<PROJECT>] package <PACKAGE_NAME>

dotnet remove package -h|--help
```

## <a name="description"></a><span data-ttu-id="9c9b0-108">Description</span><span class="sxs-lookup"><span data-stu-id="9c9b0-108">Description</span></span>

<span data-ttu-id="9c9b0-109">El comando `dotnet remove package` constituye una opción práctica para quitar una referencia de paquete NuGet de un proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-109">The `dotnet remove package` command provides a convenient option to remove a NuGet package reference from a project.</span></span>

## <a name="arguments"></a><span data-ttu-id="9c9b0-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="9c9b0-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="9c9b0-111">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-111">Specifies the project file.</span></span> <span data-ttu-id="9c9b0-112">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-112">If not specified, the command searches the current directory for one.</span></span>

`PACKAGE_NAME`

<span data-ttu-id="9c9b0-113">La referencia de paquete que hay que quitar.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-113">The package reference to remove.</span></span>

## <a name="options"></a><span data-ttu-id="9c9b0-114">Opciones</span><span class="sxs-lookup"><span data-stu-id="9c9b0-114">Options</span></span>

- **`-h|--help`**

  <span data-ttu-id="9c9b0-115">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="9c9b0-115">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="9c9b0-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9c9b0-116">Examples</span></span>

- <span data-ttu-id="9c9b0-117">Quite el paquete NuGet `Newtonsoft.Json` de un proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="9c9b0-117">Remove `Newtonsoft.Json` NuGet package from a project in the current directory:</span></span>

  ```dotnetcli
  dotnet remove package Newtonsoft.Json
  ```
