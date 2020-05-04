---
title: Comando dotnet add reference
description: El comando dotnet add reference constituye una opción práctica para agregar referencias entre proyectos.
ms.date: 02/14/2020
ms.openlocfilehash: b261e24ed6a9d5bd489d317d2663b1420b5c34ff
ms.sourcegitcommit: c2c1269a81ffdcfc8675bcd9a8505b1a11ffb271
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2020
ms.locfileid: "82158325"
---
# <a name="dotnet-add-reference"></a><span data-ttu-id="21aed-103">dotnet add reference</span><span class="sxs-lookup"><span data-stu-id="21aed-103">dotnet add reference</span></span>

<span data-ttu-id="21aed-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="21aed-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="21aed-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="21aed-105">Name</span></span>

<span data-ttu-id="21aed-106">`dotnet add reference` Agrega referencias entre proyectos (P2P) .</span><span class="sxs-lookup"><span data-stu-id="21aed-106">`dotnet add reference` - Adds project-to-project (P2P) references.</span></span>

## <a name="synopsis"></a><span data-ttu-id="21aed-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="21aed-107">Synopsis</span></span>

```dotnetcli
dotnet add [<PROJECT>] reference [-f|--framework <FRAMEWORK>]
     [--interactive] <PROJECT_REFERENCES>

dotnet add reference -h|--help
```

## <a name="description"></a><span data-ttu-id="21aed-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="21aed-108">Description</span></span>

<span data-ttu-id="21aed-109">El comando `dotnet add reference` constituye una opción práctica para agregar referencias de proyecto a un proyecto.</span><span class="sxs-lookup"><span data-stu-id="21aed-109">The `dotnet add reference` command provides a convenient option to add project references to a project.</span></span> <span data-ttu-id="21aed-110">Después de ejecutar el comando, los elementos `<ProjectReference>` se agregan al archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="21aed-110">After running the command, the `<ProjectReference>` elements are added to the project file.</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="app.csproj" />
  <ProjectReference Include="..\lib2\lib2.csproj" />
  <ProjectReference Include="..\lib1\lib1.csproj" />
</ItemGroup>
```

## <a name="arguments"></a><span data-ttu-id="21aed-111">Argumentos</span><span class="sxs-lookup"><span data-stu-id="21aed-111">Arguments</span></span>

- **`PROJECT`**

  <span data-ttu-id="21aed-112">Especifica el archivo del proyecto.</span><span class="sxs-lookup"><span data-stu-id="21aed-112">Specifies the project file.</span></span> <span data-ttu-id="21aed-113">Si no se especifica, el comando busca uno en el directorio actual.</span><span class="sxs-lookup"><span data-stu-id="21aed-113">If not specified, the command searches the current directory for one.</span></span>

- **`PROJECT_REFERENCES`**

  <span data-ttu-id="21aed-114">Referencias entre proyectos (P2P) que se van a agregar.</span><span class="sxs-lookup"><span data-stu-id="21aed-114">Project-to-project (P2P) references to add.</span></span> <span data-ttu-id="21aed-115">Especifique uno o más proyectos.</span><span class="sxs-lookup"><span data-stu-id="21aed-115">Specify one or more projects.</span></span> <span data-ttu-id="21aed-116">[El patrón glob](https://en.wikipedia.org/wiki/Glob_(programming)) se admite en sistemas basados en Unix/Linux.</span><span class="sxs-lookup"><span data-stu-id="21aed-116">[Glob patterns](https://en.wikipedia.org/wiki/Glob_(programming)) are supported on Unix/Linux-based systems.</span></span>

## <a name="options"></a><span data-ttu-id="21aed-117">Opciones</span><span class="sxs-lookup"><span data-stu-id="21aed-117">Options</span></span>

- **`-f|--framework <FRAMEWORK>`**

  <span data-ttu-id="21aed-118">Agrega referencias de proyecto solo cuando apunta a un [marco](../../standard/frameworks.md) específico con el formato TFM.</span><span class="sxs-lookup"><span data-stu-id="21aed-118">Adds project references only when targeting a specific [framework](../../standard/frameworks.md) using the TFM format.</span></span>

- **`-h|--help`**

  <span data-ttu-id="21aed-119">Imprime una corta ayuda para el comando.</span><span class="sxs-lookup"><span data-stu-id="21aed-119">Prints out a short help for the command.</span></span>

- **`--interactive`**

  <span data-ttu-id="21aed-120">Permite que el comando se detenga y espere la entrada o acción del usuario (se suele utilizar para completar la autenticación).</span><span class="sxs-lookup"><span data-stu-id="21aed-120">Allows the command to stop and wait for user input or action (typically used to complete authentication).</span></span> <span data-ttu-id="21aed-121">Disponible desde el SDK de .NET Core 3.0.</span><span class="sxs-lookup"><span data-stu-id="21aed-121">Available since .NET Core 3.0 SDK.</span></span>

## <a name="examples"></a><span data-ttu-id="21aed-122">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="21aed-122">Examples</span></span>

- <span data-ttu-id="21aed-123">Agregar una referencia de proyecto:</span><span class="sxs-lookup"><span data-stu-id="21aed-123">Add a project reference:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference lib/lib.csproj
  ```

- <span data-ttu-id="21aed-124">Agregar varias referencias de proyecto al proyecto en el directorio actual:</span><span class="sxs-lookup"><span data-stu-id="21aed-124">Add multiple project references to the project in the current directory:</span></span>

  ```dotnetcli
  dotnet add reference lib1/lib1.csproj lib2/lib2.csproj
  ```

- <span data-ttu-id="21aed-125">Agregar varias referencias de proyecto usando el patrón global en Linux/Unix:</span><span class="sxs-lookup"><span data-stu-id="21aed-125">Add multiple project references using a globbing pattern on Linux/Unix:</span></span>

  ```dotnetcli
  dotnet add app/app.csproj reference **/*.csproj
  ```
