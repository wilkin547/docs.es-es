---
title: 'Comando dotnet msbuild: CLI de .NET Core'
description: "El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 96e4eac528abad2b336a979a98c9be2bee5d17ee
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="a8db9-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="a8db9-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="a8db9-104">Name</span><span class="sxs-lookup"><span data-stu-id="a8db9-104">Name</span></span>

<span data-ttu-id="a8db9-105">`dotnet msbuild`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="a8db9-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="a8db9-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="a8db9-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="a8db9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a8db9-107">Description</span></span>

<span data-ttu-id="a8db9-108">El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="a8db9-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="a8db9-109">El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente.</span><span class="sxs-lookup"><span data-stu-id="a8db9-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="a8db9-110">Las opciones son las mismas.</span><span class="sxs-lookup"><span data-stu-id="a8db9-110">The options are all the same.</span></span> <span data-ttu-id="a8db9-111">Use la [referencia de línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference) para más información sobre las opciones disponibles.</span><span class="sxs-lookup"><span data-stu-id="a8db9-111">Use the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference) to obtain information on the available options.</span></span> 

## <a name="examples"></a><span data-ttu-id="a8db9-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="a8db9-112">Examples</span></span>

<span data-ttu-id="a8db9-113">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="a8db9-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="a8db9-114">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="a8db9-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild /p:Configuration=Release`

<span data-ttu-id="a8db9-115">Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="a8db9-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild /t:Publish /p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="a8db9-116">Visualización del proyecto completo con todos los destinos incluidos en el SDK:</span><span class="sxs-lookup"><span data-stu-id="a8db9-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild /pp`
