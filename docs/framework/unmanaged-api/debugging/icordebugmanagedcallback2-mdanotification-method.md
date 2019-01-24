---
title: ICorDebugManagedCallback2::MDANotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90c805a5f1f1da990564034fc292562d5f933d71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608094"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="e2497-102">ICorDebugManagedCallback2::MDANotification (Método)</span><span class="sxs-lookup"><span data-stu-id="e2497-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="e2497-103">Proporciona notificación de que la ejecución de código ha encontrado a un Asistente para depuración administrada (MDA) de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e2497-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2497-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2497-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="e2497-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2497-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="e2497-106">[in] Un puntero a un ICorDebugController (interfaz) que expone el proceso o un dominio de aplicación en el que se ha producido el MDA.</span><span class="sxs-lookup"><span data-stu-id="e2497-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="e2497-107">Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para tomar una decisión.</span><span class="sxs-lookup"><span data-stu-id="e2497-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="e2497-108">[in] Un puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se ha producido el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="e2497-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="e2497-109">Si el MDA se produjo en una no administrado de subprocesos, el valor de `pThread` será null.</span><span class="sxs-lookup"><span data-stu-id="e2497-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="e2497-110">Debe obtener el identificador de subproceso del sistema operativo (SO) desde el propio objeto MDA.</span><span class="sxs-lookup"><span data-stu-id="e2497-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="e2497-111">[in] Un puntero a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaz que expone la información de MDA.</span><span class="sxs-lookup"><span data-stu-id="e2497-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e2497-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e2497-112">Remarks</span></span>  
 <span data-ttu-id="e2497-113">Un MDA es una advertencia heurística y no requiere ninguna acción explícita del depurador, excepto que realiza la llamada [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="e2497-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="e2497-114">Common language runtime (CLR) puede determinar qué MDA se desencadenan y qué datos están en cualquier MDA en cualquier momento determinado.</span><span class="sxs-lookup"><span data-stu-id="e2497-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="e2497-115">Por lo tanto, los depuradores no deben compilar cualquier funcionalidad que requiera modelos de MDA concretos.</span><span class="sxs-lookup"><span data-stu-id="e2497-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="e2497-116">MDA se pueden poner en cola y poco después de que se encuentra el MDA se desencadena.</span><span class="sxs-lookup"><span data-stu-id="e2497-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="e2497-117">Esto podría suceder si el tiempo de ejecución debe esperar hasta que alcanza un punto seguro para activar el MDA, en lugar de activar el MDA cuando lo encuentra.</span><span class="sxs-lookup"><span data-stu-id="e2497-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="e2497-118">También significa que el tiempo de ejecución puede desencadenar un número de MDA en un único conjunto de devoluciones de llamada en cola (similares a una operación de evento "adjuntar").</span><span class="sxs-lookup"><span data-stu-id="e2497-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="e2497-119">Un depurador debe liberar la referencia a un `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que el CLR se recicle la memoria utilizada por un MDA.</span><span class="sxs-lookup"><span data-stu-id="e2497-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="e2497-120">Liberar la instancia puede mejorar el rendimiento si se desencadenan muchos MDA.</span><span class="sxs-lookup"><span data-stu-id="e2497-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2497-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2497-121">Requirements</span></span>  
 <span data-ttu-id="e2497-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2497-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2497-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e2497-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e2497-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e2497-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e2497-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2497-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2497-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2497-126">See also</span></span>
- [<span data-ttu-id="e2497-127">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="e2497-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="e2497-128">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2497-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="e2497-129">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2497-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
