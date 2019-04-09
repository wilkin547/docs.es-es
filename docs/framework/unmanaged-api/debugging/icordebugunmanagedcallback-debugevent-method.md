---
title: ICorDebugUnmanagedCallback::DebugEvent (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ec45004f5dd87983187690a0a4feefb35b05e85
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59183617"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="db5be-102">ICorDebugUnmanagedCallback::DebugEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="db5be-102">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>
<span data-ttu-id="db5be-103">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="db5be-103">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db5be-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="db5be-104">Syntax</span></span>  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="db5be-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="db5be-105">Parameters</span></span>  
 `pDebugEvent`  
 <span data-ttu-id="db5be-106">[in] Un puntero al evento nativo.</span><span class="sxs-lookup"><span data-stu-id="db5be-106">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="db5be-107">[in] `true`, si es posible la interacción con el estado del proceso administrado después de que se produce un evento no administrado, hasta que el depurador llama [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="db5be-107">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="db5be-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="db5be-108">Remarks</span></span>  
 <span data-ttu-id="db5be-109">Si el subproceso que se está depurando un subproceso de Win32, no utilice a ningún miembro de Win32 de interfaz de depuración.</span><span class="sxs-lookup"><span data-stu-id="db5be-109">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="db5be-110">Puede llamar a `ICorDebugController::Continue` solo en un subproceso de Win32 y sólo cuando continuar más allá de un evento fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="db5be-110">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="db5be-111">El `DebugEvent` devolución de llamada no sigue las reglas estándar para las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="db5be-111">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="db5be-112">Cuando se llama a `DebugEvent`, será el proceso en el modo raw, estado de detención de depuración del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="db5be-112">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="db5be-113">El proceso no se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="db5be-113">The process will not be synchronized.</span></span> <span data-ttu-id="db5be-114">Especificará automáticamente el estado sincronizado cuando sea necesario para satisfacer las solicitudes para obtener información sobre el código administrado, lo que puede provocar otros anidados `DebugEvent` devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="db5be-114">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="db5be-115">Llame a [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) en el proceso para ignorar un evento de excepción antes de continuar el proceso.</span><span class="sxs-lookup"><span data-stu-id="db5be-115">Call [ICorDebugProcess::ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="db5be-116">Llamar a este método envía DBG_CONTINUE en lugar de DBG_EXCEPTION_NOT_HANDLED en la solicitud y borra automáticamente los puntos de interrupción fuera de banda y las excepciones de paso a paso.</span><span class="sxs-lookup"><span data-stu-id="db5be-116">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="db5be-117">Eventos de fuera de banda pueden proceder en cualquier momento, incluso cuando la aplicación que se está depura aparezca detenida y cuando ya existe un evento en banda pendiente.</span><span class="sxs-lookup"><span data-stu-id="db5be-117">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="db5be-118">En la versión 2.0 de .NET Framework, el depurador debe continuar inmediatamente tras un evento de punto de interrupción fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="db5be-118">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="db5be-119">El depurador debe usar el [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) y [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) métodos para agregar y quitar puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="db5be-119">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="db5be-120">Estos métodos omitirán automáticamente cualquier punto de interrupción fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="db5be-120">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="db5be-121">Por lo tanto, los puntos de interrupción solo fuera de banda que se distribución deben ser puntos de interrupción sin formato que ya están en la secuencia de instrucciones, como una llamada a Win32 `DebugBreak` función.</span><span class="sxs-lookup"><span data-stu-id="db5be-121">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="db5be-122">No intente usar `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), o cualquier otro miembro de la [API de depuración](../../../../docs/framework/unmanaged-api/debugging/index.md).</span><span class="sxs-lookup"><span data-stu-id="db5be-122">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](../../../../docs/framework/unmanaged-api/debugging/index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db5be-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db5be-123">Requirements</span></span>  
 <span data-ttu-id="db5be-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db5be-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db5be-125">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db5be-125">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db5be-126">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db5be-126">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="db5be-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="db5be-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="db5be-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="db5be-128">See also</span></span>

- [<span data-ttu-id="db5be-129">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db5be-129">ICorDebugUnmanagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
