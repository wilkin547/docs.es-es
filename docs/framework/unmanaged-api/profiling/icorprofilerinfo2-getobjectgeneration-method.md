---
title: ICorProfilerInfo2::GetObjectGeneration (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetObjectGeneration
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetObjectGeneration
helpviewer_keywords:
- GetObjectGeneration method [.NET Framework profiling]
- ICorProfilerInfo2::GetObjectGeneration method [.NET Framework profiling]
ms.assetid: b0d25f76-0bd5-4aa6-96cf-bfec0e1de28b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 64e362be57a96bbe0f61b964ab413234f30d0ed1
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61782549"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="ebda6-102">ICorProfilerInfo2::GetObjectGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="ebda6-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>
<span data-ttu-id="ebda6-103">Obtiene el segmento del montón que contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="ebda6-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ebda6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebda6-104">Syntax</span></span>  
  
```  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ebda6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ebda6-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="ebda6-106">[in] El identificador del objeto.</span><span class="sxs-lookup"><span data-stu-id="ebda6-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="ebda6-107">[out] Un puntero a un [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) estructura que describe un intervalo (es decir, un bloque) de memoria dentro de la generación que se está sometiendo a la recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="ebda6-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="ebda6-108">Este intervalo contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="ebda6-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ebda6-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebda6-109">Remarks</span></span>  
 <span data-ttu-id="ebda6-110">El `GetObjectGeneration` método puede llamarse desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no está en curso.</span><span class="sxs-lookup"><span data-stu-id="ebda6-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="ebda6-111">Es decir, se puede llamar desde cualquier devolución de llamada, excepto los que se producen entre [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="ebda6-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ebda6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebda6-112">Requirements</span></span>  
 <span data-ttu-id="ebda6-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ebda6-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ebda6-114">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ebda6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ebda6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ebda6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ebda6-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ebda6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ebda6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebda6-117">See also</span></span>

- [<span data-ttu-id="ebda6-118">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebda6-118">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="ebda6-119">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ebda6-119">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
