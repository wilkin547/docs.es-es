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
ms.openlocfilehash: 6b7aa7c60b5e861787d7a115d90a00d67cc48db0
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866538"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="74783-102">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="74783-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="74783-103">Notifica al generador de perfiles que el control se está pasando fuera del bloque de `catch` adecuado.</span><span class="sxs-lookup"><span data-stu-id="74783-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="74783-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="74783-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="74783-105">Notas</span><span class="sxs-lookup"><span data-stu-id="74783-105">Remarks</span></span>  
 <span data-ttu-id="74783-106">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="74783-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="74783-107">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="74783-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="74783-108">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="74783-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="74783-109">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="74783-109">Requirements</span></span>  
 <span data-ttu-id="74783-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="74783-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="74783-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="74783-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="74783-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="74783-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="74783-113">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="74783-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74783-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="74783-114">See also</span></span>

- [<span data-ttu-id="74783-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="74783-115">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="74783-116">ExceptionCatcherEnter (método)</span><span class="sxs-lookup"><span data-stu-id="74783-116">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
