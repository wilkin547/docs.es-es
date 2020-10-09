---
title: Cambios importantes de MSBuild
description: Se enumeran los cambios importantes de MSBuild en .NET Core.
ms.date: 02/10/2020
ms.openlocfilehash: b57c70d21e061c59f26b11a025d4d05ce3b8ca99
ms.sourcegitcommit: 4d45bda8cd9558ea8af4be591e3d5a29360c1ece
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/02/2020
ms.locfileid: "91654747"
---
# <a name="msbuild-breaking-changes"></a><span data-ttu-id="5e676-103">Cambios importantes de MSBuild</span><span class="sxs-lookup"><span data-stu-id="5e676-103">MSBuild breaking changes</span></span>

<span data-ttu-id="5e676-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="5e676-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="5e676-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="5e676-105">Breaking change</span></span> | <span data-ttu-id="5e676-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="5e676-106">Version introduced</span></span> |
| - | - |
| [<span data-ttu-id="5e676-107">Símbolo de preprocesador de NETCOREAPP3_1 no definido al establecer .NET 5 como destino</span><span class="sxs-lookup"><span data-stu-id="5e676-107">NETCOREAPP3_1 preprocessor symbol is not defined when targeting .NET 5</span></span>](#netcoreapp3_1-preprocessor-symbol-is-not-defined-when-targeting-net-5) | <span data-ttu-id="5e676-108">5.0</span><span class="sxs-lookup"><span data-stu-id="5e676-108">5.0</span></span> |
| [<span data-ttu-id="5e676-109">Cambio de comportamiento de PublishDepsFilePath</span><span class="sxs-lookup"><span data-stu-id="5e676-109">PublishDepsFilePath behavior change</span></span>](#publishdepsfilepath-behavior-change) | <span data-ttu-id="5e676-110">5.0</span><span class="sxs-lookup"><span data-stu-id="5e676-110">5.0</span></span> |
| [<span data-ttu-id="5e676-111">Los archivos Directory.Packages.props se importan de forma predeterminada</span><span class="sxs-lookup"><span data-stu-id="5e676-111">Directory.Packages.props files is imported by default</span></span>](#directorypackagesprops-files-is-imported-by-default) | <span data-ttu-id="5e676-112">5.0</span><span class="sxs-lookup"><span data-stu-id="5e676-112">5.0</span></span> |
| [<span data-ttu-id="5e676-113">Cambio de nombre de archivo de manifiesto del recurso</span><span class="sxs-lookup"><span data-stu-id="5e676-113">Resource manifest file name change</span></span>](#resource-manifest-file-name-change) | <span data-ttu-id="5e676-114">3.0</span><span class="sxs-lookup"><span data-stu-id="5e676-114">3.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="5e676-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5e676-115">.NET 5.0</span></span>

[!INCLUDE [netcoreapp3_1-preprocessor-symbol-not-defined](../../../includes/core-changes/msbuild/5.0/netcoreapp3_1-preprocessor-symbol-not-defined.md)]

***

[!INCLUDE [publishdepsfilepath-behavior-change](../../../includes/core-changes/msbuild/5.0/publishdepsfilepath-behavior-change.md)]

***

[!INCLUDE [directory-packages-props-imported-by-default](../../../includes/core-changes/msbuild/5.0/directory-packages-props-imported-by-default.md)]

***

## <a name="net-core-30"></a><span data-ttu-id="5e676-116">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="5e676-116">.NET Core 3.0</span></span>

[!INCLUDE[Resource file names](~/includes/core-changes/msbuild/3.0/resource-manifest-name.md)]

***
