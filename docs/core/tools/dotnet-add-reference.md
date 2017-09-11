---
title: 'Comando dotnet-add reference: CLI de .NET Core'
description: "El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos."
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.translationtype: HT
ms.sourcegitcommit: a19ab54a6cc44bd7acd1e40a4ca94da52bf14297
ms.openlocfilehash: 18e3ce22c1b9a4506b2690262d8d0c4e13a58ed1
ms.contentlocale: es-es
ms.lasthandoff: 08/14/2017

---
# <a name="dotnet-add-reference"></a><span data-ttu-id="37ccf-103">dotnet-add reference</span><span class="sxs-lookup"><span data-stu-id="37ccf-103">dotnet-add reference</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="37ccf-104">Name</span><span class="sxs-lookup"><span data-stu-id="37ccf-104">Name</span></span>

<span data-ttu-id="37ccf-105">`dotnet add reference` Agrega referencias entre proyectos (P2P) .</span><span class="sxs-lookup"><span data-stu-id="37ccf-105">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="37ccf-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="37ccf-106">Synopsis</span></span>

`dotnet add [<PROJECT>] reference [-f|--framework] <PROJECT_REFERENCES> [-h|--help]`

## <a name="description"></a><span data-ttu-id="37ccf-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="37ccf-107">Description</span></span>

<span data-ttu-id="37ccf-108">El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="37ccf-108">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="37ccf-109">Después de ejecutar el comando, los elementos [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) se agregan al archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="37ccf-109">After running the command, the [`<ProjectReference>`](/visualstudio/msbuild/common-msbuild-project-items) elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="37ccf-110">Argumentos</span><span class="sxs-lookup"><span data-stu-id="37ccf-110">Arguments</span></span>

`PROJECT`

<span data-ttu-id="37ccf-111">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="37ccf-111">Specifies the project file.</span></span> <span data-ttu-id="37ccf-112">Si no se especifica, el comando buscará uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="37ccf-112">If not specified, the command will search the current directory for one.</span></span>

`PROJECT_REFERENCES`

<span data-ttu-id="37ccf-113">Referencias entre proyectos (P2P) que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="37ccf-113">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="37ccf-114">Especifique uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="37ccf-114">Specify one or more projects.</span></span> <span data-ttu-id="37ccf-115">[El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="37ccf-115">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="37ccf-116">Opciones</span><span class="sxs-lookup"><span data-stu-id="37ccf-116">Options</span></span>

`-h|--help`

<span data-ttu-id="37ccf-117">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="37ccf-117">Prints out a short help for the command.</span></span>

`-f|--framework <FRAMEWORK>`

<span data-ttu-id="37ccf-118">Agrega referencias de proyecto solo cuando apunta a un[marco](../../standard/frameworks.md) específico.</span><span class="sxs-lookup"><span data-stu-id="37ccf-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md).</span></span>

## <a name="examples"></a><span data-ttu-id="37ccf-119">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="37ccf-119">Examples</span></span>

<span data-ttu-id="37ccf-120">Agregar una referencia de proyecto:</span><span class="sxs-lookup"><span data-stu-id="37ccf-120">Add a project reference:</span></span>

`dotnet add app/app.csproj reference lib/lib.csproj`

<span data-ttu-id="37ccf-121">Agregar varias referencias de proyecto:</span><span class="sxs-lookup"><span data-stu-id="37ccf-121">Add multiple project references:</span></span>

`dotnet add reference lib1/lib1.csproj lib2/lib2.csproj`

<span data-ttu-id="37ccf-122">Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="37ccf-122">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

`dotnet add app/app.csproj reference **/*.csproj`
