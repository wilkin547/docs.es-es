---
description: 'Más información acerca de: ICorProfilerCallback:: ObjectReferences (método)'
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
ms.openlocfilehash: 55ea6fae87ecb6534af322fc9d5055c8a247f37a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745117"
---
# <a name="icorprofilercallbackobjectreferences-method"></a><span data-ttu-id="09585-103">ICorProfilerCallback::ObjectReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="09585-103">ICorProfilerCallback::ObjectReferences Method</span></span>

<span data-ttu-id="09585-104">Notifica al generador de perfiles sobre los objetos de memoria a los que hace referencia el objeto especificado.</span><span class="sxs-lookup"><span data-stu-id="09585-104">Notifies the profiler about objects in memory that are being referenced by the specified object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09585-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09585-105">Syntax</span></span>  
  
```cpp  
HRESULT ObjectReferences(  
    [in]  ObjectID objectId,  
    [in]  ClassID  classId,  
    [in]  ULONG    cObjectRefs,  
    [in, size_is(cObjectRefs)] ObjectID objectRefIds[] );  
```  
  
## <a name="parameters"></a><span data-ttu-id="09585-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09585-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="09585-107">de IDENTIFICADOR del objeto que hace referencia a los objetos.</span><span class="sxs-lookup"><span data-stu-id="09585-107">[in] The ID of the object that is referencing objects.</span></span>  
  
 `classId`  
 <span data-ttu-id="09585-108">de IDENTIFICADOR de la clase de la que el objeto especificado es una instancia de.</span><span class="sxs-lookup"><span data-stu-id="09585-108">[in] The ID of the class that the specified object is an instance of.</span></span>  
  
 `cObjectRefs`  
 <span data-ttu-id="09585-109">de El número de objetos a los que hace referencia el objeto especificado (es decir, el número de elementos de la `objectRefIds` matriz).</span><span class="sxs-lookup"><span data-stu-id="09585-109">[in] The number of objects referenced by the specified object (that is, the number of elements in the `objectRefIds` array).</span></span>  
  
 `objectRefIds`  
 <span data-ttu-id="09585-110">de Matriz de identificadores de objetos a los que hace referencia `objectId` .</span><span class="sxs-lookup"><span data-stu-id="09585-110">[in] An array of IDs of objects that are being referenced by `objectId`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09585-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="09585-111">Remarks</span></span>  

 <span data-ttu-id="09585-112">`ObjectReferences`Se llama al método para cada objeto restante en el montón después de que se haya completado una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="09585-112">The `ObjectReferences` method is called for each object remaining in the heap after a garbage collection has completed.</span></span> <span data-ttu-id="09585-113">Si el generador de perfiles devuelve un error de esta devolución de llamada, los servicios de generación de perfiles interrumpirán la invocación de esta devolución de llamada hasta la siguiente recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="09585-113">If the profiler returns an error from this callback, the profiling services will discontinue invoking this callback until the next garbage collection.</span></span>  
  
 <span data-ttu-id="09585-114">La `ObjectReferences` devolución de llamada se puede usar junto con la devolución de llamada [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) para crear un gráfico de referencia de objeto completo para el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="09585-114">The `ObjectReferences` callback can be used in conjunction with the [ICorProfilerCallback::RootReferences](icorprofilercallback-rootreferences-method.md) callback to create a complete object reference graph for the runtime.</span></span> <span data-ttu-id="09585-115">El Common Language Runtime (CLR) garantiza que cada referencia de objeto se notifique solo una vez por el `ObjectReferences` método.</span><span class="sxs-lookup"><span data-stu-id="09585-115">The common language runtime (CLR) ensures that each object reference is reported only once by the `ObjectReferences` method.</span></span>  
  
 <span data-ttu-id="09585-116">Los identificadores de objeto devueltos por `ObjectReferences` no son válidos durante la devolución de llamada, ya que la recolección de elementos no utilizados podría estar en medio de mover objetos.</span><span class="sxs-lookup"><span data-stu-id="09585-116">The object IDs returned by `ObjectReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects.</span></span> <span data-ttu-id="09585-117">Por lo tanto, los perfiles no deben intentar inspeccionar objetos durante una `ObjectReferences` llamada.</span><span class="sxs-lookup"><span data-stu-id="09585-117">Therefore, profilers must not attempt to inspect objects during an `ObjectReferences` call.</span></span> <span data-ttu-id="09585-118">Cuando se llama a [ICorProfilerCallback2:: garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md) , se completa la recolección de elementos no utilizados y se puede realizar la inspección de forma segura.</span><span class="sxs-lookup"><span data-stu-id="09585-118">When [ICorProfilerCallback2::GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md) is called, the garbage collection is complete and inspection can be safely done.</span></span>  
  
 <span data-ttu-id="09585-119">Un valor null `ClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="09585-119">A null `ClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09585-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09585-120">Requirements</span></span>  

 <span data-ttu-id="09585-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09585-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09585-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="09585-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="09585-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="09585-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="09585-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09585-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09585-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="09585-125">See also</span></span>

- [<span data-ttu-id="09585-126">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09585-126">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
