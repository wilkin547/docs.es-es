---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: dae1e9f0ca355166d41c11fbafb80c7c9fb29748
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/24/2020
ms.locfileid: "76733202"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="73f65-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="73f65-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="73f65-104">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="73f65-104">Name</span></span>

<span data-ttu-id="73f65-105">`dotnet msbuild`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="73f65-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="73f65-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="73f65-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="73f65-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="73f65-107">Description</span></span>

<span data-ttu-id="73f65-108">El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="73f65-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="73f65-109">El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="73f65-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="73f65-110">Las opciones son las mismas.</span><span class="sxs-lookup"><span data-stu-id="73f65-110">The options are all the same.</span></span> <span data-ttu-id="73f65-111">Para obtener más información sobre las opciones disponibles, vea [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="73f65-111">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="73f65-112">El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="73f65-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="73f65-113">[dotnet build](dotnet-build.md) se usa con más frecuencia para compilar proyectos, pero dado que siempre ejecuta el destino de compilación, puede usar `dotnet msbuild` si no quiere compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="73f65-113">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="73f65-114">Por ejemplo, si hay un destino concreto que quiere ejecutar sin compilar el proyecto, use `dotnet msbuild` y especifique el destino.</span><span class="sxs-lookup"><span data-stu-id="73f65-114">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="73f65-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="73f65-115">Examples</span></span>

* <span data-ttu-id="73f65-116">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="73f65-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="73f65-117">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="73f65-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

* <span data-ttu-id="73f65-118">Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="73f65-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="73f65-119">Visualización del proyecto completo con todos los destinos incluidos en el SDK:</span><span class="sxs-lookup"><span data-stu-id="73f65-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
