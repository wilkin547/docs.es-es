---
title: ICorProfilerCallback::ExceptionCatcherEnter (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherEnter
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter
helpviewer_keywords:
- ICorProfilerCallback::ExceptionCatcherEnter method [.NET Framework profiling]
- ExceptionCatcherEnter method [.NET Framework profiling]
ms.assetid: 41462329-a648-46f0-ae6d-728b94c31aa9
topic_type:
- apiref
ms.openlocfilehash: 97b9f517a24a7d82b7697cd0723628ede073b537
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95700163"
---
# <a name="icorprofilercallbackexceptioncatcherenter-method"></a><span data-ttu-id="d2495-102">ICorProfilerCallback::ExceptionCatcherEnter (Método)</span><span class="sxs-lookup"><span data-stu-id="d2495-102">ICorProfilerCallback::ExceptionCatcherEnter Method</span></span>

<span data-ttu-id="d2495-103">Notifica al generador de perfiles que el control se está pasando al `catch` bloque adecuado.</span><span class="sxs-lookup"><span data-stu-id="d2495-103">Notifies the profiler that control is being passed to the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d2495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d2495-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherEnter(  
    [in] FunctionID functionId,  
    [in] ObjectID   objectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d2495-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d2495-105">Parameters</span></span>

- `functionId`

  <span data-ttu-id="d2495-106">\[in] el identificador de la función que contiene el `catch` bloque.</span><span class="sxs-lookup"><span data-stu-id="d2495-106">\[in] The identifier of the function containing the `catch` block.</span></span>
  
- `objectId`

  <span data-ttu-id="d2495-107">\[in] el identificador de la excepción que se está controlando.</span><span class="sxs-lookup"><span data-stu-id="d2495-107">\[in] The identifier of the exception being handled.</span></span>

## <a name="remarks"></a><span data-ttu-id="d2495-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2495-108">Remarks</span></span>  

 <span data-ttu-id="d2495-109">`ExceptionCatcherEnter`Solo se llama al método si el punto de captura está en código compilado con el compilador Just-in-Time (JIT).</span><span class="sxs-lookup"><span data-stu-id="d2495-109">The `ExceptionCatcherEnter` method is called only if the catch point is in code compiled with the just-in-time (JIT) compiler.</span></span> <span data-ttu-id="d2495-110">Una excepción que se detecta en el código no administrado o en el código interno del tiempo de ejecución no llamará a esta notificación.</span><span class="sxs-lookup"><span data-stu-id="d2495-110">An exception that is caught in unmanaged code or in the internal code of the runtime will not call this notification.</span></span> <span data-ttu-id="d2495-111">El `objectId` valor se pasa de nuevo porque una recolección de elementos no utilizados podría haber trasladado el objeto desde la `ExceptionThrown` notificación.</span><span class="sxs-lookup"><span data-stu-id="d2495-111">The `objectId` value is passed again since a garbage collection could have moved the object since the `ExceptionThrown` notification.</span></span>  
  
 <span data-ttu-id="d2495-112">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="d2495-112">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="d2495-113">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="d2495-113">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="d2495-114">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="d2495-114">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2495-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2495-115">Requirements</span></span>  

 <span data-ttu-id="d2495-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2495-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2495-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d2495-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d2495-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2495-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2495-119">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2495-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2495-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d2495-120">See also</span></span>

- [<span data-ttu-id="d2495-121">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2495-121">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="d2495-122">Método ExceptionCatcherLeave</span><span class="sxs-lookup"><span data-stu-id="d2495-122">ExceptionCatcherLeave Method</span></span>](icorprofilercallback-exceptioncatcherleave-method.md)
