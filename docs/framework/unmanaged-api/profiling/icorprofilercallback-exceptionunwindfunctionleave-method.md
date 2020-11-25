---
title: ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionLeave method [.NET Framework profiling]
- ExceptionUnwindFunctionLeave method [.NET Framework profiling]
ms.assetid: ebaad1d5-ee0a-4cb0-96bc-8ba5d371b747
topic_type:
- apiref
ms.openlocfilehash: 9f88a3fde7d7cb5941e3a7f44a7d94056a959ab8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95733924"
---
# <a name="icorprofilercallbackexceptionunwindfunctionleave-method"></a><span data-ttu-id="fda5d-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="fda5d-102">ICorProfilerCallback::ExceptionUnwindFunctionLeave Method</span></span>

<span data-ttu-id="fda5d-103">Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha terminado de desenredar una función.</span><span class="sxs-lookup"><span data-stu-id="fda5d-103">Notifies the profiler that the unwind phase of exception handling has finished unwinding a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fda5d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fda5d-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fda5d-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fda5d-105">Remarks</span></span>  

 <span data-ttu-id="fda5d-106">Cuando `ExceptionUnwindFunctionLeave` se llama al método, la instancia de la función y sus datos de pila se quitan de la pila.</span><span class="sxs-lookup"><span data-stu-id="fda5d-106">When the `ExceptionUnwindFunctionLeave` method is called, the function instance and its stack data are removed from the stack.</span></span>  
  
 <span data-ttu-id="fda5d-107">El generador de perfiles no debe bloquearse durante esta llamada porque es posible que la pila no esté en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="fda5d-107">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="fda5d-108">Si el generador de perfiles se bloquea aquí y se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="fda5d-108">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="fda5d-109">Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="fda5d-109">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fda5d-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fda5d-110">Requirements</span></span>  

 <span data-ttu-id="fda5d-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fda5d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fda5d-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fda5d-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fda5d-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fda5d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fda5d-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fda5d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fda5d-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="fda5d-115">See also</span></span>

- [<span data-ttu-id="fda5d-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fda5d-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="fda5d-117">Método ExceptionUnwindFunctionEnter</span><span class="sxs-lookup"><span data-stu-id="fda5d-117">ExceptionUnwindFunctionEnter Method</span></span>](icorprofilercallback-exceptionunwindfunctionenter-method.md)
