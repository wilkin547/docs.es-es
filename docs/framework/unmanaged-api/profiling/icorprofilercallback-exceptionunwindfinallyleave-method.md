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
ms.openlocfilehash: b6ef54297b69892f07df1aa92a92600fb20756e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445304"
---
# <a name="icorprofilercallbackexceptionunwindfinallyleave-method"></a><span data-ttu-id="89d2c-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="89d2c-102">ICorProfilerCallback::ExceptionUnwindFinallyLeave Method</span></span>
<span data-ttu-id="89d2c-103">Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha dejado una cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="89d2c-103">Notifies the profiler that the unwind phase of exception handling has left a `finally` clause.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89d2c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89d2c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="89d2c-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="89d2c-105">Remarks</span></span>  
 <span data-ttu-id="89d2c-106">El generador de perfiles no debe bloquearse durante esta llamada porque es posible que la pila no esté en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="89d2c-106">The profiler should not block during this call because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="89d2c-107">Si el generador de perfiles se bloquea aquí y se intenta realizar una recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="89d2c-107">If the profiler blocks here and a garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="89d2c-108">Además, durante esta llamada, el generador de perfiles no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="89d2c-108">Also, during this call, the profiler must not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89d2c-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89d2c-109">Requirements</span></span>  
 <span data-ttu-id="89d2c-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89d2c-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89d2c-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="89d2c-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="89d2c-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="89d2c-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="89d2c-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89d2c-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89d2c-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="89d2c-114">See also</span></span>

- [<span data-ttu-id="89d2c-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89d2c-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="89d2c-116">ExceptionUnwindFinallyEnter (método)</span><span class="sxs-lookup"><span data-stu-id="89d2c-116">ExceptionUnwindFinallyEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)
