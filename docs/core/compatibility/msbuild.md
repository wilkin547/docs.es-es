---
title: Cambios importantes de MSBuild
description: Se enumeran los cambios importantes de MSBuild en .NET Core 2.1 - 3.1.
ms.date: 02/22/2021
ms.openlocfilehash: 03fcd9807a83c4f679dc659b009c857e351b9b2d
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102105648"
---
# <a name="msbuild-breaking-changes-in-net-core-21---31"></a><span data-ttu-id="7e701-103">Cambios importantes de MSBuild en .NET Core 2.1 - 3.1</span><span class="sxs-lookup"><span data-stu-id="7e701-103">MSBuild breaking changes in .NET Core 2.1 - 3.1</span></span>

<span data-ttu-id="7e701-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="7e701-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="7e701-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="7e701-105">Breaking change</span></span> | <span data-ttu-id="7e701-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="7e701-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="7e701-107">Las compilaciones en tiempo de diseño solo devuelven referencias de paquete de nivel superior</span><span class="sxs-lookup"><span data-stu-id="7e701-107">Design-time builds only return top-level package references</span></span>](#design-time-builds-only-return-top-level-package-references) | <span data-ttu-id="7e701-108">3.1</span><span class="sxs-lookup"><span data-stu-id="7e701-108">3.1</span></span> |
| [<span data-ttu-id="7e701-109">Cambio de nombre de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="7e701-109">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="7e701-110">3.0</span><span class="sxs-lookup"><span data-stu-id="7e701-110">3.0</span></span> |
| [<span data-ttu-id="7e701-111">Herramientas de proyecto ahora incluidas en el SDK</span><span class="sxs-lookup"><span data-stu-id="7e701-111">Project tools now included in SDK</span></span>](#project-tools-now-included-in-sdk) | <span data-ttu-id="7e701-112">2.1</span><span class="sxs-lookup"><span data-stu-id="7e701-112">2.1</span></span> |

## <a name="net-core-31"></a><span data-ttu-id="7e701-113">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="7e701-113">.NET Core 3.1</span></span>

[!INCLUDE [design-time-builds-return-top-level-package-refs](../../../includes/core-changes/msbuild/3.1/design-time-builds-return-top-level-package-refs.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="7e701-114">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="7e701-114">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](../../../includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***

## <a name="net-core-21"></a><span data-ttu-id="7e701-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="7e701-115">.NET Core 2.1</span></span>

[!INCLUDE [DotNetCliToolReference project elements removed for bundled tools](../../../includes/core-changes/msbuild/2.1/dotnetclitoolreference.md)]

***
