---
title: "ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: e420d27fa1bf122b794489b00853555a7005e69e
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="c106b-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="c106b-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>
<span data-ttu-id="c106b-103">Notifica al generador de perfiles que la fase de desenredo del control de excepciones ha terminado de desenredar una función.</span><span class="sxs-lookup"><span data-stu-id="c106b-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c106b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c106b-104">Syntax</span></span>  
  
```  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="c106b-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c106b-105">Remarks</span></span>  
 <span data-ttu-id="c106b-106">Cuando el `ExceptionUnwindFunctionLeave` se llama al método, la instancia de la función y sus datos de pila se quitan de la pila.</span><span class="sxs-lookup"><span data-stu-id="c106b-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="c106b-107">El generador de perfiles no debe bloquearse durante esta llamada porque la pila no puede estar en un estado que permita la recopilación de elementos no utilizados y, por lo tanto, no se puede habilitar la colección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="c106b-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="c106b-108">Si se intenta aquí los bloques del generador de perfiles y una colección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que devuelve esta devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="c106b-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="c106b-109">Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado o en modo alguno provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="c106b-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c106b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c106b-110">Requirements</span></span>  
 <span data-ttu-id="c106b-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c106b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c106b-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="c106b-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="c106b-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c106b-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c106b-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c106b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c106b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c106b-115">See Also</span></span>  
 [<span data-ttu-id="c106b-116">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c106b-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="c106b-117">ExceptionUnwindFunctionEnter (método)</span><span class="sxs-lookup"><span data-stu-id="c106b-117">ExceptionUnwindFunctionEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)
