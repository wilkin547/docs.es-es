---
description: 'Más información acerca de: estructura de COR_PRF_GC_GENERATION_RANGE'
title: COR_PRF_GC_GENERATION_RANGE (Estructura)
ms.date: 03/30/2017
api_name:
- COR_PRF_GC_GENERATION_RANGE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_GC_GENERATION_RANGE
helpviewer_keywords:
- COR_PRF_GC_GENERATION_RANGE structure [.NET Framework profiling]
ms.assetid: e7e07273-8d10-4a68-807e-59634e3f8c5e
topic_type:
- apiref
ms.openlocfilehash: ea67a6e6b972b9406b84ad331e8af6189327c5ff
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648927"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="2af03-103">COR_PRF_GC_GENERATION_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="2af03-103">COR_PRF_GC_GENERATION_RANGE Structure</span></span>

<span data-ttu-id="2af03-104">Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="2af03-104">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2af03-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2af03-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="2af03-106">Members</span><span class="sxs-lookup"><span data-stu-id="2af03-106">Members</span></span>  
  
|<span data-ttu-id="2af03-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="2af03-107">Member</span></span>|<span data-ttu-id="2af03-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="2af03-108">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="2af03-109">Un valor de la enumeración [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) que especifica la generación a la que pertenece el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="2af03-109">A value of the [COR_PRF_GC_GENERATION](cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="2af03-110">IDENTIFICADOR de un objeto que especifica la ubicación inicial del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="2af03-110">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="2af03-111">Un puntero a un entero que especifica el tamaño de la parte utilizada del bloque de memoria (es decir, la cantidad de memoria que se usa en el bloque).</span><span class="sxs-lookup"><span data-stu-id="2af03-111">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="2af03-112">Un puntero a un entero que especifica el tamaño del bloque de memoria (es decir, la cantidad de memoria reservada para el bloque).</span><span class="sxs-lookup"><span data-stu-id="2af03-112">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2af03-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="2af03-113">Remarks</span></span>  

 <span data-ttu-id="2af03-114">Se `rangeLength` garantiza que el valor es preciso solo si [ICorProfilerInfo2:: Getgenerationbounds (](icorprofilerinfo2-getgenerationbounds-method.md) o [ICorProfilerInfo2:: getobjectgeneration (](icorprofilerinfo2-getobjectgeneration-method.md), ambos usan la `COR_PRF_GC_GENERATION_RANGE` estructura, se llama desde [ICorProfilerCallback2:: Garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md) o el método [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2af03-114">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2af03-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2af03-115">Requirements</span></span>  

 <span data-ttu-id="2af03-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2af03-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2af03-117">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="2af03-117">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="2af03-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2af03-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2af03-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2af03-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2af03-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="2af03-120">See also</span></span>

- [<span data-ttu-id="2af03-121">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="2af03-121">Profiling Structures</span></span>](profiling-structures.md)
