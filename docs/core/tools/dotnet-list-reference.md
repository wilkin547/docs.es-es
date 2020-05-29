---
title: Comando dotnet list reference
description: El comando dotnet list reference constituye una opción práctica para enumerar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: b9b34c17102c6218f3d99f6e2620e99f70140284
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83802761"
---
# <a name="dotnet-list-reference"></a><span data-ttu-id="b7f9d-103">dotnet list reference</span><span class="sxs-lookup"><span data-stu-id="b7f9d-103">dotnet list reference</span></span>

<span data-ttu-id="b7f9d-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="b7f9d-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="b7f9d-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="b7f9d-105">Name</span></span>

<span data-ttu-id="b7f9d-106">`dotnet list reference`: enumera las referencias entre proyectos.</span><span class="sxs-lookup"><span data-stu-id="b7f9d-106">`dotnet list reference` - Lists project-to-project references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b7f9d-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b7f9d-107">Synopsis</span></span>

```dotnetcli
dotnet list [<PROJECT>] reference

dotnet list -h|--help
```

## <a name="description"></a><span data-ttu-id="b7f9d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="b7f9d-108">Description</span></span>

<span data-ttu-id="b7f9d-109">El comando `dotnet list reference` constituye una opción práctica para enumerar las referencias de proyecto de un proyecto concreto.</span><span class="sxs-lookup"><span data-stu-id="b7f9d-109">The `dotnet list reference` command provides a convenient option to list project references for a given project.</span></span>

## <a name="arguments"></a><span data-ttu-id="b7f9d-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="b7f9d-110">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="b7f9d-111">El archivo del proyecto sobre el que actuar.</span><span class="sxs-lookup"><span data-stu-id="b7f9d-111">The project file to operate on.</span></span> <span data-ttu-id="b7f9d-112">Si no se especifica un archivo, el comando buscará uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="b7f9d-112">If a file is not specified, the command will search the current directory for one.</span></span>

## <a name="options"></a><span data-ttu-id="b7f9d-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="b7f9d-113">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="b7f9d-114">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="b7f9d-114">Prints out a short help for the command.</span></span>

## <a name="examples"></a><span data-ttu-id="b7f9d-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b7f9d-115">Examples</span></span>

* <span data-ttu-id="b7f9d-116">Enumerar las referencias del proyecto para el proyecto especificado:</span><span class="sxs-lookup"><span data-stu-id="b7f9d-116">List the project references for the specified project:</span></span>

  ```dotnetcli
  dotnet list app/app.csproj reference
  ```

* <span data-ttu-id="b7f9d-117">Enumerar las referencias del proyecto para el proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="b7f9d-117">List the project references for the project in the current directory:</span></span>

  ```dotnetcli
  dotnet list reference
  ```
