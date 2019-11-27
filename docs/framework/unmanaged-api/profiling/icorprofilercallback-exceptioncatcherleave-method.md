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
ms.openlocfilehash: 7d61a6db8f42398a0d6e0d818605592f4fe71cf7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445000"
---
# <a name="icorprofilercallbackexceptioncatcherleave-method"></a><span data-ttu-id="a04f7-102">ICorProfilerCallback::ExceptionCatcherLeave (Método)</span><span class="sxs-lookup"><span data-stu-id="a04f7-102">ICorProfilerCallback::ExceptionCatcherLeave Method</span></span>
<span data-ttu-id="a04f7-103">Notifica al generador de perfiles que el control se está pasando fuera del bloque de `catch` adecuado.</span><span class="sxs-lookup"><span data-stu-id="a04f7-103">Notifies the profiler that control is being passed out of the appropriate `catch` block.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a04f7-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a04f7-104">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionCatcherLeave();  
```  
  
## <a name="remarks"></a><span data-ttu-id="a04f7-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a04f7-105">Remarks</span></span>  
 <span data-ttu-id="a04f7-106">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="a04f7-106">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="a04f7-107">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="a04f7-107">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="a04f7-108">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="a04f7-108">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a04f7-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a04f7-109">Requirements</span></span>  
 <span data-ttu-id="a04f7-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a04f7-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a04f7-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a04f7-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a04f7-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a04f7-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a04f7-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a04f7-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a04f7-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="a04f7-114">See also</span></span>

- [<span data-ttu-id="a04f7-115">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a04f7-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [<span data-ttu-id="a04f7-116">ExceptionCatcherEnter (método)</span><span class="sxs-lookup"><span data-stu-id="a04f7-116">ExceptionCatcherEnter Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)
