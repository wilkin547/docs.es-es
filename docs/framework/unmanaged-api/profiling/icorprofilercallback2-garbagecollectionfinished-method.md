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
ms.openlocfilehash: f613842c12b50b8a58aac1b71bf2f3c53aaf961f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61914490"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="69308-102">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="69308-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="69308-103">Notifica al generador de perfiles que ha completado la recolección de elementos y todas las devoluciones de llamada de colección de elementos no utilizados se han emitido para ella.</span><span class="sxs-lookup"><span data-stu-id="69308-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69308-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="69308-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="69308-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="69308-105">Remarks</span></span>  
 <span data-ttu-id="69308-106">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones finales cuando el `GarbageCollectionFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="69308-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69308-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="69308-107">Requirements</span></span>  
 <span data-ttu-id="69308-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="69308-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69308-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="69308-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="69308-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69308-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69308-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69308-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69308-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="69308-112">See also</span></span>

- [<span data-ttu-id="69308-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69308-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="69308-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="69308-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
