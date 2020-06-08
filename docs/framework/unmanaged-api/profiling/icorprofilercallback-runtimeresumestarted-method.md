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
ms.openlocfilehash: 08e76e295e30ede48733ab35870ec965eb157f60
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499875"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="7f280-102">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="7f280-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="7f280-103">Notifica al generador de perfiles que el Runtime está reanudando todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="7f280-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7f280-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7f280-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="7f280-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7f280-105">Requirements</span></span>  
 <span data-ttu-id="7f280-106">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7f280-106">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7f280-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="7f280-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="7f280-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7f280-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7f280-109">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7f280-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7f280-110">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="7f280-110">See also</span></span>

- [<span data-ttu-id="7f280-111">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7f280-111">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="7f280-112">Método RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="7f280-112">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
