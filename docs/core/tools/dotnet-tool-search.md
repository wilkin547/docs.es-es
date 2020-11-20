---
title: Comando dotnet tool search
description: El comando dotnet tool search busca las herramientas de .NET publicadas en NuGet.org.
ms.date: 11/11/2020
ms.openlocfilehash: e0289e651ec4a439c791c8c948bef2d85d9c3794
ms.sourcegitcommit: b201d177e01480a139622f3bf8facd367657a472
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2020
ms.locfileid: "94634147"
---
# <a name="dotnet-tool-search"></a><span data-ttu-id="d70e5-103">dotnet tool search</span><span class="sxs-lookup"><span data-stu-id="d70e5-103">dotnet tool search</span></span>

<span data-ttu-id="d70e5-104">**Este artículo se aplica a:** ✔️ SDK de .NET 5.0 y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d70e5-104">**This article applies to:** ✔️ .NET 5.0 SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d70e5-105">Name</span><span class="sxs-lookup"><span data-stu-id="d70e5-105">Name</span></span>

<span data-ttu-id="d70e5-106">`dotnet tool search`: busca todas las [herramientas de .NET](global-tools.md) publicadas en NuGet.</span><span class="sxs-lookup"><span data-stu-id="d70e5-106">`dotnet tool search` - Searches all [.NET tools](global-tools.md) that are published to NuGet.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d70e5-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d70e5-107">Synopsis</span></span>

```dotnetcli
dotnet tool search [--detail]  [--prerelease]
    [--skip <NUMBER>] [--take <NUMBER>] <SEARCH TERM>

dotnet tool search -h|--help
```

## <a name="description"></a><span data-ttu-id="d70e5-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d70e5-108">Description</span></span>

<span data-ttu-id="d70e5-109">El comando `dotnet tool search` proporciona una manera de buscar en NuGet las herramientas que se pueden usar como herramientas globales, de ruta de acceso de herramientas o locales de .NET.</span><span class="sxs-lookup"><span data-stu-id="d70e5-109">The `dotnet tool search` command provides a way for you to search NuGet for tools that can be used as .NET global, tool-path, or local tools.</span></span> <span data-ttu-id="d70e5-110">El comando busca en los nombres de herramienta y los metadatos, como títulos, descripciones y etiquetas.</span><span class="sxs-lookup"><span data-stu-id="d70e5-110">The command searches the tool names and metadata such as titles, descriptions, and tags.</span></span>

<span data-ttu-id="d70e5-111">El comando usa la [API Search de NuGet](/nuget/api/search-query-service-resource#search-for-packages).</span><span class="sxs-lookup"><span data-stu-id="d70e5-111">The command uses the [NuGet Search API](/nuget/api/search-query-service-resource#search-for-packages).</span></span> <span data-ttu-id="d70e5-112">Filtra por `packageType=dotnettool` para seleccionar solo los paquetes de herramientas de .NET.</span><span class="sxs-lookup"><span data-stu-id="d70e5-112">It filters on `packageType=dotnettool` to select only .NET tool packages.</span></span>

## <a name="options"></a><span data-ttu-id="d70e5-113">Opciones</span><span class="sxs-lookup"><span data-stu-id="d70e5-113">Options</span></span>

- **`--detail`**

  <span data-ttu-id="d70e5-114">Muestra los resultados detallados de la consulta.</span><span class="sxs-lookup"><span data-stu-id="d70e5-114">Shows detailed results from the query.</span></span>

- **`--prerelease`**

  <span data-ttu-id="d70e5-115">Incluye paquetes en versión preliminar.</span><span class="sxs-lookup"><span data-stu-id="d70e5-115">Includes pre-release packages.</span></span>

- **`--skip <NUMBER>`**

  <span data-ttu-id="d70e5-116">Especifica el número de resultados de la consulta que se omiten.</span><span class="sxs-lookup"><span data-stu-id="d70e5-116">Specifies the number of query results to skip.</span></span> <span data-ttu-id="d70e5-117">Se usa para la paginación.</span><span class="sxs-lookup"><span data-stu-id="d70e5-117">Used for pagination.</span></span>

- **`--take <NUMBER>`**

  <span data-ttu-id="d70e5-118">Especifica el número de resultados de la consulta que se muestran.</span><span class="sxs-lookup"><span data-stu-id="d70e5-118">Specifies the number of query results to show.</span></span> <span data-ttu-id="d70e5-119">Se usa para la paginación.</span><span class="sxs-lookup"><span data-stu-id="d70e5-119">Used for pagination.</span></span>

- **`-h|--help`**

  <span data-ttu-id="d70e5-120">Muestra la ayuda de la línea de comandos.</span><span class="sxs-lookup"><span data-stu-id="d70e5-120">Shows command-line help.</span></span>

## <a name="examples"></a><span data-ttu-id="d70e5-121">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d70e5-121">Examples</span></span>

- <span data-ttu-id="d70e5-122">Busque herramientas de .NET en NuGet.org que incluyan "formato" en el nombre o la descripción del paquete:</span><span class="sxs-lookup"><span data-stu-id="d70e5-122">Search NuGet.org for .NET tools that have "format" in their package name or description:</span></span>

  ```dotnetcli
  dotnet tool search format
  ```

  <span data-ttu-id="d70e5-123">La salida se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d70e5-123">The output looks like the following example:</span></span>

  ```output
  Package ID                              Latest Version      Authors                                                                     Downloads      Verified
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------
  dotnet-format                           4.1.131201          Microsoft                                                                   496746
  bsoa.generator                          1.0.0               Microsoft                                                                   533
  ```

- <span data-ttu-id="d70e5-124">Busque herramientas de .NET en NuGet.org que incluyan "formato" en el nombre o los metadatos del paquete, muestre solo el primer resultado y muestre una vista detallada.</span><span class="sxs-lookup"><span data-stu-id="d70e5-124">Search NuGet.org for .NET tools that have "format" in their package name or metadata, show only the first result, and show a detailed view.</span></span>

  ```dotnetcli
  dotnet tool search format --take 1 --detail
  ```

  <span data-ttu-id="d70e5-125">La salida se parece al ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="d70e5-125">The output looks like the following example:</span></span>

  ```output
  ----------------
  dotnet-format
  Latest Version: 4.1.131201
  Authors: Microsoft
  Tags:
  Downloads: 496746
  Verified: False
  Description: Command line tool for formatting C# and Visual Basic code files based on .editorconfig settings.
  Versions:
          3.0.2 Downloads: 1973
          3.0.4 Downloads: 9064
          3.1.37601 Downloads: 114730
          3.2.107702 Downloads: 13423
          3.3.111304 Downloads: 131195
          4.0.130203 Downloads: 78610
          4.1.131201 Downloads: 145927
  ```

## <a name="see-also"></a><span data-ttu-id="d70e5-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d70e5-126">See also</span></span>

- [<span data-ttu-id="d70e5-127">Herramientas de .NET</span><span class="sxs-lookup"><span data-stu-id="d70e5-127">.NET tools</span></span>](global-tools.md)
- [<span data-ttu-id="d70e5-128">Tutorial: Instalación y uso de una herramienta global de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="d70e5-128">Tutorial: Install and use a .NET global tool using the .NET CLI</span></span>](global-tools-how-to-use.md)
- [<span data-ttu-id="d70e5-129">Tutorial: Instalación y uso de una herramienta local de .NET mediante la CLI de .NET</span><span class="sxs-lookup"><span data-stu-id="d70e5-129">Tutorial: Install and use a .NET local tool using the .NET CLI</span></span>](local-tools-how-to-use.md)
