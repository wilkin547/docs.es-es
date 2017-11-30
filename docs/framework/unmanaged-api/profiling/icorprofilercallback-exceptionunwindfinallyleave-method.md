---
title: "ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type: apiref
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf373872ada8364fe755162597dc9baf5c527f84
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="3b398-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="3b398-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="3b398-103">Notifica al generador de perfiles que la fase de desenredo de la excepción que ha dejado control un `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="3b398-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b398-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b398-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="3b398-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b398-105">Remarks</span></span>  
 <span data-ttu-id="3b398-106">El generador de perfiles no debe bloquearse durante esta llamada porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="3b398-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="3b398-107">Si se intenta aquí los bloques del generador de perfiles y una colección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="3b398-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="3b398-108">Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="3b398-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b398-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b398-109">Requirements</span></span>  
 <span data-ttu-id="3b398-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b398-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b398-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3b398-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3b398-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b398-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3b398-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3b398-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b398-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b398-114">See Also</span></span>  
 [<span data-ttu-id="3b398-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b398-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="3b398-116">ExceptionUnwindFinallyEnter (método)</span><span class="sxs-lookup"><span data-stu-id="3b398-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
