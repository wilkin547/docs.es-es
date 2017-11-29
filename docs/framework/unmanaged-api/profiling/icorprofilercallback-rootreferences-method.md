---
title: "ICorProfilerCallback::RootReferences (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RootReferences
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RootReferences
helpviewer_keywords:
- RootReferences method [.NET Framework profiling]
- ICorProfilerCallback::RootReferences method [.NET Framework profiling]
ms.assetid: dbdf853b-d1a4-4828-8ef7-53d121d8e6ae
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a12dec1ed0fecad235090592def9689f60e50193
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackrootreferences-method"></a><span data-ttu-id="86341-102">ICorProfilerCallback::RootReferences (Método)</span><span class="sxs-lookup"><span data-stu-id="86341-102">ICorProfilerCallback::RootReferences Method</span></span>
<span data-ttu-id="86341-103">Notifica al generador de perfiles con información sobre las referencias raíz después de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="86341-103">Notifies the profiler with information about root references after garbage collection.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86341-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86341-104">Syntax</span></span>  
  
```  
HRESULT RootReferences(  
    [in] ULONG    cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[] );  
```  
  
#### <a name="parameters"></a><span data-ttu-id="86341-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86341-105">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="86341-106">[in] El número de referencias en el `rootRefIds` matriz.</span><span class="sxs-lookup"><span data-stu-id="86341-106">[in] The number of references in the `rootRefIds` array.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="86341-107">[in] Una matriz de identificadores de objeto que hacen referencia a un objeto estático o un objeto en la pila.</span><span class="sxs-lookup"><span data-stu-id="86341-107">[in] An array of object IDs that reference either a static object or an object on the stack.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="86341-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86341-108">Remarks</span></span>  
 <span data-ttu-id="86341-109">Ambos `RootReferences` y [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) se llama para notificar al generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="86341-109">Both `RootReferences` and [ICorProfilerCallback2::RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md) are called to notify the profiler.</span></span> <span data-ttu-id="86341-110">Los generadores de perfiles normalmente implementarán uno u otro, pero no ambos, porque la información que se pasa en `RootReferences2` es un supraconjunto de la que se pasan en `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="86341-110">Profilers will normally implement one or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="86341-111">Es posible que el `rootRefIds` matriz para que contenga un objeto null.</span><span class="sxs-lookup"><span data-stu-id="86341-111">It is possible for the `rootRefIds` array to contain a null object.</span></span> <span data-ttu-id="86341-112">Por ejemplo, todas las referencias a objeto declaradas en la pila se tratan como raíces por el recolector de elementos no utilizados y siempre se notificará.</span><span class="sxs-lookup"><span data-stu-id="86341-112">For example, all object references declared on the stack are treated as roots by the garbage collector and will always be reported.</span></span>  
  
 <span data-ttu-id="86341-113">Los identificadores de objeto devuelven por `RootReferences` no son válidos durante la devolución de llamada, porque la colección de elementos no utilizados puede estar en el proceso de mover objetos de direcciones antiguas a nuevas direcciones.</span><span class="sxs-lookup"><span data-stu-id="86341-113">The object IDs returned by `RootReferences` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="86341-114">Por lo tanto, los generadores de perfiles no deben intentar inspeccionar objetos durante una `RootReferences` llamar.</span><span class="sxs-lookup"><span data-stu-id="86341-114">Therefore, profilers must not attempt to inspect objects during a `RootReferences` call.</span></span> <span data-ttu-id="86341-115">Cuando [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) es llama, todos los objetos que se han movido a sus nuevas ubicaciones y se puede inspeccionar con seguridad.</span><span class="sxs-lookup"><span data-stu-id="86341-115">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86341-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86341-116">Requirements</span></span>  
 <span data-ttu-id="86341-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86341-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86341-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="86341-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="86341-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="86341-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="86341-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86341-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86341-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="86341-121">See Also</span></span>  
 [<span data-ttu-id="86341-122">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="86341-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
