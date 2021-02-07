---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionunwindfinallyenter ((método)'
title: ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFinallyEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFinallyEnter method [.NET Framework profiling]
- ExceptionUnwindFinallyEnter method [.NET Framework profiling]
ms.assetid: c7fab986-b69f-4ec8-b7b7-91dcfc239cd0
topic_type:
- apiref
ms.openlocfilehash: e4a701597b318a387405a152f2c3b4758d616eb0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706089"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="3efb6-103">ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="3efb6-103">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>

<span data-ttu-id="3efb6-104">Notifica al generador de perfiles que la fase de desenredado del control de excepciones está entrando `finally` en una cláusula incluida en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="3efb6-104">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3efb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3efb6-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3efb6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3efb6-106">Parameters</span></span>

- `functionId`

  <span data-ttu-id="3efb6-107">\[in] identificador de la función que contiene la `finally` cláusula.</span><span class="sxs-lookup"><span data-stu-id="3efb6-107">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="3efb6-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3efb6-108">Remarks</span></span>  

 <span data-ttu-id="3efb6-109">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="3efb6-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="3efb6-110">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="3efb6-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="3efb6-111">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="3efb6-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efb6-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3efb6-112">Requirements</span></span>  

 <span data-ttu-id="3efb6-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3efb6-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3efb6-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3efb6-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3efb6-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3efb6-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3efb6-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3efb6-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efb6-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="3efb6-117">See also</span></span>

- [<span data-ttu-id="3efb6-118">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3efb6-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="3efb6-119">Método GetNotifiedExceptionClauseInfo</span><span class="sxs-lookup"><span data-stu-id="3efb6-119">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="3efb6-120">Método ExceptionUnwindFinallyLeave</span><span class="sxs-lookup"><span data-stu-id="3efb6-120">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
