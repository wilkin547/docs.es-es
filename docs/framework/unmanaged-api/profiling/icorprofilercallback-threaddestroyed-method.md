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
ms.openlocfilehash: d4c45290b1ef4360e51b5ed8e1b0fac3dcdde727
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59217346"
---
# <a name="icorprofilercallbackthreaddestroyed-method"></a><span data-ttu-id="da103-102">ICorProfilerCallback::ThreadDestroyed (Método)</span><span class="sxs-lookup"><span data-stu-id="da103-102">ICorProfilerCallback::ThreadDestroyed Method</span></span>
<span data-ttu-id="da103-103">Notifica al generador de perfiles que se ha destruido un subproceso.</span><span class="sxs-lookup"><span data-stu-id="da103-103">Notifies the profiler that a thread has been destroyed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da103-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da103-104">Syntax</span></span>  
  
```  
HRESULT ThreadDestroyed(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da103-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da103-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="da103-106">[in] El identificador del subproceso que se ha destruido.</span><span class="sxs-lookup"><span data-stu-id="da103-106">[in] The ID of the thread that has been destroyed.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da103-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da103-107">Remarks</span></span>  
 <span data-ttu-id="da103-108">El `threadId` valor ya no es válido en el momento de esta llamada.</span><span class="sxs-lookup"><span data-stu-id="da103-108">The `threadId` value is no longer valid at the time of this call.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da103-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da103-109">Requirements</span></span>  
 <span data-ttu-id="da103-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da103-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da103-111">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da103-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da103-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da103-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da103-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da103-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da103-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="da103-114">See also</span></span>

- [<span data-ttu-id="da103-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="da103-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="da103-116">ThreadCreated (método)</span><span class="sxs-lookup"><span data-stu-id="da103-116">ThreadCreated Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)
