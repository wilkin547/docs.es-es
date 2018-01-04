---
title: "ICorProfilerCallback::RuntimeThreadResumed (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeThreadResumed
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 94d7e46140b36d6fcce788d70cc856a6776e9f24
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="92013-102">ICorProfilerCallback::RuntimeThreadResumed (Método)</span><span class="sxs-lookup"><span data-stu-id="92013-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="92013-103">Notifica al generador de perfiles que el subproceso especificado ha reanudado después de haberse suspendido.</span><span class="sxs-lookup"><span data-stu-id="92013-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92013-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92013-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="92013-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92013-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="92013-106">[in] El identificador del subproceso que se ha reanudado.</span><span class="sxs-lookup"><span data-stu-id="92013-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="92013-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92013-107">Requirements</span></span>  
 <span data-ttu-id="92013-108">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92013-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92013-109">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92013-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="92013-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92013-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="92013-111">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92013-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92013-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="92013-112">See Also</span></span>  
 [<span data-ttu-id="92013-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92013-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="92013-114">RuntimeThreadSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="92013-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
