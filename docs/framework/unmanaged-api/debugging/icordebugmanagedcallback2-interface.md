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
ms.openlocfilehash: 937a2fb322eb63461d90e215635e1b10ab6afd09
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689789"
---
# <a name="icordebugmanagedcallback2-interface"></a><span data-ttu-id="62e1d-102">ICorDebugManagedCallback2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62e1d-102">ICorDebugManagedCallback2 Interface</span></span>

<span data-ttu-id="62e1d-103">Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="62e1d-103">Provides methods to support debugger exception handling and managed debugging assistants (MDAs).</span></span> <span data-ttu-id="62e1d-104">`ICorDebugManagedCallback2` es una extensión lógica de la interfaz [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .</span><span class="sxs-lookup"><span data-stu-id="62e1d-104">`ICorDebugManagedCallback2` is a logical extension of the [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="62e1d-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="62e1d-105">Methods</span></span>  
  
|<span data-ttu-id="62e1d-106">Método</span><span class="sxs-lookup"><span data-stu-id="62e1d-106">Method</span></span>|<span data-ttu-id="62e1d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="62e1d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="62e1d-108">Método ChangeConnection</span><span class="sxs-lookup"><span data-stu-id="62e1d-108">ChangeConnection Method</span></span>](icordebugmanagedcallback2-changeconnection-method.md)|<span data-ttu-id="62e1d-109">Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="62e1d-109">Notifies the debugger that the set of tasks associated with the specified connection has changed.</span></span>|  
|[<span data-ttu-id="62e1d-110">Método CreateConnection</span><span class="sxs-lookup"><span data-stu-id="62e1d-110">CreateConnection Method</span></span>](icordebugmanagedcallback2-createconnection-method.md)|<span data-ttu-id="62e1d-111">Notifica al depurador que se ha creado una nueva conexión.</span><span class="sxs-lookup"><span data-stu-id="62e1d-111">Notifies the debugger that a new connection has been created.</span></span>|  
|[<span data-ttu-id="62e1d-112">Método DestroyConnection</span><span class="sxs-lookup"><span data-stu-id="62e1d-112">DestroyConnection Method</span></span>](icordebugmanagedcallback2-destroyconnection-method.md)|<span data-ttu-id="62e1d-113">Notifica al depurador que se ha terminado la conexión especificada.</span><span class="sxs-lookup"><span data-stu-id="62e1d-113">Notifies the debugger that the specified connection has been terminated.</span></span>|  
|[<span data-ttu-id="62e1d-114">Método Exception</span><span class="sxs-lookup"><span data-stu-id="62e1d-114">Exception Method</span></span>](icordebugmanagedcallback2-exception-method.md)|<span data-ttu-id="62e1d-115">Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.</span><span class="sxs-lookup"><span data-stu-id="62e1d-115">Notifies the debugger that a search for an exception handler has started.</span></span>|  
|[<span data-ttu-id="62e1d-116">Método ExceptionUnwind</span><span class="sxs-lookup"><span data-stu-id="62e1d-116">ExceptionUnwind Method</span></span>](icordebugmanagedcallback2-exceptionunwind-method.md)|<span data-ttu-id="62e1d-117">Proporciona una notificación de estado durante el proceso de desenredo de excepciones.</span><span class="sxs-lookup"><span data-stu-id="62e1d-117">Provides a status notification during the exception unwinding process.</span></span>|  
|[<span data-ttu-id="62e1d-118">Método FunctionRemapComplete</span><span class="sxs-lookup"><span data-stu-id="62e1d-118">FunctionRemapComplete Method</span></span>](icordebugmanagedcallback2-functionremapcomplete-method.md)|<span data-ttu-id="62e1d-119">Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.</span><span class="sxs-lookup"><span data-stu-id="62e1d-119">Notifies the debugger that code execution has switched to a new version of an edited function.</span></span>|  
|[<span data-ttu-id="62e1d-120">Método FunctionRemapOpportunity</span><span class="sxs-lookup"><span data-stu-id="62e1d-120">FunctionRemapOpportunity Method</span></span>](icordebugmanagedcallback2-functionremapopportunity-method.md)|<span data-ttu-id="62e1d-121">Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.</span><span class="sxs-lookup"><span data-stu-id="62e1d-121">Notifies the debugger that code execution has reached a sequence point in an older version of an edited function.</span></span>|  
|[<span data-ttu-id="62e1d-122">Método MDANotification</span><span class="sxs-lookup"><span data-stu-id="62e1d-122">MDANotification Method</span></span>](icordebugmanagedcallback2-mdanotification-method.md)|<span data-ttu-id="62e1d-123">Proporciona una notificación de que la ejecución del código ha encontrado un mensaje del Asistente para la depuración administrada (MDA).</span><span class="sxs-lookup"><span data-stu-id="62e1d-123">Provides notification that code execution has encountered a managed debugging assistant (MDA) message.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62e1d-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="62e1d-124">Remarks</span></span>  

 <span data-ttu-id="62e1d-125">La `ICorDebugManagedCallback2` interfaz extiende la `ICorDebugManagedCallback` interfaz para controlar los nuevos eventos de depuración introducidos en la .NET Framework versión 2,0.</span><span class="sxs-lookup"><span data-stu-id="62e1d-125">The `ICorDebugManagedCallback2` interface extends the `ICorDebugManagedCallback` interface to handle new debug events introduced in the .NET Framework version 2.0.</span></span>  
  
 <span data-ttu-id="62e1d-126">Un depurador debe implementar `ICorDebugManagedCallback2` si está depurando .NET Framework aplicaciones 2,0.</span><span class="sxs-lookup"><span data-stu-id="62e1d-126">A debugger must implement `ICorDebugManagedCallback2` if it is debugging .NET Framework 2.0 applications.</span></span> <span data-ttu-id="62e1d-127">Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](icordebug-setmanagedhandler-method.md).</span><span class="sxs-lookup"><span data-stu-id="62e1d-127">An instance of `ICorDebugManagedCallback` or `ICorDebugManagedCallback2` is passed as the callback object to [ICorDebug::SetManagedHandler](icordebug-setmanagedhandler-method.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="62e1d-128">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="62e1d-128">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62e1d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="62e1d-129">Requirements</span></span>  

 <span data-ttu-id="62e1d-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="62e1d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62e1d-131">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="62e1d-131">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="62e1d-132">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="62e1d-132">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="62e1d-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62e1d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62e1d-134">Consulte también</span><span class="sxs-lookup"><span data-stu-id="62e1d-134">See also</span></span>

- [<span data-ttu-id="62e1d-135">Diagnóstico de errores con asistentes de depuraciones administradas</span><span class="sxs-lookup"><span data-stu-id="62e1d-135">Diagnosing Errors with Managed Debugging Assistants</span></span>](../../debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [<span data-ttu-id="62e1d-136">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="62e1d-136">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="62e1d-137">ICorDebugManagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="62e1d-137">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
