---
title: Comando dotnet msbuild
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
ms.date: 02/14/2020
ms.openlocfilehash: 28a32a460d644d3e22f16b5dd9416222ae466e2e
ms.sourcegitcommit: f38e527623883b92010cf4760246203073e12898
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/20/2020
ms.locfileid: "77503672"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="d25d8-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="d25d8-103">dotnet msbuild</span></span>

<span data-ttu-id="d25d8-104">**Este artículo se aplica a:** ✔️ SDK de .NET Core 2.x y versiones posteriores</span><span class="sxs-lookup"><span data-stu-id="d25d8-104">**This article applies to:** ✔️ .NET Core 2.x SDK and later versions</span></span>

## <a name="name"></a><span data-ttu-id="d25d8-105">NOMBRE</span><span class="sxs-lookup"><span data-stu-id="d25d8-105">Name</span></span>

<span data-ttu-id="d25d8-106">`dotnet msbuild`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="d25d8-106">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="d25d8-107">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="d25d8-107">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="d25d8-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="d25d8-108">Description</span></span>

<span data-ttu-id="d25d8-109">El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="d25d8-109">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="d25d8-110">El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente solo para proyectos de estilo SDK.</span><span class="sxs-lookup"><span data-stu-id="d25d8-110">The command has the exact same capabilities as the existing MSBuild command-line client for SDK-style projects only.</span></span> <span data-ttu-id="d25d8-111">Las opciones son las mismas.</span><span class="sxs-lookup"><span data-stu-id="d25d8-111">The options are all the same.</span></span> <span data-ttu-id="d25d8-112">Para obtener más información sobre las opciones disponibles, vea [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="d25d8-112">For more information about the available options, see the [MSBuild command-line reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

<span data-ttu-id="d25d8-113">El comando [dotnet build](dotnet-build.md) es equivalente al comando `dotnet msbuild -restore -target:Build`.</span><span class="sxs-lookup"><span data-stu-id="d25d8-113">The [dotnet build](dotnet-build.md) command is equivalent to `dotnet msbuild -restore -target:Build`.</span></span> <span data-ttu-id="d25d8-114">[dotnet build](dotnet-build.md) se usa con más frecuencia para compilar proyectos, pero dado que siempre ejecuta el destino de compilación, puede usar `dotnet msbuild` si no quiere compilar el proyecto.</span><span class="sxs-lookup"><span data-stu-id="d25d8-114">[dotnet build](dotnet-build.md) is more commonly used for building projects, but because it always runs the build target, you can use `dotnet msbuild` when you don't want to build the project.</span></span> <span data-ttu-id="d25d8-115">Por ejemplo, si hay un destino concreto que quiere ejecutar sin compilar el proyecto, use `dotnet msbuild` y especifique el destino.</span><span class="sxs-lookup"><span data-stu-id="d25d8-115">For example, if you have a specific target you want to run without building the project, use `dotnet msbuild` and specify the target.</span></span>

## <a name="examples"></a><span data-ttu-id="d25d8-116">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="d25d8-116">Examples</span></span>

- <span data-ttu-id="d25d8-117">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="d25d8-117">Build a project and its dependencies:</span></span>

  ```dotnetcli
  dotnet msbuild
  ```

- <span data-ttu-id="d25d8-118">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="d25d8-118">Build a project and its dependencies using Release configuration:</span></span>

  ```dotnetcli
  dotnet msbuild -property:Configuration=Release
  ```

- <span data-ttu-id="d25d8-119">Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="d25d8-119">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

  ```dotnetcli
  dotnet msbuild -target:Publish -property:RuntimeIdentifiers=osx.10.11-x64
  ```

- <span data-ttu-id="d25d8-120">Visualización del proyecto completo con todos los destinos incluidos en el SDK:</span><span class="sxs-lookup"><span data-stu-id="d25d8-120">See the whole project with all targets included by the SDK:</span></span>

  ```dotnetcli
  dotnet msbuild -preprocess
  ```
