---
title: ICorProfilerCallback::ExceptionUnwindFunctionEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionUnwindFunctionEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionUnwindFunctionEnter method [.NET Framework profiling]
- ExceptionUnwindFunctionEnter method [.NET Framework profiling]
ms.assetid: ea3dc625-5650-4bf4-8e67-01e42be065b1
topic_type:
- apiref
ms.openlocfilehash: d3a09a6caf3febd04296fce518ade42e8676a4b8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731012"
---
# <a name="icorprofilercallbackexceptionunwindfunctionenter-method"></a><span data-ttu-id="db8a7-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="db8a7-102">ICorProfilerCallback::ExceptionUnwindFunctionEnter Method</span></span>

<span data-ttu-id="db8a7-103">Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha empezado a desenredar una función.</span><span class="sxs-lookup"><span data-stu-id="db8a7-103">Notifies the profiler that the unwind phase of exception handling has begun to unwind a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db8a7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db8a7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFunctionEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db8a7-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db8a7-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="db8a7-106">\[in] identificador de la función que se está desenredando.</span><span class="sxs-lookup"><span data-stu-id="db8a7-106">\[in] The ID of the function that is being unwound.</span></span>

## <a name="remarks"></a><span data-ttu-id="db8a7-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db8a7-107">Remarks</span></span>  

 <span data-ttu-id="db8a7-108">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="db8a7-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="db8a7-109">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="db8a7-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="db8a7-110">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="db8a7-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db8a7-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db8a7-111">Requirements</span></span>  

 <span data-ttu-id="db8a7-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db8a7-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db8a7-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="db8a7-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="db8a7-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db8a7-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db8a7-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db8a7-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db8a7-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="db8a7-116">See also</span></span>

- [<span data-ttu-id="db8a7-117">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db8a7-117">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="db8a7-118">Método ExceptionUnwindFunctionLeave</span><span class="sxs-lookup"><span data-stu-id="db8a7-118">ExceptionUnwindFunctionLeave Method</span></span>](icorprofilercallback-exceptionunwindfunctionleave-method.md)
