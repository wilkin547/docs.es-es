---
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
ms.openlocfilehash: 0bdb8cd02e0beb69e3ec594b0aadd741a5f0d924
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74428337"
---
# <a name="cor_prf_gc_generation_range-structure"></a><span data-ttu-id="5d889-102">COR_PRF_GC_GENERATION_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="5d889-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="5d889-103">Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="5d889-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d889-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5d889-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="5d889-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5d889-105">Members</span></span>  
  
|<span data-ttu-id="5d889-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5d889-106">Member</span></span>|<span data-ttu-id="5d889-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5d889-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="5d889-108">Un valor de la enumeración [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) que especifica la generación a la que pertenece el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="5d889-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="5d889-109">IDENTIFICADOR de un objeto que especifica la ubicación inicial del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="5d889-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="5d889-110">Un puntero a un entero que especifica el tamaño de la parte utilizada del bloque de memoria (es decir, la cantidad de memoria que se usa en el bloque).</span><span class="sxs-lookup"><span data-stu-id="5d889-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="5d889-111">Un puntero a un entero que especifica el tamaño del bloque de memoria (es decir, la cantidad de memoria reservada para el bloque).</span><span class="sxs-lookup"><span data-stu-id="5d889-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d889-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5d889-112">Remarks</span></span>  
 <span data-ttu-id="5d889-113">Se garantiza que el valor `rangeLength` sea preciso solo si [ICorProfilerInfo2:: getgenerationbounds (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) o [Icorprofilerinfo2:: getobjectgeneration (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), ambos usan la estructura `COR_PRF_GC_GENERATION_RANGE`, se llama desde [ICorProfilerCallback2:: garbagecollectionstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) o el método [ICorProfilerCallback2:: garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5d889-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5d889-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5d889-114">Requirements</span></span>  
 <span data-ttu-id="5d889-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5d889-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5d889-116">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="5d889-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="5d889-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5d889-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5d889-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5d889-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d889-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="5d889-119">See also</span></span>

- [<span data-ttu-id="5d889-120">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5d889-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
