---
description: 'Más información sobre: ICorProfilerCallback:: Exceptionthrown ((método)'
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
ms.openlocfilehash: 77ebca8fbc52ed0c46a4f76fb5cdf6cb2923edaf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706141"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="e7736-103">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="e7736-103">ICorProfilerCallback::ExceptionThrown Method</span></span>

<span data-ttu-id="e7736-104">Notifica al generador de perfiles que se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="e7736-104">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e7736-105">Solo se llama a esta función si la excepción llega al código administrado.</span><span class="sxs-lookup"><span data-stu-id="e7736-105">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e7736-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e7736-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e7736-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e7736-107">Parameters</span></span>

- `thrownObjectId`

  <span data-ttu-id="e7736-108">\[in] identificador del objeto que produjo la excepción que se va a producir.</span><span class="sxs-lookup"><span data-stu-id="e7736-108">\[in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="e7736-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="e7736-109">Remarks</span></span>  

 <span data-ttu-id="e7736-110">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="e7736-110">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="e7736-111">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="e7736-111">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="e7736-112">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="e7736-112">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e7736-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e7736-113">Requirements</span></span>  

 <span data-ttu-id="e7736-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e7736-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e7736-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e7736-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e7736-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e7736-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e7736-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e7736-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7736-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e7736-118">See also</span></span>

- [<span data-ttu-id="e7736-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e7736-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
