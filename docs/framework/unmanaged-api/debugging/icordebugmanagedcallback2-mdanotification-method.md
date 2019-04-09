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
ms.openlocfilehash: 425c606b1f340bbd49cfe3497d394d5ad0dd37a9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133488"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a><span data-ttu-id="3b8e0-102">ICorDebugManagedCallback2::MDANotification (Método)</span><span class="sxs-lookup"><span data-stu-id="3b8e0-102">ICorDebugManagedCallback2::MDANotification Method</span></span>
<span data-ttu-id="3b8e0-103">Proporciona notificación de que la ejecución de código ha encontrado a un Asistente para depuración administrada (MDA) de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-103">Provides notification that code execution has encountered a managed debugging assistant (MDA) in the application that is being debugged.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b8e0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b8e0-104">Syntax</span></span>  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b8e0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b8e0-105">Parameters</span></span>  
 `pController`  
 <span data-ttu-id="3b8e0-106">[in] Un puntero a un ICorDebugController (interfaz) que expone el proceso o un dominio de aplicación en el que se ha producido el MDA.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-106">[in] A pointer to an ICorDebugController interface that exposes the process or application domain in which the MDA occurred.</span></span>  
  
 <span data-ttu-id="3b8e0-107">Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para tomar una decisión.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-107">A debugger should not make any assumptions about whether the controller is a process or an application domain, although it can always query the interface to make a determination.</span></span>  
  
 `pThread`  
 <span data-ttu-id="3b8e0-108">[in] Un puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se ha producido el evento de depuración.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-108">[in] A pointer to an ICorDebugThread interface that exposes the managed thread on which the debug event occurred.</span></span>  
  
 <span data-ttu-id="3b8e0-109">Si el MDA se produjo en una no administrado de subprocesos, el valor de `pThread` será null.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-109">If the MDA occurred on an unmanaged thread, the value of `pThread` will be null.</span></span>  
  
 <span data-ttu-id="3b8e0-110">Debe obtener el identificador de subproceso del sistema operativo (SO) desde el propio objeto MDA.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-110">You must get the operating system (OS) thread ID from the MDA object itself.</span></span>  
  
 `pMDA`  
 <span data-ttu-id="3b8e0-111">[in] Un puntero a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaz que expone la información de MDA.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-111">[in] A pointer to an [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interface that exposes the MDA information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b8e0-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b8e0-112">Remarks</span></span>  
 <span data-ttu-id="3b8e0-113">Un MDA es una advertencia heurística y no requiere ninguna acción explícita del depurador, excepto que realiza la llamada [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-113">An MDA is a heuristic warning and does not require any explicit debugger action except for calling [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) to resume execution of the application that is being debugged.</span></span>  
  
 <span data-ttu-id="3b8e0-114">Common language runtime (CLR) puede determinar qué MDA se desencadenan y qué datos están en cualquier MDA en cualquier momento determinado.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-114">The common language runtime (CLR) can determine which MDAs are fired and which data is in any given MDA at any point.</span></span> <span data-ttu-id="3b8e0-115">Por lo tanto, los depuradores no deben compilar cualquier funcionalidad que requiera modelos de MDA concretos.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-115">Therefore, debuggers should not build any functionality requiring specific MDA patterns.</span></span>  
  
 <span data-ttu-id="3b8e0-116">MDA se pueden poner en cola y poco después de que se encuentra el MDA se desencadena.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-116">MDAs may be queued and fired shortly after the MDA is encountered.</span></span> <span data-ttu-id="3b8e0-117">Esto podría suceder si el tiempo de ejecución debe esperar hasta que alcanza un punto seguro para activar el MDA, en lugar de activar el MDA cuando lo encuentra.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-117">This could happen if the runtime needs to wait until it reaches a safe point for firing the MDA, instead of firing the MDA when it encounters it.</span></span> <span data-ttu-id="3b8e0-118">También significa que el tiempo de ejecución puede desencadenar un número de MDA en un único conjunto de devoluciones de llamada en cola (similares a una operación de evento "adjuntar").</span><span class="sxs-lookup"><span data-stu-id="3b8e0-118">It also means that the runtime may fire a number of MDAs in a single set of queued callbacks (similar to an "attach" event operation).</span></span>  
  
 <span data-ttu-id="3b8e0-119">Un depurador debe liberar la referencia a un `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que el CLR se recicle la memoria utilizada por un MDA.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-119">A debugger should release the reference to an `ICorDebugMDA` instance immediately after returning from the `MDANotification` callback, to allow the CLR to recycle the memory consumed by an MDA.</span></span> <span data-ttu-id="3b8e0-120">Liberar la instancia puede mejorar el rendimiento si se desencadenan muchos MDA.</span><span class="sxs-lookup"><span data-stu-id="3b8e0-120">Releasing the instance may improve performance if many MDAs are firing.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3b8e0-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b8e0-121">Requirements</span></span>  
 <span data-ttu-id="3b8e0-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b8e0-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b8e0-123">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3b8e0-123">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3b8e0-124">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3b8e0-124">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="3b8e0-125">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="3b8e0-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="3b8e0-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b8e0-126">See also</span></span>

- [<span data-ttu-id="3b8e0-127">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="3b8e0-127">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="3b8e0-128">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b8e0-128">ICorDebugManagedCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [<span data-ttu-id="3b8e0-129">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3b8e0-129">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
