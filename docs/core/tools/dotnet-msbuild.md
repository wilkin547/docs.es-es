---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 12/03/2018
ms.openlocfilehash: b83f1272cdd4c5fcdb6b1e34aef7692e9acc01cd
ms.sourcegitcommit: a4b10e1f2a8bb4e8ff902630855474a0c4f1b37a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2019
ms.locfileid: "71117708"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="3fca7-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="3fca7-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="3fca7-104">Name</span><span class="sxs-lookup"><span data-stu-id="3fca7-104">Name</span></span>

<span data-ttu-id="3fca7-105">`dotnet msbuild`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="3fca7-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="3fca7-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="3fca7-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="3fca7-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="3fca7-107">Description</span></span>

<span data-ttu-id="3fca7-108">El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="3fca7-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="3fca7-109">El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de tipo SDK.</span><span class="sxs-lookup"><span data-stu-id="3fca7-109">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style project only.</span></span> <span data-ttu-id="3fca7-110">Las opciones son las mismas.</span><span class="sxs-lookup"><span data-stu-id="3fca7-110">The options are all the same.</span></span> <span data-ttu-id="3fca7-111">Para obtener más información sobre las opciones disponibles, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="3fca7-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="3fca7-112">El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="3fca7-112">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="3fca7-113">`dotnet build` suele utilizase para compilar proyectos, pero `dotnet msbuild` le aporta mayor control.</span><span class="sxs-lookup"><span data-stu-id="3fca7-113">`dotnet build` is more commonly used for building projects, but `dotnet msbuild` gives you more control.</span></span> <span data-ttu-id="3fca7-114">Por ejemplo, si hay un destino concreto que quiere ejecutar (sin ejecutar el destino de compilación), probablemente prefiera usar `dotnet msbuild`.</span><span class="sxs-lookup"><span data-stu-id="3fca7-114">For example, if you have a specific target you want to run (without running the build target), you probably want to use `dotnet msbuild`.</span></span>

## <a name="examples"></a><span data-ttu-id="3fca7-115">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="3fca7-115">Examples</span></span>

* <span data-ttu-id="3fca7-116">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="3fca7-116">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

* <span data-ttu-id="3fca7-117">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="3fca7-117">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -p:Configuration=Release
  ```

* <span data-ttu-id="3fca7-118">Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="3fca7-118">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64
  ```

* <span data-ttu-id="3fca7-119">Visualización del proyecto completo con todos los destinos incluidos en el SDK:</span><span class="sxs-lookup"><span data-stu-id="3fca7-119">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -pp
  ```
