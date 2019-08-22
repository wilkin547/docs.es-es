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
ms.openlocfilehash: ac193b6b78434245b8f11a4f627b4e1992feb8a7
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/21/2019
ms.locfileid: "69661272"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="a8b60-102">ICorProfilerInfo10:: EnumerateObjectReferences (método)</span><span class="sxs-lookup"><span data-stu-id="a8b60-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>

<span data-ttu-id="a8b60-103">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="a8b60-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>

## <a name="syntax"></a><span data-ttu-id="a8b60-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a8b60-104">Syntax</span></span>

```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```

#### <a name="parameters"></a><span data-ttu-id="a8b60-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a8b60-105">Parameters</span></span>

`objectId` \
<span data-ttu-id="a8b60-106">de Objeto en el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="a8b60-106">[in] The object to enumerate references on.</span></span>

`callback` \
<span data-ttu-id="a8b60-107">de Función a la que se llamará con las referencias para el objeto.</span><span class="sxs-lookup"><span data-stu-id="a8b60-107">[in] The function that will be called with the references for the object.</span></span>

`clientData` \
<span data-ttu-id="a8b60-108">de Datos proporcionados por el generador de perfiles `callback` que se van a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="a8b60-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>

## <a name="remarks"></a><span data-ttu-id="a8b60-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a8b60-109">Remarks</span></span>

<span data-ttu-id="a8b60-110">El `EnumerateObjectReferences` método es similar a [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.</span><span class="sxs-lookup"><span data-stu-id="a8b60-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>

## <a name="requirements"></a><span data-ttu-id="a8b60-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a8b60-111">Requirements</span></span>

<span data-ttu-id="a8b60-112">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="a8b60-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>

<span data-ttu-id="a8b60-113">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="a8b60-113">**Header:** CorProf.idl, CorProf.h</span></span>

<span data-ttu-id="a8b60-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a8b60-114">**Library:** CorGuids.lib</span></span>

<span data-ttu-id="a8b60-115">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a8b60-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a8b60-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8b60-116">See also</span></span>

- [<span data-ttu-id="a8b60-117">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="a8b60-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)
