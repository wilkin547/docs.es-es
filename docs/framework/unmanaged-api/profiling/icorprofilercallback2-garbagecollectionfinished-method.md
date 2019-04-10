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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59231102"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="cb296-102">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="cb296-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="cb296-103">Notifica al generador de perfiles que ha completado la recolección de elementos y todas las devoluciones de llamada de colección de elementos no utilizados se han emitido para ella.</span><span class="sxs-lookup"><span data-stu-id="cb296-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb296-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb296-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cb296-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cb296-105">Remarks</span></span>  
 <span data-ttu-id="cb296-106">Es seguro para el generador de perfiles inspeccionar los objetos en sus ubicaciones finales cuando el `GarbageCollectionFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="cb296-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cb296-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb296-107">Requirements</span></span>  
 <span data-ttu-id="cb296-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb296-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb296-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb296-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb296-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb296-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="cb296-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="cb296-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="cb296-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb296-112">See also</span></span>

- [<span data-ttu-id="cb296-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb296-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="cb296-114">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb296-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
