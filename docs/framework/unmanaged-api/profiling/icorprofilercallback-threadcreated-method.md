---
title: "ICorProfilerCallback::ThreadCreated (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorProfilerCallback.ThreadCreated
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ThreadCreated
helpviewer_keywords:
- ICorProfilerCallback::ThreadCreated method [.NET Framework profiling]
- ThreadCreated method [.NET Framework profiling]
ms.assetid: cca0f799-09b8-4689-a33c-6d6537943a9b
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 01062931e64cf8daa698fd99d4e6318a7a8f6a5f
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackthreadcreated-method"></a><span data-ttu-id="5fbcb-102">ICorProfilerCallback::ThreadCreated (Método)</span><span class="sxs-lookup"><span data-stu-id="5fbcb-102">ICorProfilerCallback::ThreadCreated Method</span></span>
<span data-ttu-id="5fbcb-103">Notifica al generador de perfiles que se ha creado un subproceso.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-103">Notifies the profiler that a thread has been created.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5fbcb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5fbcb-104">Syntax</span></span>  
  
```  
HRESULT ThreadCreated(  
    [in] ThreadID threadId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="5fbcb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5fbcb-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="5fbcb-106">[in] El identificador del subproceso que se ha creado.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-106">[in] The ID of the thread that has been created.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5fbcb-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5fbcb-107">Remarks</span></span>  
 <span data-ttu-id="5fbcb-108">El `threadId` el valor es válido inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="5fbcb-108">The `threadId` value is immediately valid.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5fbcb-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5fbcb-109">Requirements</span></span>  
 <span data-ttu-id="5fbcb-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5fbcb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5fbcb-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5fbcb-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5fbcb-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5fbcb-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5fbcb-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5fbcb-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5fbcb-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="5fbcb-114">See Also</span></span>  
 [<span data-ttu-id="5fbcb-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5fbcb-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="5fbcb-116">ThreadDestroyed (método)</span><span class="sxs-lookup"><span data-stu-id="5fbcb-116">ThreadDestroyed Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)
