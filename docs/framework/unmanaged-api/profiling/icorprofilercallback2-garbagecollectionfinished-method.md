---
description: 'Más información sobre: método ICorProfilerCallback2:: Garbagecollectionfinished ('
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
ms.openlocfilehash: 9e41c5ced76af40866269fdff74fd302b937b70e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657119"
---
# <a name="icorprofilercallback2garbagecollectionfinished-method"></a><span data-ttu-id="b7888-103">ICorProfilerCallback2::GarbageCollectionFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="b7888-103">ICorProfilerCallback2::GarbageCollectionFinished Method</span></span>

<span data-ttu-id="b7888-104">Notifica al generador de perfiles que se ha completado la recolección de elementos no utilizados y que se han emitido todas las devoluciones de llamada de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="b7888-104">Notifies the profiler that garbage collection has completed and all garbage collection callbacks have been issued for it.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7888-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b7888-105">Syntax</span></span>  
  
```cpp  
HRESULT GarbageCollectionFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="b7888-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b7888-106">Remarks</span></span>  

 <span data-ttu-id="b7888-107">Es seguro que el generador de perfiles Inspeccione los objetos en sus ubicaciones finales cuando `GarbageCollectionFinished` se llama al método.</span><span class="sxs-lookup"><span data-stu-id="b7888-107">It is safe for the profiler to inspect objects in their final locations when the `GarbageCollectionFinished` method is called.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b7888-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b7888-108">Requirements</span></span>  

 <span data-ttu-id="b7888-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7888-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b7888-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b7888-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b7888-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b7888-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b7888-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b7888-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b7888-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="b7888-113">See also</span></span>

- [<span data-ttu-id="b7888-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7888-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="b7888-115">ICorProfilerCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b7888-115">ICorProfilerCallback2 Interface</span></span>](icorprofilercallback2-interface.md)
