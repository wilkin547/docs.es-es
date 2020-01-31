---
title: COR_PRF_SUSPEND_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
ms.openlocfilehash: 1036ecbdb735b95c0ad6897c1545e3bd8cb6c3a9
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867079"
---
# <a name="cor_prf_suspend_reason-enumeration"></a><span data-ttu-id="872d8-102">COR_PRF_SUSPEND_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="872d8-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="872d8-103">Indica la razón por la que se suspende el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="872d8-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="872d8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="872d8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a><span data-ttu-id="872d8-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="872d8-105">Members</span></span>  
  
|<span data-ttu-id="872d8-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="872d8-106">Member</span></span>|<span data-ttu-id="872d8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="872d8-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="872d8-108">El tiempo de ejecución se suspende por una razón no especificada.</span><span class="sxs-lookup"><span data-stu-id="872d8-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="872d8-109">El tiempo de ejecución se suspende para atender una solicitud de recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="872d8-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="872d8-110">Las devoluciones de llamada relacionadas con la recolección de elementos no utilizados se producen entre las devoluciones de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) y [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) .</span><span class="sxs-lookup"><span data-stu-id="872d8-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="872d8-111">El tiempo de ejecución se suspende para que se pueda cerrar un `AppDomain`.</span><span class="sxs-lookup"><span data-stu-id="872d8-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="872d8-112">Mientras se suspende el tiempo de ejecución, el tiempo de ejecución determinará qué subprocesos se encuentran en el `AppDomain` que se está cerrando y configurarlos para que se anulen cuando se reanuden.</span><span class="sxs-lookup"><span data-stu-id="872d8-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="872d8-113">No hay devoluciones de llamada específicas de `AppDomain`durante esta suspensión.</span><span class="sxs-lookup"><span data-stu-id="872d8-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="872d8-114">El tiempo de ejecución se suspende para que pueda producirse el paso del código.</span><span class="sxs-lookup"><span data-stu-id="872d8-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="872d8-115">El paso de código solo se retiene cuando el compilador Just-in-Time (JIT) está activo con la eliminación de código habilitada.</span><span class="sxs-lookup"><span data-stu-id="872d8-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="872d8-116">Las devoluciones de llamada de paso de código se producen entre las devoluciones de llamada `ICorProfilerCallback::RuntimeSuspendFinished` y `ICorProfilerCallback::RuntimeResumeStarted`.</span><span class="sxs-lookup"><span data-stu-id="872d8-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="872d8-117">**Nota:**  CLR JIT no realiza el paso de las funciones de la versión 2,0 de .NET Framework, por lo que este valor no se utiliza en 2,0.</span><span class="sxs-lookup"><span data-stu-id="872d8-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="872d8-118">El tiempo de ejecución se suspende para que pueda cerrarse.</span><span class="sxs-lookup"><span data-stu-id="872d8-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="872d8-119">Debe suspender todos los subprocesos para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="872d8-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="872d8-120">El tiempo de ejecución se suspende para la depuración en proceso.</span><span class="sxs-lookup"><span data-stu-id="872d8-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="872d8-121">El tiempo de ejecución se suspende para prepararse para una recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="872d8-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="872d8-122">El tiempo de ejecución se suspende para la recompilación JIT.</span><span class="sxs-lookup"><span data-stu-id="872d8-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="872d8-123">Notas</span><span class="sxs-lookup"><span data-stu-id="872d8-123">Remarks</span></span>  
 <span data-ttu-id="872d8-124">Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución, momento en el que también se suspenderán hasta que se reanude el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="872d8-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="872d8-125">Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="872d8-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="872d8-126">Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si están en código interrumpido o se le piden que se suspendan cuando llegan a código interrumpido.</span><span class="sxs-lookup"><span data-stu-id="872d8-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="872d8-127">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="872d8-127">Requirements</span></span>  
 <span data-ttu-id="872d8-128">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="872d8-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="872d8-129">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="872d8-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="872d8-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="872d8-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="872d8-131">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="872d8-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="872d8-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="872d8-132">See also</span></span>

- [<span data-ttu-id="872d8-133">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="872d8-133">Profiling Enumerations</span></span>](profiling-enumerations.md)
