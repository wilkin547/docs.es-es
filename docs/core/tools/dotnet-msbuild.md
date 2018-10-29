---
title: 'Comando dotnet msbuild: CLI de .NET Core'
description: El comando dotnet msbuild proporciona acceso a la línea de comandos de MSBuild.
author: mairaw
ms.author: mairaw
ms.date: 05/25/2018
ms.openlocfilehash: 76165590478b0e76d19d546c87e012da4716b6db
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/04/2018
ms.locfileid: "48583728"
---
# <a name="dotnet-msbuild"></a><span data-ttu-id="b4993-103">dotnet msbuild</span><span class="sxs-lookup"><span data-stu-id="b4993-103">dotnet msbuild</span></span>

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a><span data-ttu-id="b4993-104">nombre</span><span class="sxs-lookup"><span data-stu-id="b4993-104">Name</span></span>

<span data-ttu-id="b4993-105">`dotnet msbuild`: compila un proyecto y todas sus dependencias.</span><span class="sxs-lookup"><span data-stu-id="b4993-105">`dotnet msbuild` - Builds a project and all of its dependencies.</span></span>

## <a name="synopsis"></a><span data-ttu-id="b4993-106">Sinopsis</span><span class="sxs-lookup"><span data-stu-id="b4993-106">Synopsis</span></span>

`dotnet msbuild <msbuild_arguments> [-h]`

## <a name="description"></a><span data-ttu-id="b4993-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b4993-107">Description</span></span>

<span data-ttu-id="b4993-108">El comando `dotnet msbuild` permite el acceso a una instancia de MSBuild completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="b4993-108">The `dotnet msbuild` command allows access to a fully functional MSBuild.</span></span>

<span data-ttu-id="b4993-109">El comando tiene exactamente las mismas funcionalidades que el cliente de línea de comandos de MSBuild existente.</span><span class="sxs-lookup"><span data-stu-id="b4993-109">The command has the exact same capabilities as existing MSBuild command-line client.</span></span> <span data-ttu-id="b4993-110">Las opciones son las mismas.</span><span class="sxs-lookup"><span data-stu-id="b4993-110">The options are all the same.</span></span> <span data-ttu-id="b4993-111">Para obtener más información sobre las opciones disponibles, vea la [Referencia de la línea de comandos de MSBuild](/visualstudio/msbuild/msbuild-command-line-reference).</span><span class="sxs-lookup"><span data-stu-id="b4993-111">For more information about the available options, see the [MSBuild Command-Line Reference](/visualstudio/msbuild/msbuild-command-line-reference).</span></span>

## <a name="examples"></a><span data-ttu-id="b4993-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="b4993-112">Examples</span></span>

<span data-ttu-id="b4993-113">Creación de un proyecto y sus dependencias:</span><span class="sxs-lookup"><span data-stu-id="b4993-113">Build a project and its dependencies:</span></span>

`dotnet msbuild`

<span data-ttu-id="b4993-114">Creación de un proyecto y sus dependencias mediante la configuración de lanzamiento:</span><span class="sxs-lookup"><span data-stu-id="b4993-114">Build a project and its dependencies using Release configuration:</span></span>

`dotnet msbuild -p:Configuration=Release`

<span data-ttu-id="b4993-115">Ejecuta el destino de publicación y publica para el RID `osx.10.11-x64`:</span><span class="sxs-lookup"><span data-stu-id="b4993-115">Run the publish target and publish for the `osx.10.11-x64` RID:</span></span>

`dotnet msbuild -t:Publish -p:RuntimeIdentifiers=osx.10.11-x64`

<span data-ttu-id="b4993-116">Visualización del proyecto completo con todos los destinos incluidos en el SDK:</span><span class="sxs-lookup"><span data-stu-id="b4993-116">See the whole project with all targets included by the SDK:</span></span>

`dotnet msbuild -pp`
