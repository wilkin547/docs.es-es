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
ms.openlocfilehash: 1f16add7b5a9d18e0c1eb33209b609e9bf7e18b0
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445311"
---
# <a name="icorprofilercallbackexceptionunwindfinallyenter-method"></a><span data-ttu-id="218b2-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="218b2-102">ICorProfilerCallback::ExceptionUnwindFinallyEnter Method</span></span>
<span data-ttu-id="218b2-103">Notifica al generador de perfiles que la fase de desenredo del control de excepciones está entrando en una cláusula `finally` incluida en la función especificada.</span><span class="sxs-lookup"><span data-stu-id="218b2-103">Notifies the profiler that the unwind phase of exception handling is entering a `finally` clause contained in the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="218b2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="218b2-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionUnwindFinallyEnter(  
    [in] FunctionID functionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="218b2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="218b2-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="218b2-106">de IDENTIFICADOR de la función que contiene la cláusula `finally`.</span><span class="sxs-lookup"><span data-stu-id="218b2-106">[in] The ID of the function that contains the `finally` clause.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="218b2-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="218b2-107">Remarks</span></span>  
 <span data-ttu-id="218b2-108">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="218b2-108">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="218b2-109">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="218b2-109">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="218b2-110">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="218b2-110">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="218b2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="218b2-111">Requirements</span></span>  
 <span data-ttu-id="218b2-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="218b2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="218b2-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="218b2-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="218b2-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="218b2-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="218b2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="218b2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="218b2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="218b2-116">See also</span></span>

- [<span data-ttu-id="218b2-117">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="218b2-117">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="218b2-118">GetNotifiedExceptionClauseInfo (método)</span><span class="sxs-lookup"><span data-stu-id="218b2-118">GetNotifiedExceptionClauseInfo Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)
- [<span data-ttu-id="218b2-119">ExceptionUnwindFinallyLeave (método)</span><span class="sxs-lookup"><span data-stu-id="218b2-119">ExceptionUnwindFinallyLeave Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)
