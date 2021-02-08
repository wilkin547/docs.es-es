---
description: 'Más información acerca de: ICorProfilerCallback:: RootReferences (método)'
title: ICorProfilerCallback::RootReferences (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RootReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type:
- apiref
ms.openlocfilehash: e09434c425784e646c9856693abdfd4ac0d49273
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788870"
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="788b7-103">ICorProfilerCallback::RootReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="788b7-103">ICorProfilerCallback::RootReferences Method</span></span>

<span data-ttu-id="788b7-104">Notifica al generador de perfiles información sobre las referencias raíz después de la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="788b7-104">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="788b7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="788b7-105">Syntax</span></span>  
  
```cpp  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="788b7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="788b7-106">Parameters</span></span>  

 `cRootRefs`  
 <span data-ttu-id="788b7-107">de Número de referencias de la `rootRefIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="788b7-107">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="788b7-108">de Matriz de identificadores de objeto que hacen referencia a un objeto estático o a un objeto de la pila.</span><span class="sxs-lookup"><span data-stu-id="788b7-108">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="788b7-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="788b7-109">Remarks</span></span>  

 <span data-ttu-id="788b7-110">`RootReferences`Se llama a y [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) para notificar al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="788b7-110">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="788b7-111">Normalmente, los generadores implementarán uno u otro, pero no ambos, ya que la información `RootReferences2` que se pasa es un superconjunto de que se ha pasado `RootReferences` .</span><span class="sxs-lookup"><span data-stu-id="788b7-111">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="788b7-112">Es posible `rootRefIds` que la matriz contenga un objeto null.</span><span class="sxs-lookup"><span data-stu-id="788b7-112">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="788b7-113">Por ejemplo, todas las referencias de objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se informará.</span><span class="sxs-lookup"><span data-stu-id="788b7-113">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="788b7-114">Los identificadores de objeto devueltos por `RootReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos de direcciones antiguas a direcciones nuevas.</span><span class="sxs-lookup"><span data-stu-id="788b7-114">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="788b7-115">Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una `RootReferences` llamada.</span><span class="sxs-lookup"><span data-stu-id="788b7-115">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="788b7-116">Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , todos los objetos se movieron a sus nuevas ubicaciones y se pueden inspeccionar de forma segura.</span><span class="sxs-lookup"><span data-stu-id="788b7-116">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="788b7-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="788b7-117">Requirements</span></span>  

 <span data-ttu-id="788b7-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="788b7-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="788b7-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="788b7-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="788b7-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="788b7-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="788b7-121">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="788b7-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="788b7-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="788b7-122">See also</span></span>

- [<span data-ttu-id="788b7-123">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="788b7-123">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
