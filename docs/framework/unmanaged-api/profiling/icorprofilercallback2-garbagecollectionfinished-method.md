---
title: ICorProfilerCallback2::GarbageCollectionFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2.GarbageCollectionFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished
helpviewer_keywords:
- ICorProfilerCallback2::GarbageCollectionFinished method [.NET Framework profiling]
- GarbageCollectionFinished method [.NET Framework profiling]
ms.assetid: 1a5758ea-2354-43c0-92a3-32c9909d64e1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 21f7e9fa0e567063c49caa390ace09c43454b092
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451687"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="9dc7a-102">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="9dc7a-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="9dc7a-103">Notifica al generador de perfiles que ha completado la recopilación de elementos no utilizados y se han emitido para él todas las devoluciones de llamada de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="9dc7a-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc7a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9dc7a-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9dc7a-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9dc7a-105">Remarks</span></span>  
 <span data-ttu-id="9dc7a-106">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones definitivas cuando el `GarbageCollectionFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="9dc7a-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc7a-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9dc7a-107">Requirements</span></span>  
 <span data-ttu-id="9dc7a-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9dc7a-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dc7a-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9dc7a-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9dc7a-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9dc7a-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9dc7a-111">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dc7a-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc7a-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="9dc7a-112">See Also</span></span>  
 [<span data-ttu-id="9dc7a-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dc7a-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="9dc7a-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9dc7a-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
