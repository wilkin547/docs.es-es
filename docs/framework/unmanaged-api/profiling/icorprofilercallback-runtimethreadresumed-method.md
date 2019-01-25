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
ms.openlocfilehash: 8d1198a931b79cb469048bf5afd48f5172a45721
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54517713"
---
# <a name="icorprofilercallbackruntimethreadresumed-method"></a><span data-ttu-id="eca00-102">ICorProfilerCallback::RuntimeThreadResumed (Método)</span><span class="sxs-lookup"><span data-stu-id="eca00-102">ICorProfilerCallback::RuntimeThreadResumed Method</span></span>
<span data-ttu-id="eca00-103">Notifica al generador de perfiles que se ha reanudado el subproceso especificado después de haberse suspendido.</span><span class="sxs-lookup"><span data-stu-id="eca00-103">Notifies the profiler that the specified thread has resumed after being suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eca00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eca00-104">Syntax</span></span>  
  
```  
HRESULT RuntimeThreadResumed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eca00-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eca00-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="eca00-106">[in] El identificador del subproceso que se ha reanudado.</span><span class="sxs-lookup"><span data-stu-id="eca00-106">[in] The ID of the thread that has been resumed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eca00-107">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eca00-107">Requirements</span></span>  
 <span data-ttu-id="eca00-108">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eca00-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eca00-109">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eca00-109">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eca00-110">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eca00-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eca00-111">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eca00-111">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eca00-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="eca00-112">See also</span></span>
- [<span data-ttu-id="eca00-113">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="eca00-113">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="eca00-114">RuntimeThreadSuspended (método)</span><span class="sxs-lookup"><span data-stu-id="eca00-114">RuntimeThreadSuspended Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)
