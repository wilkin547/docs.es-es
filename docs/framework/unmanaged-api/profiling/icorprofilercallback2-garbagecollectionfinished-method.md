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
ms.openlocfilehash: 1217bb30be8b88f8ba1cf21f03f2531778358d4b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74439841"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="3a8bd-102">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="3a8bd-102">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>
<span data-ttu-id="3a8bd-103">Notifica al generador de perfiles que se ha completado la recolección de elementos no utilizados y que se han emitido todas las devoluciones de llamada de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="3a8bd-103">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a8bd-104">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3a8bd-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a8bd-105">Remarks</span></span>  
 <span data-ttu-id="3a8bd-106">Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones finales cuando se llama al método `GarbageCollectionFinished`.</span><span class="sxs-lookup"><span data-stu-id="3a8bd-106">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a8bd-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a8bd-107">Requirements</span></span>  
 <span data-ttu-id="3a8bd-108">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a8bd-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8bd-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3a8bd-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3a8bd-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3a8bd-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3a8bd-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8bd-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8bd-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a8bd-112">See also</span></span>

- [<span data-ttu-id="3a8bd-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a8bd-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="3a8bd-114">ICorProfilerCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a8bd-114">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
