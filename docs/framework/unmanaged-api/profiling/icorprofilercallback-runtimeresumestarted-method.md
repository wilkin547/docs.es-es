---
title: ICorProfilerCallback::RuntimeResumeStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeResumeStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeResumeStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeResumeStarted method [.NET Framework profiling]
- RuntimeResumeStarted method [.NET Framework profiling]
ms.assetid: 5854bfb2-c568-4f19-904a-7c9d41e7b995
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70e687f0645fdb68d95effe6fdd52178b92c08e7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452262"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="5f575-102">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="5f575-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="5f575-103">Notifica al generador de perfiles que el runtime está reanudando todos los subprocesos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5f575-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5f575-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5f575-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="5f575-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5f575-105">Requirements</span></span>  
 <span data-ttu-id="5f575-106">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5f575-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5f575-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5f575-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5f575-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5f575-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5f575-109">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5f575-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5f575-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="5f575-110">See Also</span></span>  
 [<span data-ttu-id="5f575-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5f575-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="5f575-112">RuntimeResumeFinished (método)</span><span class="sxs-lookup"><span data-stu-id="5f575-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
