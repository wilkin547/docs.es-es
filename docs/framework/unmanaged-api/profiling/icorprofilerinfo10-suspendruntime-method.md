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
ms.openlocfilehash: 74300a12d000565a63cd7ea862c759d47b87bbe1
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69665693"
---
# <a name="icorprofilerinfo10suspendruntime-method"></a><span data-ttu-id="3e2ee-102">ICorProfilerInfo10:: SuspendRuntime (método)</span><span class="sxs-lookup"><span data-stu-id="3e2ee-102">ICorProfilerInfo10::SuspendRuntime Method</span></span>

<span data-ttu-id="3e2ee-103">Suspende el tiempo de ejecución sin realizar un GC.</span><span class="sxs-lookup"><span data-stu-id="3e2ee-103">Suspends the runtime without performing a GC.</span></span>

## <a name="syntax"></a><span data-ttu-id="3e2ee-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e2ee-104">Syntax</span></span>

```cpp
HRESULT SuspendRuntime();
```

## <a name="requirements"></a><span data-ttu-id="3e2ee-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e2ee-105">Requirements</span></span>

<span data-ttu-id="3e2ee-106">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="3e2ee-106">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="3e2ee-107">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="3e2ee-107">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="3e2ee-108">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e2ee-108">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="3e2ee-109">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e2ee-109">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3e2ee-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="3e2ee-110">See also</span></span>

- [<span data-ttu-id="3e2ee-111">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="3e2ee-111">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
