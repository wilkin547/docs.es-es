---
title: "ICorDebugManagedCallback2::MDANotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.MDANotification
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aeddab575f6667dbd27ab3474ae9c6e00dd05750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="ce21d-102">ICorDebugManagedCallback2::MDANotification (Método)</span><span class="sxs-lookup"><span data-stu-id="ce21d-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="ce21d-103">Proporciona notificación de que la ejecución de código ha encontrado a un Asistente para depuración administrada (MDA) en la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="ce21d-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ce21d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ce21d-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ce21d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ce21d-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="ce21d-106">[in] Un puntero a un ICorDebugController (interfaz) que expone el proceso o dominio de aplicación en la que ocurrió el MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="ce21d-107">Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para determinarlo.</span><span class="sxs-lookup"><span data-stu-id="ce21d-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="ce21d-108">[in] Un puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se ha producido el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="ce21d-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="ce21d-109">Si el MDA se produjo en una no administrada de subprocesos, el valor de `pThread` será null.</span><span class="sxs-lookup"><span data-stu-id="ce21d-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="ce21d-110">Debe obtener el identificador de subproceso del sistema operativo (SO) desde el propio objeto MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="ce21d-111">[in] Un puntero a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaz que expone la información de MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ce21d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ce21d-112">Remarks</span></span>  
 <span data-ttu-id="ce21d-113">Un MDA es un aviso heurístico y no requiere ninguna acción del depurador explícita salvo llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="ce21d-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="ce21d-114">Common language runtime (CLR) puede determinar qué MDA se desencadenan y qué datos están en cualquier MDA determinado en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="ce21d-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="ce21d-115">Por lo tanto, los depuradores no deberían compilar funcionalidad que requiera modelos de MDA concretos.</span><span class="sxs-lookup"><span data-stu-id="ce21d-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="ce21d-116">MDA pueden ser en cola y activar poco después de que se encuentra el MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="ce21d-117">Esto podría suceder si el tiempo de ejecución debe esperar hasta que alcanza un punto seguro para desencadenar el MDA, en lugar de activar el MDA cuando lo encuentra.</span><span class="sxs-lookup"><span data-stu-id="ce21d-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="ce21d-118">También significa que el tiempo de ejecución puede activar un número de MDA en un conjunto único de devoluciones de llamada en cola (similares a una operación de eventos "adjuntar").</span><span class="sxs-lookup"><span data-stu-id="ce21d-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="ce21d-119">Un depurador debería liberar la referencia a un `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que el CLR recicle la memoria utilizada por un MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="ce21d-120">Al lanzar la instancia puede mejorar el rendimiento si se desencadenan muchos MDA.</span><span class="sxs-lookup"><span data-stu-id="ce21d-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ce21d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ce21d-121">Requirements</span></span>  
 <span data-ttu-id="ce21d-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ce21d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ce21d-123">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ce21d-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ce21d-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ce21d-124">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ce21d-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ce21d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ce21d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="ce21d-126">See Also</span></span>  
 [<span data-ttu-id="ce21d-127">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="ce21d-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="ce21d-128">ICorDebugManagedCallback2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce21d-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [<span data-ttu-id="ce21d-129">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ce21d-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
