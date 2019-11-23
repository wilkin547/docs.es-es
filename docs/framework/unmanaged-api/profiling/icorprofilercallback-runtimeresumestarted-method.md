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
ms.openlocfilehash: fe204bbe6154bf3d512a998818cf053d1e96ab3d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433534"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="a9700-102">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="a9700-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="a9700-103">Notifies the profiler that the runtime is resuming all run-time threads.</span><span class="sxs-lookup"><span data-stu-id="a9700-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9700-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9700-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="a9700-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9700-105">Requirements</span></span>  
 <span data-ttu-id="a9700-106">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9700-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9700-107">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9700-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9700-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9700-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9700-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9700-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9700-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9700-110">See also</span></span>

- [<span data-ttu-id="a9700-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9700-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a9700-112">RuntimeResumeFinished (método)</span><span class="sxs-lookup"><span data-stu-id="a9700-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
