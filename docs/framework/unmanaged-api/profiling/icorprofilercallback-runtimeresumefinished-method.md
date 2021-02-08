---
description: 'Más información sobre: ICorProfilerCallback:: Runtimeresumefinished ((método)'
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
ms.openlocfilehash: a8a38ff8372df9890239966c90175d72bda4b09d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788857"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="cffa3-103">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="cffa3-103">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>

<span data-ttu-id="cffa3-104">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.</span><span class="sxs-lookup"><span data-stu-id="cffa3-104">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cffa3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cffa3-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="cffa3-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="cffa3-106">Remarks</span></span>  

 <span data-ttu-id="cffa3-107">`RuntimeResumeFinished`No se garantiza que la devolución de llamada se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cffa3-107">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="cffa3-108">Sin embargo, se garantiza que se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cffa3-108">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cffa3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cffa3-109">Requirements</span></span>  

 <span data-ttu-id="cffa3-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cffa3-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cffa3-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cffa3-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cffa3-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cffa3-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cffa3-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cffa3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cffa3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="cffa3-114">See also</span></span>

- [<span data-ttu-id="cffa3-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cffa3-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
