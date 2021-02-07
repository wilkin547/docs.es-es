---
description: 'Más información sobre: ICorProfilerCallback:: Exceptioncatcherleave ((método)'
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
ms.openlocfilehash: 402a622dc949ef6f93c0ca5916a0690c6e734bd8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706362"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="9358f-103">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="9358f-103">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>

<span data-ttu-id="9358f-104">Notifica al generador de perfiles que el control se está pasando fuera del `catch` bloque adecuado.</span><span class="sxs-lookup"><span data-stu-id="9358f-104">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9358f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9358f-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="9358f-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9358f-106">Remarks</span></span>  

 <span data-ttu-id="9358f-107">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="9358f-107">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="9358f-108">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="9358f-108">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="9358f-109">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="9358f-109">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9358f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9358f-110">Requirements</span></span>  

 <span data-ttu-id="9358f-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9358f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9358f-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9358f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9358f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9358f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9358f-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9358f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9358f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9358f-115">See also</span></span>

- [<span data-ttu-id="9358f-116">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9358f-116">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="9358f-117">Método ExceptionCatcherEnter</span><span class="sxs-lookup"><span data-stu-id="9358f-117">ExceptionCatcherEnter Method</span></span>](icorprofilercallback-exceptioncatcherenter-method.md)
