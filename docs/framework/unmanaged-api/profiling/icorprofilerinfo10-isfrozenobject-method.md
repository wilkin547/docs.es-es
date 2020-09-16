---
title: ICorProfilerInfo10::IsFrozenObject
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.IsFrozenObject
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 3755260b885768de6b5b2d6342c0ad590a95caff
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90548675"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="8de9f-102">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="8de9f-102">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="8de9f-103">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8de9f-103">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="8de9f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8de9f-104">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="8de9f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8de9f-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="8de9f-106">\[en] objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="8de9f-106">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="8de9f-107">\[out] un valor de `BOOL` tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="8de9f-107">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="8de9f-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8de9f-108">Requirements</span></span>

<span data-ttu-id="8de9f-109">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="8de9f-109">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="8de9f-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8de9f-110">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="8de9f-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8de9f-111">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="8de9f-112">**Versiones de .net:**[!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8de9f-112">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8de9f-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8de9f-113">See also</span></span>

- [<span data-ttu-id="8de9f-114">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="8de9f-114">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
