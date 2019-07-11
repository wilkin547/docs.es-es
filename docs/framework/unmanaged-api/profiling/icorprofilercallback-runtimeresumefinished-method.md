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
ms.openlocfilehash: 883e226042225b63097acf731b13abd69cc757ba
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750421"
---
# <a name="icorprofilercallbackruntimeresumefinished-method"></a><span data-ttu-id="5fef3-102">ICorProfilerCallback::RuntimeResumeFinished (Método)</span><span class="sxs-lookup"><span data-stu-id="5fef3-102">ICorProfilerCallback::RuntimeResumeFinished Method</span></span>
<span data-ttu-id="5fef3-103">Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y se ha vuelto a su funcionamiento normal.</span><span class="sxs-lookup"><span data-stu-id="5fef3-103">Notifies the profiler that the runtime has resumed all runtime threads and has returned to normal operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fef3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fef3-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeFinished();  
```  
  
## <a name="remarks"></a><span data-ttu-id="5fef3-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fef3-105">Remarks</span></span>  
 <span data-ttu-id="5fef3-106">El `RuntimeResumeFinished` devolución de llamada no se garantiza que se producen en el mismo subproceso que la [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5fef3-106">The `RuntimeResumeFinished` callback is not guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) callback.</span></span> <span data-ttu-id="5fef3-107">Sin embargo, se garantiza que se producen en el mismo subproceso que la [RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="5fef3-107">However, it is guaranteed to occur on the same thread as the [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fef3-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fef3-108">Requirements</span></span>  
 <span data-ttu-id="5fef3-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fef3-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fef3-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fef3-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fef3-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fef3-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fef3-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fef3-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fef3-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fef3-113">See also</span></span>

- [<span data-ttu-id="5fef3-114">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fef3-114">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
