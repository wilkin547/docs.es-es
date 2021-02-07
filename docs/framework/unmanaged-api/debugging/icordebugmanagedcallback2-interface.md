---
description: 'Más información acerca de: interfaz ICorDebugManagedCallback2'
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
ms.openlocfilehash: a6a5b05479ea0f9e2d86f7c0ce42f5edd35bcb7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691762"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="40216-103">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40216-103">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="40216-104">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="40216-104">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="40216-105">`ICorDebugManagedCallback2` es una extensión lógica de la interfaz [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="40216-105">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="40216-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="40216-106">Methods</span></span>  
  
|<span data-ttu-id="40216-107">Método</span><span class="sxs-lookup"><span data-stu-id="40216-107">Method</span></span>|<span data-ttu-id="40216-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="40216-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="40216-109">Método ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="40216-109">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="40216-110">Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="40216-110">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="40216-111">Método CreateConnection</span><span class="sxs-lookup"><span data-stu-id="40216-111">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="40216-112">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="40216-112">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="40216-113">Método DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="40216-113">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="40216-114">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="40216-114">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="40216-115">Método Exception</span><span class="sxs-lookup"><span data-stu-id="40216-115">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="40216-116">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="40216-116">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="40216-117">Método ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="40216-117">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="40216-118">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="40216-118">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="40216-119">Método FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="40216-119">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="40216-120">Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.</span><span class="sxs-lookup"><span data-stu-id="40216-120">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="40216-121">Método FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="40216-121">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="40216-122">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="40216-122">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="40216-123">Método MDANotification</span><span class="sxs-lookup"><span data-stu-id="40216-123">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="40216-124">Proporciona una notificación de que la ejecución del código ha encontrado un mensaje del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="40216-124">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40216-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="40216-125">Remarks</span></span>  

 <span data-ttu-id="40216-126">La `ICorDebugManagedCallback2` interfaz extiende la `ICorDebugManagedCallback` interfaz para controlar los nuevos eventos de depuración introducidos en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="40216-126">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="40216-127">Un depurador debe implementar `ICorDebugManagedCallback2` si está depurando .NET Framework aplicaciones 2,0.</span><span class="sxs-lookup"><span data-stu-id="40216-127">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="40216-128">Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="40216-128">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="40216-129">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="40216-129">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="40216-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="40216-130">Requirements</span></span>  

 <span data-ttu-id="40216-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="40216-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="40216-132">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="40216-132">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="40216-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="40216-133">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="40216-134">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="40216-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40216-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="40216-135">See also</span></span>

- [<span data-ttu-id="40216-136">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="40216-136">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="40216-137">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="40216-137">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="40216-138">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="40216-138">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
