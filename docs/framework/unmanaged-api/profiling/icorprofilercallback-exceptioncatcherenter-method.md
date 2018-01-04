---
title: "ICorProfilerCallback::ExceptionCatcherEnter (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionCatcherEnter
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type: apiref
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: a72b2e75ee622bab357046ff29fac4aa9223d7a0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="4b000-102">ICorProfilerCallback::ExceptionCatcherEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="4b000-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>
<span data-ttu-id="4b000-103">Notifica al generador de perfiles que se está pasando el control a la correspondiente `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="4b000-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b000-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b000-104">Syntax</span></span>  
  
```  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4b000-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b000-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="4b000-106">[in] El identificador de la función que contiene el `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="4b000-106">[in] The identifier of the function containing the `catch` block.</span></span>  
  
 `objectId`  
 <span data-ttu-id="4b000-107">[in] El identificador de la excepción que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="4b000-107">[in] The identifier of the exception being handled.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4b000-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4b000-108">Remarks</span></span>  
 <span data-ttu-id="4b000-109">El `ExceptionCatcherEnter` método se llama solo si el punto de captura está en código compilado con el compilador just-in-time (JIT).</span><span class="sxs-lookup"><span data-stu-id="4b000-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="4b000-110">Una excepción que se captura en código no administrado o en el código interno del tiempo de ejecución no llamará a esta notificación.</span><span class="sxs-lookup"><span data-stu-id="4b000-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="4b000-111">El `objectId` valor se pasa de nuevo desde una colección de elementos no utilizados podría haber movido el objeto desde el `ExceptionThrown` notificación.</span><span class="sxs-lookup"><span data-stu-id="4b000-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="4b000-112">El generador de perfiles no debe bloquearse en su implementación de este método porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="4b000-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="4b000-113">Si el generador de perfiles se bloquea aquí y se intenta realizar la recolección de elementos, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="4b000-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="4b000-114">Implementación del generador de perfiles de este método no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="4b000-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b000-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b000-115">Requirements</span></span>  
 <span data-ttu-id="4b000-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b000-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b000-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4b000-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4b000-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4b000-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4b000-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b000-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b000-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b000-120">See Also</span></span>  
 [<span data-ttu-id="4b000-121">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b000-121">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="4b000-122">ExceptionCatcherLeave (método)</span><span class="sxs-lookup"><span data-stu-id="4b000-122">ExceptionCatcherLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)
