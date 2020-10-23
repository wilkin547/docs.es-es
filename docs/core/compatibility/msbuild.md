---
title: Cambios importantes de MSBuild
description: Se enumeran los cambios importantes de MSBuild en .NET Core.
ms.date: 02/10/2020
ms.openlocfilehash: 9b0fba30c8955a6099bde0dc95b4df65a151d9e6
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92159498"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="17c86-103">Cambios importantes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="17c86-103">MSBuild breaking changes</span></span>

<span data-ttu-id="17c86-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="17c86-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="17c86-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="17c86-105">Breaking change</span></span> | <span data-ttu-id="17c86-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="17c86-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="17c86-107">Cambio de TargetFramework de netcoreapp a net</span><span class="sxs-lookup"><span data-stu-id="17c86-107">TargetFramework change from netcoreapp to net</span></span>](#targetframework-change-from-netcoreapp-to-net) | <span data-ttu-id="17c86-108">5.0</span><span class="sxs-lookup"><span data-stu-id="17c86-108">5.0</span></span> |
| [<span data-ttu-id="17c86-109">Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino</span><span class="sxs-lookup"><span data-stu-id="17c86-109">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="17c86-110">5.0</span><span class="sxs-lookup"><span data-stu-id="17c86-110">5.0</span></span> |
| [<span data-ttu-id="17c86-111">Cambio de comportamiento de PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="17c86-111">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="17c86-112">5.0</span><span class="sxs-lookup"><span data-stu-id="17c86-112">5.0</span></span> |
| [<span data-ttu-id="17c86-113">Los archivos Directory.Packages.props se importan de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="17c86-113">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="17c86-114">5.0</span><span class="sxs-lookup"><span data-stu-id="17c86-114">5.0</span></span> |
| [<span data-ttu-id="17c86-115">Cambio de nombre de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="17c86-115">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="17c86-116">3.0</span><span class="sxs-lookup"><span data-stu-id="17c86-116">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="17c86-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="17c86-117">.NET 5.0</span></span>

[!INCLUDE [targetframework-name-change](../../../includes/core-changes/msbuild/5.0/targetframework-name-change.md)]

***

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="17c86-118">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="17c86-118">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
