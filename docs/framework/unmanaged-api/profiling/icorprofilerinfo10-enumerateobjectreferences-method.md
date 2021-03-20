---
description: 'Más información sobre: ICorProfilerInfo10:: EnumerateObjectReferences (método)'
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
ms.openlocfilehash: bcd374aec2944977a0745177995ba8adf0cce9b7
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759422"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="f3251-103">ICorProfilerInfo10:: EnumerateObjectReferences (método)</span><span class="sxs-lookup"><span data-stu-id="f3251-103">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="f3251-104">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="f3251-104">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="f3251-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3251-105">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

## <a name="parameters"></a><span data-ttu-id="f3251-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3251-106">Parameters</span></span>

<span data-ttu-id="f3251-107">`objectId` de Objeto en el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="f3251-107">`objectId` [in] The object to enumerate references on.</span></span>

<span data-ttu-id="f3251-108">`callback` de Función a la que se llamará con las referencias para el objeto.</span><span class="sxs-lookup"><span data-stu-id="f3251-108">`callback` [in] The function that will be called with the references for the object.</span></span>

<span data-ttu-id="f3251-109">`clientData` de Datos proporcionados por el generador de perfiles que se van a pasar a la `callback` función.</span><span class="sxs-lookup"><span data-stu-id="f3251-109">`clientData` [in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3251-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f3251-110">Remarks</span></span>

<span data-ttu-id="f3251-111">El `EnumerateObjectReferences` método es similar a [ObjectReferences](icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.</span><span class="sxs-lookup"><span data-stu-id="f3251-111">The `EnumerateObjectReferences` method is similar to [ObjectReferences](icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3251-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3251-112">Requirements</span></span>

<span data-ttu-id="f3251-113">**Plataformas:** Consulte [sistemas operativos compatibles con .net Core](../../../core/install/windows.md?pivots=os-windows).</span><span class="sxs-lookup"><span data-stu-id="f3251-113">**Platforms:** See [.NET Core supported operating systems](../../../core/install/windows.md?pivots=os-windows).</span></span>

<span data-ttu-id="f3251-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3251-114">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="f3251-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3251-115">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="f3251-116">**Versiones de .net:**[!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3251-116">**.NET Versions:** [!INCLUDE[net_core_30](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="f3251-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3251-117">See also</span></span>

- [<span data-ttu-id="f3251-118">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="f3251-118">ICorProfilerInfo10 Interface</span></span>](icorprofilerinfo10-interface.md)
