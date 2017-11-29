---
title: "ICorProfilerCallback2::GarbageCollectionFinished (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionFinished
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 287c33a80144b9b04fd7e0797071d40e46a52454
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="e2243-102">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="e2243-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="e2243-103">Notifica al generador de perfiles que ha completado la recopilación de elementos no utilizados y se han emitido para él todas las devoluciones de llamada de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="e2243-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2243-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2243-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="e2243-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2243-105">Remarks</span></span>  
 <span data-ttu-id="e2243-106">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones definitivas cuando el `GarbageCollectionFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="e2243-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2243-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2243-107">Requirements</span></span>  
 <span data-ttu-id="e2243-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2243-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2243-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e2243-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e2243-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2243-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2243-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2243-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2243-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2243-112">See Also</span></span>  
 [<span data-ttu-id="e2243-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2243-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="e2243-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2243-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
