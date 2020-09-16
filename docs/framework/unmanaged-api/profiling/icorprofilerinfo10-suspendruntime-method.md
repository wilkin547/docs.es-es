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
ms.openlocfilehash: 121ed0401628193f6e2fe632a124c08aad7bd1b4
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551444"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="6577b-102">ICorProfilerInfo10:: SuspendRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="6577b-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="6577b-103">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="6577b-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="6577b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6577b-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="6577b-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6577b-105">Requirements</span></span>

<span data-ttu-id="6577b-106">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="6577b-106">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="6577b-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6577b-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="6577b-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6577b-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="6577b-109">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6577b-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="6577b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="6577b-110">See also</span></span>

- [<span data-ttu-id="6577b-111">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="6577b-111">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
