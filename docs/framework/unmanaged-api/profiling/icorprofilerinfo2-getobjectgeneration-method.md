---
description: 'Más información acerca de: ICorProfilerInfo2:: Getobjectgeneration ((método)'
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
ms.openlocfilehash: f4927c081393a11f7dad7d59cce311b82072659c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716450"
---
# <a name="icorprofilerinfo2getobjectgeneration-method"></a><span data-ttu-id="c1c87-103">ICorProfilerInfo2::GetObjectGeneration (Método)</span><span class="sxs-lookup"><span data-stu-id="c1c87-103">ICorProfilerInfo2::GetObjectGeneration Method</span></span>

<span data-ttu-id="c1c87-104">Obtiene el segmento del montón que contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="c1c87-104">Gets the segment of the heap that contains the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1c87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c1c87-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectGeneration(  
    [in] ObjectID objectId,  
    [out] COR_PRF_GC_GENERATION_RANGE *range);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c1c87-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c1c87-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="c1c87-107">de IDENTIFICADOR del objeto.</span><span class="sxs-lookup"><span data-stu-id="c1c87-107">[in] The ID of the object.</span></span>  
  
 `range`  
 <span data-ttu-id="c1c87-108">enuncia Puntero a una estructura de [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) , que describe un intervalo (es decir, un bloque) de memoria dentro de la generación que se está sometiendo a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="c1c87-108">[out] A pointer to a [COR_PRF_GC_GENERATION_RANGE](cor-prf-gc-generation-range-structure.md) structure, which describes a range (that is, a block) of memory within the generation that is undergoing garbage collection.</span></span> <span data-ttu-id="c1c87-109">Este intervalo contiene el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="c1c87-109">This range contains the specified object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c1c87-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="c1c87-110">Remarks</span></span>  

 <span data-ttu-id="c1c87-111">`GetObjectGeneration`Se puede llamar al método desde cualquier devolución de llamada del generador de perfiles, siempre que la recolección de elementos no utilizados no esté en curso.</span><span class="sxs-lookup"><span data-stu-id="c1c87-111">The `GetObjectGeneration` method may be called from any profiler callback, provided that garbage collection is not in progress.</span></span> <span data-ttu-id="c1c87-112">Es decir, se puede llamar desde cualquier devolución de llamada excepto las que se producen entre [ICorProfilerCallback2:: garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md) y [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md).</span><span class="sxs-lookup"><span data-stu-id="c1c87-112">That is, it may be called from any callback except those that occur between [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) and [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c1c87-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c1c87-113">Requirements</span></span>  

 <span data-ttu-id="c1c87-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c1c87-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c1c87-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c1c87-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c1c87-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c1c87-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c1c87-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c1c87-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1c87-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c1c87-118">See also</span></span>

- [<span data-ttu-id="c1c87-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c87-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="c1c87-120">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c1c87-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
