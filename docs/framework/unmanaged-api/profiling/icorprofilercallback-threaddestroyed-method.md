---
title: ICorProfilerCallback::ThreadDestroyed (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ThreadDestroyed
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadDestroyed
helpviewer_keywords:
- ThreadDestroyed method [.NET Framework profiling]
- ICorProfilerCallback::ThreadDestroyed method [.NET Framework profiling]
ms.assetid: 4c2b66fd-0595-40a3-8931-f9c4fff97ac8
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4929d9aaf7de9af72ec5ba93f5d7e35c712ac6cd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33451706"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="ec09e-102">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="ec09e-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="ec09e-103">Notifica al generador de perfiles que se ha destruido un subproceso.</span><span class="sxs-lookup"><span data-stu-id="ec09e-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec09e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec09e-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ec09e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec09e-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="ec09e-106">[in] El identificador del subproceso que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="ec09e-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec09e-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ec09e-107">Remarks</span></span>  
 <span data-ttu-id="ec09e-108">El `threadId` valor ya no es válido en el momento de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="ec09e-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec09e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec09e-109">Requirements</span></span>  
 <span data-ttu-id="ec09e-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec09e-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec09e-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ec09e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ec09e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec09e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec09e-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec09e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec09e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec09e-114">See Also</span></span>  
 [<span data-ttu-id="ec09e-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec09e-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="ec09e-116">ThreadCreated (método)</span><span class="sxs-lookup"><span data-stu-id="ec09e-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
