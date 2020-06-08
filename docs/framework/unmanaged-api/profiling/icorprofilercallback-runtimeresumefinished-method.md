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
ms.openlocfilehash: 8bc97bb0d36a046353587a95aa2b79eff12866e0
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499888"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="bf8f4-102">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="bf8f4-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="bf8f4-103">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.</span><span class="sxs-lookup"><span data-stu-id="bf8f4-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf8f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bf8f4-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="bf8f4-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bf8f4-105">Remarks</span></span>  
 <span data-ttu-id="bf8f4-106">`RuntimeResumeFinished`No se garantiza que la devolución de llamada se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf8f4-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="bf8f4-107">Sin embargo, se garantiza que se produzca en el mismo subproceso que la devolución de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="bf8f4-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf8f4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bf8f4-108">Requirements</span></span>  
 <span data-ttu-id="bf8f4-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bf8f4-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf8f4-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bf8f4-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bf8f4-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf8f4-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf8f4-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf8f4-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf8f4-113">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="bf8f4-113">See also</span></span>

- [<span data-ttu-id="bf8f4-114">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="bf8f4-114">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
