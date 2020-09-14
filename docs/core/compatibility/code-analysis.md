---
title: Cambios importantes en el análisis de código
description: Enumera los cambios importantes en los analizadores de código fuente de .NET.
ms.date: 08/22/2020
ms.openlocfilehash: 8b2b50c5f03a3ca971aefd0f2cf53624dfa82274
ms.sourcegitcommit: e7acba36517134238065e4d50bb4a1cfe47ebd06
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/04/2020
ms.locfileid: "89465597"
---
# <a name="code-analysis-breaking-changes"></a><span data-ttu-id="49188-103">Cambios importantes en el análisis de código</span><span class="sxs-lookup"><span data-stu-id="49188-103">Code analysis breaking changes</span></span>

<span data-ttu-id="49188-104">En esta página se documentan los siguientes cambios importantes:</span><span class="sxs-lookup"><span data-stu-id="49188-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="49188-105">Cambio importante</span><span class="sxs-lookup"><span data-stu-id="49188-105">Breaking change</span></span> | <span data-ttu-id="49188-106">Versión introducida</span><span class="sxs-lookup"><span data-stu-id="49188-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="49188-107">CA1831: Uso de AsSpan o AsMemory en lugar de indizadores basados en intervalos</span><span class="sxs-lookup"><span data-stu-id="49188-107">CA1831: Use AsSpan or AsMemory instead of Range-based indexer</span></span>](#ca1831-use-asspan-or-asmemory-instead-of-range-based-indexer) | <span data-ttu-id="49188-108">5.0</span><span class="sxs-lookup"><span data-stu-id="49188-108">5.0</span></span> |
| [<span data-ttu-id="49188-109">CA2014: No usar stackalloc en los bucles</span><span class="sxs-lookup"><span data-stu-id="49188-109">CA2014: Do not use stackalloc in loops</span></span>](#ca2014-do-not-use-stackalloc-in-loops) | <span data-ttu-id="49188-110">5.0</span><span class="sxs-lookup"><span data-stu-id="49188-110">5.0</span></span> |
| [<span data-ttu-id="49188-111">CA2015: No definir finalizadores para los tipos derivados de MemoryManager\<T></span><span class="sxs-lookup"><span data-stu-id="49188-111">CA2015: Do not define finalizers for types derived from MemoryManager\<T></span></span>](#ca2015-do-not-define-finalizers-for-types-derived-from-memorymanagert) | <span data-ttu-id="49188-112">5.0</span><span class="sxs-lookup"><span data-stu-id="49188-112">5.0</span></span> |
| [<span data-ttu-id="49188-113">CA2247: El argumento para el constructor TaskCompletionSource debe ser el valor TaskCreationOptions</span><span class="sxs-lookup"><span data-stu-id="49188-113">CA2247: Argument to TaskCompletionSource constructor should be TaskCreationOptions value</span></span>](#ca2247-argument-to-taskcompletionsource-constructor-should-be-taskcreationoptions-value) | <span data-ttu-id="49188-114">5.0</span><span class="sxs-lookup"><span data-stu-id="49188-114">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="49188-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="49188-115">.NET 5.0</span></span>

[!INCLUDE [range-based-indexer-on-string](../../../includes/core-changes/codeanalysis/5.0/range-based-indexer-on-string.md)]

***

[!INCLUDE [stackalloc-in-loops](../../../includes/core-changes/codeanalysis/5.0/stackalloc-in-loops.md)]

***

[!INCLUDE [finalizers-for-memorymanager-types](../../../includes/core-changes/codeanalysis/5.0/finalizers-for-memorymanager-types.md)]

***

[!INCLUDE [ctor-arg-should-be-taskcreationoptions](../../../includes/core-changes/codeanalysis/5.0/ctor-arg-should-be-taskcreationoptions.md)]

***
