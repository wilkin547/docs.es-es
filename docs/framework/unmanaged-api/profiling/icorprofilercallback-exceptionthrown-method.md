---
title: ICorProfilerCallback::ExceptionThrown (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.ExceptionThrown
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::ExceptionThrown
helpviewer_keywords:
- ExceptionThrown method [.NET Framework profiling]
- ICorProfilerCallback::ExceptionThrown method [.NET Framework profiling]
ms.assetid: f1a23f3b-ac21-4905-8abf-8ea59f15af53
topic_type:
- apiref
ms.openlocfilehash: b1799472c4923aaccfabeae459ad72f6ae94c80d
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866382"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="12a6a-102">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="12a6a-102">ICorProfilerCallback::ExceptionThrown Method</span></span>
<span data-ttu-id="12a6a-103">Notifica al generador de perfiles que se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="12a6a-103">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="12a6a-104">Solo se llama a esta función si la excepción llega al código administrado.</span><span class="sxs-lookup"><span data-stu-id="12a6a-104">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12a6a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="12a6a-105">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="12a6a-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="12a6a-106">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="12a6a-107">\[en] identificador del objeto que provocó que se produjera la excepción.</span><span class="sxs-lookup"><span data-stu-id="12a6a-107">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="12a6a-108">Notas</span><span class="sxs-lookup"><span data-stu-id="12a6a-108">Remarks</span></span>  
 <span data-ttu-id="12a6a-109">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="12a6a-109">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="12a6a-110">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="12a6a-110">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="12a6a-111">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="12a6a-111">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12a6a-112">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="12a6a-112">Requirements</span></span>  
 <span data-ttu-id="12a6a-113">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="12a6a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12a6a-114">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="12a6a-114">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="12a6a-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="12a6a-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="12a6a-116">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12a6a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12a6a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="12a6a-117">See also</span></span>

- [<span data-ttu-id="12a6a-118">ICorProfilerCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="12a6a-118">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
