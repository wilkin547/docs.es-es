---
title: ICorProfilerInfo10::EnumerateObjectReferences
ms.date: 08/06/2019
dev_langs:
- cpp
api_name:
- ICorProfilerInfo10.EnumerateObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
author: davmason
ms.author: davmason
ms.openlocfilehash: 7fd62e0d3d9173f3b75882131e57126075c0677f
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76863314"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="18ecd-102">ICorProfilerInfo10:: EnumerateObjectReferences (método)</span><span class="sxs-lookup"><span data-stu-id="18ecd-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="18ecd-103">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="18ecd-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="18ecd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18ecd-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="18ecd-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="18ecd-105">Parameters</span></span>

- `objectId`

  <span data-ttu-id="18ecd-106">\[en] el objeto en el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="18ecd-106">\[in] The object to enumerate references on.</span></span>

- `callback`

  <span data-ttu-id="18ecd-107">\[en] la función a la que se llamará con las referencias para el objeto.</span><span class="sxs-lookup"><span data-stu-id="18ecd-107">\[in] The function that will be called with the references for the object.</span></span>

- `clientData`

  <span data-ttu-id="18ecd-108">\[en] datos proporcionados por el generador de perfiles que se van a pasar a la función `callback`.</span><span class="sxs-lookup"><span data-stu-id="18ecd-108">\[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="18ecd-109">Notas</span><span class="sxs-lookup"><span data-stu-id="18ecd-109">Remarks</span></span>

<span data-ttu-id="18ecd-110">El método `EnumerateObjectReferences` es similar a [ObjectReferences](icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.</span><span class="sxs-lookup"><span data-stu-id="18ecd-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="18ecd-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="18ecd-111">Requirements</span></span>

<span data-ttu-id="18ecd-112">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="18ecd-112">**Platforms:** See [.NET Core supported operating systems](../../../core/install/dependencies.md?tabs=netcore30&pivots=os-windows).</span></span>

<span data-ttu-id="18ecd-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18ecd-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="18ecd-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18ecd-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="18ecd-115">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18ecd-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="18ecd-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="18ecd-116">See also</span></span>

- [<span data-ttu-id="18ecd-117">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="18ecd-117">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
