---
title: ICorDebugManagedCallback2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 22f4b2cb1bafefefaf3a3fc207af76c80c0c9798
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33420347"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="042f8-102">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="042f8-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="042f8-103">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="042f8-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="042f8-104">`ICorDebugManagedCallback2` es una extensión lógica de la [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interfaz.</span><span class="sxs-lookup"><span data-stu-id="042f8-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="042f8-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="042f8-105">Methods</span></span>  
  
|<span data-ttu-id="042f8-106">Método</span><span class="sxs-lookup"><span data-stu-id="042f8-106">Method</span></span>|<span data-ttu-id="042f8-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="042f8-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="042f8-108">ChangeConnection (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="042f8-109">Notifica al depurador que se ha cambiado el conjunto de tareas asociadas con la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="042f8-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="042f8-110">CreateConnection (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="042f8-111">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="042f8-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="042f8-112">DestroyConnection (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="042f8-113">Notifica al depurador que ha finalizado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="042f8-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="042f8-114">Exception (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="042f8-115">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="042f8-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="042f8-116">ExceptionUnwind (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="042f8-117">Proporciona una notificación de estado durante el proceso de desenredo de la excepción.</span><span class="sxs-lookup"><span data-stu-id="042f8-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="042f8-118">FunctionRemapComplete (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="042f8-119">Notifica al depurador que la ejecución de código ha cambiado a una nueva versión de una función modificada.</span><span class="sxs-lookup"><span data-stu-id="042f8-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="042f8-120">FunctionRemapOpportunity (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="042f8-121">Notifica al depurador que la ejecución de código ha alcanzado un punto de secuencia en una versión anterior de una función modificada.</span><span class="sxs-lookup"><span data-stu-id="042f8-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="042f8-122">MDANotification (método)</span><span class="sxs-lookup"><span data-stu-id="042f8-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="042f8-123">Proporciona notificación de que la ejecución de código ha encontrado un mensaje de depuración administrada (MDA) del asistente.</span><span class="sxs-lookup"><span data-stu-id="042f8-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="042f8-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="042f8-124">Remarks</span></span>  
 <span data-ttu-id="042f8-125">El `ICorDebugManagedCallback2` interfaz extiende el `ICorDebugManagedCallback` interfaz para controlar nuevos eventos de depuración que se introdujo en la versión 2.0 de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="042f8-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="042f8-126">Debe implementar un depurador `ICorDebugManagedCallback2` si se está depurando aplicaciones de .NET Framework 2.0.</span><span class="sxs-lookup"><span data-stu-id="042f8-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="042f8-127">Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="042f8-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="042f8-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="042f8-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="042f8-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="042f8-129">Requirements</span></span>  
 <span data-ttu-id="042f8-130">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="042f8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="042f8-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="042f8-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="042f8-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="042f8-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="042f8-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="042f8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="042f8-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="042f8-134">See Also</span></span>  
 [<span data-ttu-id="042f8-135">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="042f8-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [<span data-ttu-id="042f8-136">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="042f8-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [<span data-ttu-id="042f8-137">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="042f8-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
