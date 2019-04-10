---
title: ICorProfilerCallback::RuntimeThreadResumed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadResumed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadResumed
helpviewer_keywords:
- ICorProfilerCallback::RuntimeThreadResumed method [.NET Framework profiling]
- RuntimeThreadResumed method [.NET Framework profiling]
ms.assetid: da984f89-4f53-4ab0-ae6f-3e2ee6085994
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 810875d1b91265fe886ce3cd11970cad7fee122d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59228866"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="e6a93-102">ICorProfilerCallback::RuntimeThreadResumed (Método)</span><span class="sxs-lookup"><span data-stu-id="e6a93-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="e6a93-103">Notifica al generador de perfiles que se ha reanudado el subproceso especificado después de haberse suspendido.</span><span class="sxs-lookup"><span data-stu-id="e6a93-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6a93-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6a93-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e6a93-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6a93-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="e6a93-106">[in] El identificador del subproceso que se ha reanudado.</span><span class="sxs-lookup"><span data-stu-id="e6a93-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e6a93-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6a93-107">Requirements</span></span>  
 <span data-ttu-id="e6a93-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6a93-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6a93-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6a93-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6a93-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6a93-110">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e6a93-111">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6a93-111">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6a93-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6a93-112">See also</span></span>

- [<span data-ttu-id="e6a93-113">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e6a93-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="e6a93-114">Método RuntimeThreadSuspended</span><span class="sxs-lookup"><span data-stu-id="e6a93-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
