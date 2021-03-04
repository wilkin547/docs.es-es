---
description: 'Más información sobre: ICorProfilerInfo10:: IsFrozenObject (método)'
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
ms.openlocfilehash: 3b47204630056e2797b5cf126bd7c291830cea05
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "102103457"
---
# <a name="icorprofilerinfo10isfrozenobject-method"></a><span data-ttu-id="bf915-103">ICorProfilerInfo10:: IsFrozenObject (método)</span><span class="sxs-lookup"><span data-stu-id="bf915-103">ICorProfilerInfo10::IsFrozenObject Method</span></span>

<span data-ttu-id="bf915-104">Dado un ObjectID, determina si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bf915-104">Given an ObjectID, determines whether the object is in a read-only segment.</span></span>

## <a name="syntax"></a><span data-ttu-id="bf915-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf915-105">Syntax</span></span>

```cpp
HRESULT IsFrozenObject( [in]  ObjectID objectId,
                        [out] BOOL *pbFrozen);
```

## <a name="parameters"></a><span data-ttu-id="bf915-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bf915-106">Parameters</span></span>

- `objectId`

  <span data-ttu-id="bf915-107">\[en] objeto que se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="bf915-107">\[in] The object to examine.</span></span>

- `pbFrozen`

  <span data-ttu-id="bf915-108">\[out] un valor de `BOOL` tipo que indica si el objeto está en un segmento de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="bf915-108">\[out] A `BOOL` indicating if the object is in a read-only segment.</span></span>

## <a name="requirements"></a><span data-ttu-id="bf915-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf915-109">Requirements</span></span>

<span data-ttu-id="bf915-110">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="bf915-110">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="bf915-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf915-111">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="bf915-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf915-112">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="bf915-113">**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf915-113">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="bf915-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="bf915-114">See also</span></span>

- [<span data-ttu-id="bf915-115">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="bf915-115">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
