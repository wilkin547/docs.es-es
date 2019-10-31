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
ms.openlocfilehash: 97f103844c38ebd3dbff058bfe96ab953cdba960
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131469"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="605fa-102">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="605fa-102">ICorDebugManagedCallback2 Interface</span></span>
<span data-ttu-id="605fa-103">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="605fa-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="605fa-104">`ICorDebugManagedCallback2` es una extensión lógica de la interfaz [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="605fa-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="605fa-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="605fa-105">Methods</span></span>  
  
|<span data-ttu-id="605fa-106">Método</span><span class="sxs-lookup"><span data-stu-id="605fa-106">Method</span></span>|<span data-ttu-id="605fa-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="605fa-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="605fa-108">ChangeConnection (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-108">ChangeConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="605fa-109">Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="605fa-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="605fa-110">CreateConnection (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-110">CreateConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="605fa-111">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="605fa-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="605fa-112">DestroyConnection (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-112">DestroyConnection Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="605fa-113">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="605fa-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="605fa-114">Exception (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-114">Exception Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="605fa-115">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="605fa-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="605fa-116">ExceptionUnwind (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-116">ExceptionUnwind Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="605fa-117">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="605fa-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="605fa-118">FunctionRemapComplete (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-118">FunctionRemapComplete Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="605fa-119">Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.</span><span class="sxs-lookup"><span data-stu-id="605fa-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="605fa-120">FunctionRemapOpportunity (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-120">FunctionRemapOpportunity Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="605fa-121">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="605fa-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="605fa-122">MDANotification (método)</span><span class="sxs-lookup"><span data-stu-id="605fa-122">MDANotification Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="605fa-123">Proporciona una notificación de que la ejecución del código ha encontrado un mensaje del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="605fa-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="605fa-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="605fa-124">Remarks</span></span>  
 <span data-ttu-id="605fa-125">La interfaz de `ICorDebugManagedCallback2` amplía la interfaz `ICorDebugManagedCallback` para controlar los nuevos eventos de depuración introducidos en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="605fa-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="605fa-126">Un depurador debe implementar `ICorDebugManagedCallback2` si está depurando .NET Framework aplicaciones 2,0.</span><span class="sxs-lookup"><span data-stu-id="605fa-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="605fa-127">Se pasa una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="605fa-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="605fa-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="605fa-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="605fa-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="605fa-129">Requirements</span></span>  
 <span data-ttu-id="605fa-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="605fa-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="605fa-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="605fa-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="605fa-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="605fa-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="605fa-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="605fa-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="605fa-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="605fa-134">See also</span></span>

- [<span data-ttu-id="605fa-135">Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)</span><span class="sxs-lookup"><span data-stu-id="605fa-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="605fa-136">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="605fa-136">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="605fa-137">ICorDebugManagedCallback (interfaz)</span><span class="sxs-lookup"><span data-stu-id="605fa-137">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
