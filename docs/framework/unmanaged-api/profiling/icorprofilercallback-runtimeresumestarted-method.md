---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeResumeStarted ((método)'
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
ms.openlocfilehash: 74e87906b4c429d795aa3074b25f4ac7a9edfa37
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788844"
---
# <a name="icorprofilercallbackruntimeresumestarted-method"></a><span data-ttu-id="cb05a-103">ICorProfilerCallback::RuntimeResumeStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="cb05a-103">ICorProfilerCallback::RuntimeResumeStarted Method</span></span>

<span data-ttu-id="cb05a-104">Notifica al generador de perfiles que el Runtime está reanudando todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="cb05a-104">Notifies the profiler that the runtime is resuming all run-time threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cb05a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cb05a-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeResumeStarted();  
```  
  
## <a name="requirements"></a><span data-ttu-id="cb05a-106">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cb05a-106">Requirements</span></span>  

 <span data-ttu-id="cb05a-107">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cb05a-107">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cb05a-108">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="cb05a-108">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="cb05a-109">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="cb05a-109">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="cb05a-110">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cb05a-110">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb05a-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="cb05a-111">See also</span></span>

- [<span data-ttu-id="cb05a-112">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cb05a-112">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="cb05a-113">Método RuntimeResumeFinished</span><span class="sxs-lookup"><span data-stu-id="cb05a-113">RuntimeResumeFinished Method</span></span>](icorprofilercallback-runtimeresumefinished-method.md)
