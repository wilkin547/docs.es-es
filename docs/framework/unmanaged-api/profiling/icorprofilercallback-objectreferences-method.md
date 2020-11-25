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
ms.openlocfilehash: 9485e3ca657ab108d2bcc9d00b1c475f8ee3c086
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95703959"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="b91e1-102">ICorProfilerCallback::ObjectReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="b91e1-102">ICorProfilerCallback::ObjectReferences Method</span></span>

<span data-ttu-id="b91e1-103">Notifica al generador de perfiles sobre los objetos de memoria a los que hace referencia el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="b91e1-103">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b91e1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b91e1-104">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="b91e1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b91e1-105">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="b91e1-106">de IDENTIFICADOR del objeto que hace referencia a los objetos.</span><span class="sxs-lookup"><span data-stu-id="b91e1-106">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="b91e1-107">de IDENTIFICADOR de la clase de la que el objeto especificado es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="b91e1-107">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="b91e1-108">de El número de objetos a los que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).</span><span class="sxs-lookup"><span data-stu-id="b91e1-108">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="b91e1-109">de Matriz de identificadores de objetos a los que hace referencia `objectId` .</span><span class="sxs-lookup"><span data-stu-id="b91e1-109">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b91e1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b91e1-110">Remarks</span></span>  

 <span data-ttu-id="b91e1-111">`ObjectReferences`Se llama al método para cada objeto restante en el montón después de que se haya completado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b91e1-111">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="b91e1-112">Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles interrumpirán la invocación de esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b91e1-112">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="b91e1-113">La `ObjectReferences` devolución de llamada se puede usar junto con la devolución de llamada [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) para crear un gráfico de referencia de objeto completo para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="b91e1-113">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="b91e1-114">El Common Language Runtime (CLR) garantiza que cada referencia de objeto se notifique solo una vez por el `ObjectReferences` método.</span><span class="sxs-lookup"><span data-stu-id="b91e1-114">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="b91e1-115">Los identificadores de objeto devueltos por `ObjectReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos.</span><span class="sxs-lookup"><span data-stu-id="b91e1-115">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="b91e1-116">Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una `ObjectReferences` llamada.</span><span class="sxs-lookup"><span data-stu-id="b91e1-116">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="b91e1-117">Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , se completa la recolección de elementos no utilizados y se puede realizar la inspección de forma segura.</span><span class="sxs-lookup"><span data-stu-id="b91e1-117">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="b91e1-118">Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="b91e1-118">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b91e1-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b91e1-119">Requirements</span></span>  

 <span data-ttu-id="b91e1-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b91e1-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b91e1-121">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b91e1-121">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b91e1-122">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b91e1-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b91e1-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b91e1-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b91e1-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b91e1-124">See also</span></span>

- [<span data-ttu-id="b91e1-125">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b91e1-125">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
