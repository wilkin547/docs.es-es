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
ms.openlocfilehash: 4b13659f7c9909e9795caee1eace8da8092c5b9a
ms.sourcegitcommit: a97ecb94437362b21fffc5eb3c38b6c0b4368999
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/13/2019
ms.locfileid: "68974035"
---
# <a name="icorprofilerinfo10enumerateobjectreferences-method"></a><span data-ttu-id="d55b6-102">ICorProfilerInfo10:: EnumerateObjectReferences (método)</span><span class="sxs-lookup"><span data-stu-id="d55b6-102">ICorProfilerInfo10::EnumerateObjectReferences Method</span></span>
  
 <span data-ttu-id="d55b6-103">Dado un ObjectID, callback y clientData, enumera cada referencia de objeto (si existe).</span><span class="sxs-lookup"><span data-stu-id="d55b6-103">Given an ObjectID, callback and clientData, enumerates each object reference (if any).</span></span>   
  
## <a name="syntax"></a><span data-ttu-id="d55b6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d55b6-104">Syntax</span></span>  
  
```cpp
HRESULT EnumerateObjectReferences( [in] ObjectID objectId,
                                   [in] ObjectReferenceCallback callback,
                                   [in] void* clientData);
```  
  
#### <a name="parameters"></a><span data-ttu-id="d55b6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d55b6-105">Parameters</span></span>  

 `objectId` \
 <span data-ttu-id="d55b6-106">de Objeto en el que se van a enumerar las referencias.</span><span class="sxs-lookup"><span data-stu-id="d55b6-106">[in] The object to enumerate references on.</span></span>

 `callback` \
 <span data-ttu-id="d55b6-107">de Función a la que se llamará con las referencias para el objeto.</span><span class="sxs-lookup"><span data-stu-id="d55b6-107">[in] The function that will be called with the references for the object.</span></span>

 `clientData` \
 <span data-ttu-id="d55b6-108">de Datos proporcionados por el generador de perfiles `callback` que se van a pasar a la función.</span><span class="sxs-lookup"><span data-stu-id="d55b6-108">[in] Profiler-provided data to pass to the `callback` function.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="d55b6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d55b6-109">Remarks</span></span>  
 <span data-ttu-id="d55b6-110">El `EnumerateObjectReferences` método es similar a [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), con la salvedad de que recorre las referencias a petición para el generador de perfiles en lugar de asignar previamente una matriz para almacenar las referencias.</span><span class="sxs-lookup"><span data-stu-id="d55b6-110">The `EnumerateObjectReferences` method is similar to [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md), except that it walks the references on demand for the profiler instead of pre-allocating an array to store the references.</span></span>  

## <a name="requirements"></a><span data-ttu-id="d55b6-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d55b6-111">Requirements</span></span>  
 <span data-ttu-id="d55b6-112">**Select** Consulte [sistemas operativos compatibles con .net Core](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span><span class="sxs-lookup"><span data-stu-id="d55b6-112">**Platforms:** See [.NET Core supported operating systems](../../../core/windows-prerequisites.md#net-core-supported-operating-systems).</span></span>  
  
 <span data-ttu-id="d55b6-113">**Encabezado**: Corprof. idl, Corprof. h</span><span class="sxs-lookup"><span data-stu-id="d55b6-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d55b6-114">**Biblioteca** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d55b6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d55b6-115">**Versiones de .net:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d55b6-115">**.NET Versions:** [!INCLUDE[net_core_22](../../../../includes/net-core-30-md.md)]</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d55b6-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d55b6-116">See also</span></span>
- [<span data-ttu-id="d55b6-117">Interfaz ICorProfilerInfo10</span><span class="sxs-lookup"><span data-stu-id="d55b6-117">ICorProfilerInfo10 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo10-interface.md)

