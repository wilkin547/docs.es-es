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
ms.openlocfilehash: 2b163d41280c8ea49554cecb845c4be757f55dfc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59168095"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="e259f-102">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="e259f-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="e259f-103">Notifica al generador de perfiles que el tiempo de ejecución está reanudando todos los subprocesos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="e259f-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e259f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e259f-104">Syntax</span></span>  
  
```  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="e259f-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e259f-105">Requirements</span></span>  
 <span data-ttu-id="e259f-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e259f-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e259f-107">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e259f-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e259f-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e259f-108">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e259f-109">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e259f-109">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e259f-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="e259f-110">See also</span></span>

- [<span data-ttu-id="e259f-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e259f-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e259f-112">Método RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="e259f-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
