---
title: "ICorProfilerCallback::ObjectReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ObjectReferences
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ObjectReferences
helpviewer_keywords:
- ObjectReferences method [.NET Framework profiling]
- ICorProfilerCallback::ObjectReferences method [.NET Framework profiling]
ms.assetid: dd5e9b64-b4a3-4ba6-9be6-ddb540f4ffcf
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 30b8f6b5f424ff81ace36baa8d2ae39e0a2f1d1e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="19ac4-102">ICorProfilerCallback::ObjectReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="19ac4-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="19ac4-103">Notifica al generador de perfiles acerca de los objetos en memoria que se hace referencia el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="19ac4-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="19ac4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="19ac4-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="19ac4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="19ac4-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="19ac4-106">[in] El identificador del objeto que hace referencia a objetos.</span><span class="sxs-lookup"><span data-stu-id="19ac4-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="19ac4-107">[in] El identificador de la clase que el objeto especificado es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="19ac4-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="19ac4-108">[in] El número de objetos al que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).</span><span class="sxs-lookup"><span data-stu-id="19ac4-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="19ac4-109">[in] Una matriz de identificadores de objetos que se hace referencia a por `objectId`.</span><span class="sxs-lookup"><span data-stu-id="19ac4-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="19ac4-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="19ac4-110">Remarks</span></span>  
 <span data-ttu-id="19ac4-111">El `ObjectReferences` método se llama para cada objeto permanece en el montón después de que ha completado una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="19ac4-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="19ac4-112">Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles dejarán de invocar esta devolución de llamada hasta la siguiente recolección.</span><span class="sxs-lookup"><span data-stu-id="19ac4-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="19ac4-113">El `ObjectReferences` devolución de llamada puede utilizarse junto con la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) devolución de llamada para crear un gráfico de referencia de objeto completo para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="19ac4-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="19ac4-114">Common language runtime (CLR) garantiza que cada referencia de objeto se ha notificado una sola vez por la `ObjectReferences` método.</span><span class="sxs-lookup"><span data-stu-id="19ac4-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="19ac4-115">Los identificadores de objeto devuelven por `ObjectReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados puede estar en el proceso de mover objetos.</span><span class="sxs-lookup"><span data-stu-id="19ac4-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="19ac4-116">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una `ObjectReferences` llamar.</span><span class="sxs-lookup"><span data-stu-id="19ac4-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="19ac4-117">Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) se llama, los elementos no utilizados recopilación está completa y la inspección puede realizarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="19ac4-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="19ac4-118">Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="19ac4-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="19ac4-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="19ac4-119">Requirements</span></span>  
 <span data-ttu-id="19ac4-120">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="19ac4-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19ac4-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="19ac4-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="19ac4-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="19ac4-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="19ac4-123">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19ac4-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19ac4-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="19ac4-124">See Also</span></span>  
 [<span data-ttu-id="19ac4-125">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="19ac4-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
