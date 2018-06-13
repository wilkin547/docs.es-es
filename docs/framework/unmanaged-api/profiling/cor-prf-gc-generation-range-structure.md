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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1f4c8e9a7ce5eddde18c1266cb724d5c3b0d5f41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33450326"
---
# <a name="corprfgcgenerationrange-structure"></a><span data-ttu-id="034fd-102">COR_PRF_GC_GENERATION_RANGE (Estructura)</span><span class="sxs-lookup"><span data-stu-id="034fd-102">COR_PRF_GC_GENERATION_RANGE Structure</span></span>
<span data-ttu-id="034fd-103">Describe un intervalo (es decir, un bloque) de memoria sometida a recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="034fd-103">Describes a range (that is, block) of memory that is undergoing garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="034fd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="034fd-104">Syntax</span></span>  
  
```  
typedef struct COR_PRF_GC_GENERATION_RANGE {  
    COR_PRF_GC_GENERATION generation;  
    ObjectID rangeStart;  
    UINT_PTR rangeLength;  
    UINT_PTR rangeLengthReserved;  
} COR_PRF_GC_GENERATION_RANGE;  
```  
  
## <a name="members"></a><span data-ttu-id="034fd-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="034fd-105">Members</span></span>  
  
|<span data-ttu-id="034fd-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="034fd-106">Member</span></span>|<span data-ttu-id="034fd-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="034fd-107">Description</span></span>|  
|------------|-----------------|  
|`generation`|<span data-ttu-id="034fd-108">Un valor de la [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) pertenece de enumeración que especifica la generación a la que el bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="034fd-108">A value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration that specifies the generation to which the block of memory belongs.</span></span>|  
|`rangeStart`|<span data-ttu-id="034fd-109">El identificador de un objeto que especifica la ubicación inicial del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="034fd-109">The ID of an object that specifies the starting location of the block of memory.</span></span>|  
|`rangeLength`|<span data-ttu-id="034fd-110">Un puntero a un entero que especifica el tamaño de la parte usada del bloque de memoria (es decir, la cantidad de memoria utilizada dentro del bloque).</span><span class="sxs-lookup"><span data-stu-id="034fd-110">A pointer to an integer that specifies the size of the used portion of the memory block (that is, the amount of memory used within the block).</span></span>|  
|`rangeLengthReserved`|<span data-ttu-id="034fd-111">Un puntero a un entero que especifica el tamaño del bloque de memoria (es decir, la cantidad de memoria reservada para el bloque).</span><span class="sxs-lookup"><span data-stu-id="034fd-111">A pointer to an integer that specifies the size of the memory block (that is, the amount of memory reserved for the block).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="034fd-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="034fd-112">Remarks</span></span>  
 <span data-ttu-id="034fd-113">El `rangeLength` valor se garantiza que sea preciso solo si [ICorProfilerInfo2:: GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) o [ICorProfilerInfo2:: GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), ambos que usan el `COR_PRF_GC_GENERATION_RANGE` la estructura, se llama desde el [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) o [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="034fd-113">The `rangeLength` value is guaranteed to be accurate only if [ICorProfilerInfo2::GetGenerationBounds](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md) or [ICorProfilerInfo2::GetObjectGeneration](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md), both of which use the `COR_PRF_GC_GENERATION_RANGE` structure, is called from the [ICorProfilerCallback2::GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) or the [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="034fd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="034fd-114">Requirements</span></span>  
 <span data-ttu-id="034fd-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="034fd-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="034fd-116">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="034fd-116">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="034fd-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="034fd-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="034fd-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="034fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="034fd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="034fd-119">See Also</span></span>  
 [<span data-ttu-id="034fd-120">Estructuras para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="034fd-120">Profiling Structures</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
