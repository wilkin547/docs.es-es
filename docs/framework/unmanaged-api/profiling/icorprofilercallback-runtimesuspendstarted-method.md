---
description: 'Más información sobre: ICorProfilerCallback:: Runtimesuspendstarted ((método)'
title: ICorProfilerCallback::RuntimeSuspendStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: 7f7ba6a2a8523589b025d98ea925b77d05d8a59d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657442"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a><span data-ttu-id="ff17e-103">ICorProfilerCallback::RuntimeSuspendStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="ff17e-103">ICorProfilerCallback::RuntimeSuspendStarted Method</span></span>

<span data-ttu-id="ff17e-104">Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff17e-104">Notifies the profiler that the runtime is about to suspend all runtime threads.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ff17e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff17e-105">Syntax</span></span>  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ff17e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff17e-106">Parameters</span></span>  

 `suspendReason`  
 <span data-ttu-id="ff17e-107">de Un valor de la enumeración [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) que indica el motivo de la suspensión.</span><span class="sxs-lookup"><span data-stu-id="ff17e-107">[in] A value of the [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) enumeration that indicates the reason for the suspension.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ff17e-108">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff17e-108">Remarks</span></span>  

 <span data-ttu-id="ff17e-109">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff17e-109">All runtime threads that are in unmanaged code are allowed to continue running until they try to re-enter the runtime.</span></span> <span data-ttu-id="ff17e-110">En ese momento, también se suspenderán hasta que se reanude el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff17e-110">At that point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="ff17e-111">Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="ff17e-111">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="ff17e-112">Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si ya están en código interrumpido, o se les pide que se suspendan cuando llegan a código interrumpido.</span><span class="sxs-lookup"><span data-stu-id="ff17e-112">All threads in the runtime are either suspended immediately if they are already in interruptible code, or they are asked to suspend when they reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ff17e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff17e-113">Requirements</span></span>  

 <span data-ttu-id="ff17e-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff17e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff17e-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ff17e-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ff17e-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ff17e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ff17e-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ff17e-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff17e-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="ff17e-118">See also</span></span>

- [<span data-ttu-id="ff17e-119">ICorProfilerCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ff17e-119">ICorProfilerCallback Interface</span></span>](icorprofilercallback-interface.md)
- [<span data-ttu-id="ff17e-120">Método RuntimeSuspendAborted</span><span class="sxs-lookup"><span data-stu-id="ff17e-120">RuntimeSuspendAborted Method</span></span>](icorprofilercallback-runtimesuspendaborted-method.md)
- [<span data-ttu-id="ff17e-121">Método RuntimeSuspendFinished</span><span class="sxs-lookup"><span data-stu-id="ff17e-121">RuntimeSuspendFinished Method</span></span>](icorprofilercallback-runtimesuspendfinished-method.md)
