---
title: "COR_PRF_SUSPEND_REASON (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 713360b3cdc30ce7bca3e0df115016d66e59b0df
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprfsuspendreason-enumeration"></a><span data-ttu-id="a9b7f-102">COR_PRF_SUSPEND_REASON (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="a9b7f-102">COR_PRF_SUSPEND_REASON Enumeration</span></span>
<span data-ttu-id="a9b7f-103">Indica la razón por la que se suspende el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-103">Indicates the reason that the runtime is suspended.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9b7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9b7f-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="a9b7f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="a9b7f-105">Members</span></span>  
  
|<span data-ttu-id="a9b7f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="a9b7f-106">Member</span></span>|<span data-ttu-id="a9b7f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a9b7f-107">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|<span data-ttu-id="a9b7f-108">El tiempo de ejecución se suspende por un motivo no especificado.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-108">The runtime is suspended for an unspecified reason.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|<span data-ttu-id="a9b7f-109">El tiempo de ejecución se suspende para atender una solicitud de recopilación de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-109">The runtime is suspended to service a garbage collection request.</span></span><br /><br /> <span data-ttu-id="a9b7f-110">Las devoluciones de llamada relacionadas con la recopilación de elementos no utilizados se producen entre el [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-110">The garbage collection-related callbacks occur between the [ICorProfilerCallback::RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) and [ICorProfilerCallback::RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) callbacks.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|<span data-ttu-id="a9b7f-111">El tiempo de ejecución se suspende para que un `AppDomain` puede cerrarse.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-111">The runtime is suspended so that an `AppDomain` can be shut down.</span></span><br /><br /> <span data-ttu-id="a9b7f-112">Mientras se suspende el tiempo de ejecución, el tiempo de ejecución determinará qué subprocesos están en el `AppDomain` es decir que se va a cerrar y configúrelos para que se anulen cuando se reanuden.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-112">While the runtime is suspended, the runtime will determine which threads are in the `AppDomain` that is being shut down and set them to abort when they resume.</span></span> <span data-ttu-id="a9b7f-113">No hay ningún `AppDomain`-devoluciones de llamada específicas durante esta suspensión.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-113">There are no `AppDomain`-specific callbacks during this suspension.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|<span data-ttu-id="a9b7f-114">El tiempo de ejecución se suspende para que puedan realizarse la eliminación de código nativo.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-114">The runtime is suspended so that code pitching can occur.</span></span><br /><br /> <span data-ttu-id="a9b7f-115">Eliminación de código nativo que habrá trastornos solo cuando el compilador de just-in-time (JIT) está activo con la eliminación de código nativo habilitada.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-115">Code pitching ensues only when the just-in-time (JIT) compiler is active with code pitching enabled.</span></span> <span data-ttu-id="a9b7f-116">Código de eliminación de devoluciones de llamada que se producen entre el `ICorProfilerCallback::RuntimeSuspendFinished` y `ICorProfilerCallback::RuntimeResumeStarted` las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-116">Code pitching callbacks occur between the `ICorProfilerCallback::RuntimeSuspendFinished` and `ICorProfilerCallback::RuntimeResumeStarted` callbacks.</span></span> <span data-ttu-id="a9b7f-117">**Nota:** CLR JIT no las funciones de eliminación en .NET Framework versión 2.0, por lo que este valor no se utiliza en 2.0.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-117">**Note:**  The CLR JIT does not pitch functions in the .NET Framework version 2.0, so this value is not used in 2.0.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|<span data-ttu-id="a9b7f-118">El tiempo de ejecución se suspende para que puede apagar.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-118">The runtime is suspended so that it can shut down.</span></span> <span data-ttu-id="a9b7f-119">Deben suspender todos los subprocesos para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-119">It must suspend all threads to complete the operation.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|<span data-ttu-id="a9b7f-120">El tiempo de ejecución se suspende para la depuración en curso.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-120">The runtime is suspended for in-process debugging.</span></span>|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|<span data-ttu-id="a9b7f-121">El tiempo de ejecución se suspende para prepararse para una colección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-121">The runtime is suspended to prepare for a garbage collection.</span></span>|  
|`COR_PRF_SUSPEND_FOR_REJIT`|<span data-ttu-id="a9b7f-122">El tiempo de ejecución se suspende para la recompilación con JIT.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-122">The runtime is suspended for JIT recompilation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9b7f-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9b7f-123">Remarks</span></span>  
 <span data-ttu-id="a9b7f-124">Para continuar la ejecución hasta que intentan volver a escribir el tiempo de ejecución, momento en que también se suspenderán hasta que el tiempo de ejecución se reanuda, se permiten todos los subprocesos en tiempo de ejecución que están en código no administrado.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-124">All runtime threads that are in unmanaged code are permitted to continue running until they try to re-enter the runtime, at which point they will also be suspended until the runtime resumes.</span></span> <span data-ttu-id="a9b7f-125">Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-125">This also applies to new threads that enter the runtime.</span></span> <span data-ttu-id="a9b7f-126">Todos los subprocesos en tiempo de ejecución se suspende inmediatamente si están en código interrumpible o solicita su suspensión cuando alcanzan código interrumpible.</span><span class="sxs-lookup"><span data-stu-id="a9b7f-126">All threads within the runtime are either suspended immediately if they are in interruptible code, or asked to suspend when they do reach interruptible code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9b7f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9b7f-127">Requirements</span></span>  
 <span data-ttu-id="a9b7f-128">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9b7f-128">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9b7f-129">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9b7f-129">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9b7f-130">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9b7f-130">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9b7f-131">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9b7f-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9b7f-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9b7f-132">See Also</span></span>  
 [<span data-ttu-id="a9b7f-133">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a9b7f-133">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
