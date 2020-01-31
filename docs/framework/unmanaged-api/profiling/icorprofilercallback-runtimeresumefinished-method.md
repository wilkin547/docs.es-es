---
title: ICorProfilerCallback::RuntimeResumeFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeFinished
helpviewer_keywords:
- RuntimeResumeFinished method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeResumeFinished method [.NET Framework profiling]
ms.assetid: 76de0494-dc49-426b-887d-bee98806a982
topic_type:
- apiref
ms.openlocfilehash: 5cafbca75992a5fe8a7d3d95628e0018f1a2e8fa
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865953"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="5056c-102">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="5056c-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="5056c-103">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.</span><span class="sxs-lookup"><span data-stu-id="5056c-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5056c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5056c-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5056c-105">Notas</span><span class="sxs-lookup"><span data-stu-id="5056c-105">Remarks</span></span>  
 <span data-ttu-id="5056c-106">No se garantiza que la devolución de llamada de `RuntimeResumeFinished` se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5056c-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="5056c-107">Sin embargo, se garantiza que se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="5056c-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5056c-108">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="5056c-108">Requirements</span></span>  
 <span data-ttu-id="5056c-109">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5056c-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5056c-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5056c-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5056c-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5056c-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5056c-112">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5056c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5056c-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5056c-113">See also</span></span>

- [<span data-ttu-id="5056c-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5056c-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
