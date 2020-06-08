---
title: ICorProfilerCallback::ExceptionCatcherLeave (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionCatcherLeave
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionCatcherLeave
helpviewer_keywords:
- ExceptionCatcherLeave method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionCatcherLeave method [.NET Framework profiling]
ms.assetid: 1f3dbdf5-db0c-4b07-bbb7-375de2a63673
topic_type:
- apiref
ms.openlocfilehash: cff2dd9fdb05ea4dd160dfa57df6f047beb57f69
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84500304"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="0fc2e-102">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="0fc2e-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="0fc2e-103">Notifica al generador de perfiles que el control se está pasando fuera del `catch` bloque adecuado.</span><span class="sxs-lookup"><span data-stu-id="0fc2e-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0fc2e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0fc2e-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="0fc2e-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0fc2e-105">Remarks</span></span>  
 <span data-ttu-id="0fc2e-106">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="0fc2e-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="0fc2e-107">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="0fc2e-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="0fc2e-108">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="0fc2e-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0fc2e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0fc2e-109">Requirements</span></span>  
 <span data-ttu-id="0fc2e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0fc2e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0fc2e-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0fc2e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0fc2e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0fc2e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0fc2e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0fc2e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0fc2e-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="0fc2e-114">See also</span></span>

- [<span data-ttu-id="0fc2e-115">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0fc2e-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="0fc2e-116">Método ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="0fc2e-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
