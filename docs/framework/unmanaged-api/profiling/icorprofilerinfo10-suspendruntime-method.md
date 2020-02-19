---
title: ICorProfilerInfo10::SuspendRuntime
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.SuspendRuntime
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 8d00718579f44a164cd83e2b05d41f70f1c65785
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452154"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="2b650-102">ICorProfilerInfo10:: SuspendRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="2b650-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="2b650-103">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="2b650-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b650-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b650-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="2b650-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b650-105">Requirements</span></span>

<span data-ttu-id="2b650-106">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="2b650-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?pivots=os-windows).</span></span>

<span data-ttu-id="2b650-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="2b650-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="2b650-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2b650-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="2b650-109">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b650-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="2b650-110">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b650-110">See also</span></span>

- [<span data-ttu-id="2b650-111">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="2b650-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
