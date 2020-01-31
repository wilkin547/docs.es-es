---
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
ms.openlocfilehash: ab7c8cbc41967af04c4c9a8813f32b9b1f01c6a1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866356"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="f3c0c-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="f3c0c-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="f3c0c-103">Notifica al generador de perfiles que la fase de desenredo del control de excepciones está entrando en una cláusula `finally` incluida en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="f3c0c-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f3c0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3c0c-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f3c0c-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="f3c0c-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="f3c0c-106">\[en] identificador de la función que contiene la cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="f3c0c-106">\[in] The ID of the function that contains the `finally` clause.</span></span>

## <a name="remarks"></a><span data-ttu-id="f3c0c-107">Notas</span><span class="sxs-lookup"><span data-stu-id="f3c0c-107">Remarks</span></span>  
 <span data-ttu-id="f3c0c-108">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="f3c0c-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="f3c0c-109">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="f3c0c-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="f3c0c-110">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="f3c0c-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3c0c-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f3c0c-111">Requirements</span></span>  
 <span data-ttu-id="f3c0c-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3c0c-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3c0c-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f3c0c-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f3c0c-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f3c0c-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f3c0c-115">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3c0c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3c0c-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3c0c-116">See also</span></span>

- [<span data-ttu-id="f3c0c-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3c0c-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="f3c0c-118">GetNotifiedExceptionClauseInfo (método)</span><span class="sxs-lookup"><span data-stu-id="f3c0c-118">GetNotifiedExceptionClauseInfo Method</span></span>](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="f3c0c-119">ExceptionUnwindFinallyLeave (método)</span><span class="sxs-lookup"><span data-stu-id="f3c0c-119">ExceptionUnwindFinallyLeave Method</span></span>](icorprofilercallback-exceptionunwindfinallyleave-method.md)
