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
ms.openlocfilehash: e5fcc9d19a400e23d98a997d051c26af1c1084a3
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783021"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="d3af1-102">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="d3af1-102">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>
<span data-ttu-id="d3af1-103">Notifica al generador de perfiles que el tiempo de ejecución está reanudando todos los subprocesos de tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="d3af1-103">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d3af1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d3af1-104">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d3af1-105">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3af1-105">Requirements</span></span>  
 <span data-ttu-id="d3af1-106">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3af1-106">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3af1-107">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d3af1-107">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d3af1-108">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d3af1-108">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d3af1-109">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3af1-109">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3af1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3af1-110">See also</span></span>

- [<span data-ttu-id="d3af1-111">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3af1-111">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="d3af1-112">RuntimeResumeFinished (método)</span><span class="sxs-lookup"><span data-stu-id="d3af1-112">RuntimeResumeFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)
