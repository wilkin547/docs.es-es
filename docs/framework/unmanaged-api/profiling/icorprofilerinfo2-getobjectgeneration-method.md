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
ms.openlocfilehash: 4ba404692bef84c0522a799c61f07eac341eaab4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703855"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="c22d2-102">ICorProfilerInfo2::GetObjectGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="c22d2-102">ICorProfilerInfo2::GetObjectGeneration Method</span></span>

<span data-ttu-id="c22d2-103">Obtiene el segmento del montón que contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="c22d2-103">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c22d2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c22d2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c22d2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c22d2-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="c22d2-106">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="c22d2-106">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="c22d2-107">enuncia Puntero a una estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , que describe un intervalo (es decir, un bloque) de memoria dentro de la generación que se está sometiendo a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c22d2-107">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="c22d2-108">Este intervalo contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="c22d2-108">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c22d2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c22d2-109">Remarks</span></span>  

 <span data-ttu-id="c22d2-110">`GetObjectGeneration`Se puede llamar al método desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.</span><span class="sxs-lookup"><span data-stu-id="c22d2-110">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="c22d2-111">Es decir, se puede llamar desde cualquier devolución de llamada excepto las que se producen entre [ICorProfilerCallback2:: garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="c22d2-111">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c22d2-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c22d2-112">Requirements</span></span>  

 <span data-ttu-id="c22d2-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c22d2-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c22d2-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c22d2-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c22d2-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c22d2-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c22d2-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c22d2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c22d2-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c22d2-117">See also</span></span>

- [<span data-ttu-id="c22d2-118">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c22d2-118">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c22d2-119">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c22d2-119">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
