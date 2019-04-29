---
title: ICorProfilerCallback::ObjectReferences (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1142b33f029708d93cc3b808dc6be2b2df5b0ee3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61942285"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="1cb93-102">ICorProfilerCallback::ObjectReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="1cb93-102">ICorProfilerCallback::ObjectReferences Method</span></span>
<span data-ttu-id="1cb93-103">Notifica al generador de perfiles de objetos en memoria que se hace referencia el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="1cb93-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cb93-104">Syntax</span></span>  
  
```  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cb93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cb93-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="1cb93-106">[in] El identificador del objeto al que hace referencia a objetos.</span><span class="sxs-lookup"><span data-stu-id="1cb93-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="1cb93-107">[in] El identificador de la clase que el objeto especificado es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="1cb93-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="1cb93-108">[in] El número de objetos al que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).</span><span class="sxs-lookup"><span data-stu-id="1cb93-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="1cb93-109">[in] Una matriz de identificadores de objetos que se hace referencia por `objectId`.</span><span class="sxs-lookup"><span data-stu-id="1cb93-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cb93-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cb93-110">Remarks</span></span>  
 <span data-ttu-id="1cb93-111">El `ObjectReferences` se llama al método para cada objeto restante en el montón de una vez completada una recolección de elementos.</span><span class="sxs-lookup"><span data-stu-id="1cb93-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="1cb93-112">Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles dejarán de invocar esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="1cb93-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="1cb93-113">El `ObjectReferences` devolución de llamada puede usarse junto con el [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) devolución de llamada para crear un gráfico de referencia de objeto completo para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="1cb93-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="1cb93-114">Common language runtime (CLR) garantiza que cada referencia de objeto se notifica una sola vez mediante la `ObjectReferences` método.</span><span class="sxs-lookup"><span data-stu-id="1cb93-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="1cb93-115">Los identificadores de objeto devuelven por `ObjectReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados podría estar moviendo los objetos.</span><span class="sxs-lookup"><span data-stu-id="1cb93-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="1cb93-116">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante un `ObjectReferences` llamar.</span><span class="sxs-lookup"><span data-stu-id="1cb93-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="1cb93-117">Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) se denomina la basura recopilación está completa y la inspección puede realizarse de forma segura.</span><span class="sxs-lookup"><span data-stu-id="1cb93-117">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="1cb93-118">Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="1cb93-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cb93-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cb93-119">Requirements</span></span>  
 <span data-ttu-id="1cb93-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cb93-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cb93-121">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1cb93-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1cb93-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cb93-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cb93-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cb93-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb93-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="1cb93-124">See also</span></span>

- [<span data-ttu-id="1cb93-125">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cb93-125">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
