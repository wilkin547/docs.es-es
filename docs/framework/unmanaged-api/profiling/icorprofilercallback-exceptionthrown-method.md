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
ms.openlocfilehash: aed3d6c4c3c45b546fa8af1db918a6f68eda9bde
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760410"
---
# <a name="icorprofilercallbackexceptionthrown-method"></a><span data-ttu-id="baf29-103">ICorProfilerCallback::ExceptionThrown (Método)</span><span class="sxs-lookup"><span data-stu-id="baf29-103">ICorProfilerCallback::ExceptionThrown Method</span></span>

<span data-ttu-id="baf29-104">Notifica al generador de perfiles que se ha producido una excepción.</span><span class="sxs-lookup"><span data-stu-id="baf29-104">Notifies the profiler that an exception has been thrown.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="baf29-105">Solo se llama a esta función si la excepción llega al código administrado.</span><span class="sxs-lookup"><span data-stu-id="baf29-105">This function is called only if the exception reaches managed code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf29-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baf29-106">Syntax</span></span>  
  
```cpp  
HRESULT ExceptionThrown(  
    [in] ObjectID thrownObjectId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="baf29-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="baf29-107">Parameters</span></span>

<span data-ttu-id="baf29-108">`thrownObjectId` de IDENTIFICADOR del objeto que produjo la excepción que se va a producir.</span><span class="sxs-lookup"><span data-stu-id="baf29-108">`thrownObjectId` [in] The ID of the object that caused the exception to be thrown.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="baf29-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="baf29-109">Remarks</span></span>  

 <span data-ttu-id="baf29-110">El generador de perfiles no debe bloquear en su implementación de este método porque la pila puede no estar en un estado que permita la recolección de elementos no utilizados y, por tanto, no se puede habilitar la recolección de elementos no utilizados preferente.</span><span class="sxs-lookup"><span data-stu-id="baf29-110">The profiler should not block in its implementation of this method because the stack may not be in a state that allows garbage collection, and therefore preemptive garbage collection cannot be enabled.</span></span> <span data-ttu-id="baf29-111">Si el generador de perfiles se bloquea aquí y se intenta la recolección de elementos no utilizados, el tiempo de ejecución se bloqueará hasta que esta devolución de llamada vuelva.</span><span class="sxs-lookup"><span data-stu-id="baf29-111">If the profiler blocks here and garbage collection is attempted, the runtime will block until this callback returns.</span></span>  
  
 <span data-ttu-id="baf29-112">La implementación del generador de perfiles de este método no debe llamar a código administrado ni provocar una asignación de memoria administrada.</span><span class="sxs-lookup"><span data-stu-id="baf29-112">The profiler's implementation of this method should not call into managed code or in any way cause a managed-memory allocation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="baf29-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baf29-113">Requirements</span></span>  

 <span data-ttu-id="baf29-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf29-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf29-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="baf29-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="baf29-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="baf29-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="baf29-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf29-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf29-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="baf29-118">See also</span></span>

- [<span data-ttu-id="baf29-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="baf29-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
