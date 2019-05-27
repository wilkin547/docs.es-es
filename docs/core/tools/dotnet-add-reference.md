---
title: Comando dotnet-add reference
description: El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos.
ms.date: 04/24/2019
ms.openlocfilehash: e90f95527d4f14c7851ccd8d30201daaaaefa2ae
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631941"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="c0e7c-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="c0e7c-103">dotnet-add reference</span></span>

<span data-ttu-id="c0e7c-104">**Este artículo se aplica a: ✓** SDK de .NET Core 1.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="c0e7c-104">**This article applies to: ✓** .NET Core 1.x SDK and later versions</span></span>

<!-- todo: uncomment when all CLI commands are reviewed
[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]
-->

## <a name="name"></a><span data-ttu-id="c0e7c-105">nombre</span><span class="sxs-lookup"><span data-stu-id="c0e7c-105">Name</span></span>

<span data-ttu-id="c0e7c-106">`dotnet add reference` Agrega referencias entre proyectos (P2P) .</span><span class="sxs-lookup"><span data-stu-id="c0e7c-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="c0e7c-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="c0e7c-107">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="c0e7c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0e7c-108">Description</span></span>

<span data-ttu-id="c0e7c-109">El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="c0e7c-110">Después de ejecutar el comando, los elementos [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) se agregan al archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-110">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="c0e7c-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="c0e7c-111">Arguments</span></span>

* **`PROJECT`**

  <span data-ttu-id="c0e7c-112">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-112">Specifies the project file.</span></span> <span data-ttu-id="c0e7c-113">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-113">If not specified, the command searches the current directory for one.</span></span>

* **`PROJECT_REFERENCES`**

  <span data-ttu-id="c0e7c-114">Referencias entre proyectos (P2P) que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="c0e7c-115">Especifique uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-115">Specify one or more projects.</span></span> <span data-ttu-id="c0e7c-116">[El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="c0e7c-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="c0e7c-117">Options</span></span>

* **`-h|--help`**

  <span data-ttu-id="c0e7c-118">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-118">Prints out a short help for the command.</span></span>

* **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="c0e7c-119">Agrega referencias de proyecto solo cuando apunta a un[marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="c0e7c-119">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="c0e7c-120">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="c0e7c-120">Examples</span></span>

* <span data-ttu-id="c0e7c-121">Agregar una referencia de proyecto:</span><span class="sxs-lookup"><span data-stu-id="c0e7c-121">Add a project reference:</span></span>

  ```console
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

* <span data-ttu-id="c0e7c-122">Agregar varias referencias de proyecto al proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="c0e7c-122">Add multiple project references to the project in the current directory:</span></span>

  ```console
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

* <span data-ttu-id="c0e7c-123">Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="c0e7c-123">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```console
  dotnet add app/app.csproj reference **/*.csproj
  ```
