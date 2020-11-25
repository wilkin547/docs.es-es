---
title: ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyLeave method [.NET Framework profiling]
- ExceptionUnwindFinallyLeave method [.NET Framework profiling]
ms.assetid: 2350351e-f253-4c0c-a191-f952bc5700e6
topic_type:
- apiref
ms.openlocfilehash: e02716350aa2bf32bdd7c4b2e01841405de6dc14
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95720404"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="83424-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="83424-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>

<span data-ttu-id="83424-103">Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha dejado una `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="83424-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="83424-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="83424-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="83424-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="83424-105">Remarks</span></span>  

 <span data-ttu-id="83424-106">El generador de perfiles no debe bloquearse durante esta llamada porque es posible que la pila no esté en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="83424-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="83424-107">Si el generador de perfiles se bloquea aquí y se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="83424-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="83424-108">Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="83424-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="83424-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="83424-109">Requirements</span></span>  

 <span data-ttu-id="83424-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="83424-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="83424-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="83424-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="83424-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="83424-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="83424-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="83424-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83424-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="83424-114">See also</span></span>

- [<span data-ttu-id="83424-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="83424-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="83424-116">Método ExceptionUnwindFinallyEnter</span><span class="sxs-lookup"><span data-stu-id="83424-116">ExceptionUnwindFinallyEnter Method</span></span>](icorprofilercallback-exceptionunwindfinallyenter-method.md)
