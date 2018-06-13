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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6b983db7da258fb94f941d01914ece0f7b1359f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453312"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="5a3cb-102">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="5a3cb-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="5a3cb-103">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a su funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="5a3cb-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a3cb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a3cb-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5a3cb-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a3cb-105">Remarks</span></span>  
 <span data-ttu-id="5a3cb-106">El `RuntimeResumeFinished` devolución de llamada no se garantiza que se producen en el mismo subproceso que el [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5a3cb-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="5a3cb-107">Sin embargo, se garantiza que se producen en el mismo subproceso que el [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5a3cb-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a3cb-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a3cb-108">Requirements</span></span>  
 <span data-ttu-id="5a3cb-109">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a3cb-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a3cb-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5a3cb-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5a3cb-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5a3cb-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5a3cb-112">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a3cb-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a3cb-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a3cb-113">See Also</span></span>  
 [<span data-ttu-id="5a3cb-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a3cb-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
