---
description: 'Más información acerca de: ICorDebugUnmanagedCallback (::D ebugEvent (método)'
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
ms.openlocfilehash: fcd7bc3b380add7465473cb01585eb1656d00aad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99690580"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a><span data-ttu-id="038b1-103">ICorDebugUnmanagedCallback::DebugEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="038b1-103">ICorDebugUnmanagedCallback::DebugEvent Method</span></span>

<span data-ttu-id="038b1-104">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="038b1-104">Notifies the debugger that a native event has been fired.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="038b1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="038b1-105">Syntax</span></span>  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="038b1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="038b1-106">Parameters</span></span>  

 `pDebugEvent`  
 <span data-ttu-id="038b1-107">de Puntero al evento nativo.</span><span class="sxs-lookup"><span data-stu-id="038b1-107">[in] A pointer to the native event.</span></span>  
  
 `fOutOfBand`  
 <span data-ttu-id="038b1-108">[in] `true` , si la interacción con el estado de proceso administrado no es posible después de que se produzca un evento no administrado, hasta que el depurador llama a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md); de lo contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="038b1-108">[in] `true`, if interaction with the managed process state is impossible after an unmanaged event occurs, until the debugger calls [ICorDebugController::Continue](icordebugcontroller-continue-method.md); otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="038b1-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="038b1-109">Remarks</span></span>  

 <span data-ttu-id="038b1-110">Si el subproceso que se está depurando es un subproceso de Win32, no use ningún miembro de la interfaz de depuración de Win32.</span><span class="sxs-lookup"><span data-stu-id="038b1-110">If the thread being debugged is a Win32 thread, do not use any members of the Win32 debugging interface.</span></span> <span data-ttu-id="038b1-111">Solo se puede llamar a `ICorDebugController::Continue` en un subproceso de Win32 y solo al continuar después de un evento fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="038b1-111">You can call `ICorDebugController::Continue` only on a Win32 thread and only when continuing past an out-of-band event.</span></span>  
  
 <span data-ttu-id="038b1-112">La `DebugEvent` devolución de llamada no sigue las reglas estándar para las devoluciones de llamada.</span><span class="sxs-lookup"><span data-stu-id="038b1-112">The `DebugEvent` callback does not follow the standard rules for callbacks.</span></span> <span data-ttu-id="038b1-113">Cuando llame a `DebugEvent` , el proceso estará en el estado sin procesar y depuración de sistema operativo detenido.</span><span class="sxs-lookup"><span data-stu-id="038b1-113">When you call `DebugEvent`, the process will be in the raw, OS-debug stopped state.</span></span> <span data-ttu-id="038b1-114">El proceso no se sincronizará.</span><span class="sxs-lookup"><span data-stu-id="038b1-114">The process will not be synchronized.</span></span> <span data-ttu-id="038b1-115">Se especificará automáticamente el estado Synchronized cuando sea necesario para satisfacer las solicitudes de información sobre el código administrado, lo que puede dar lugar a otras `DebugEvent` devoluciones de llamada anidadas.</span><span class="sxs-lookup"><span data-stu-id="038b1-115">It will automatically enter the synchronized state when necessary to satisfy requests for information about managed code, which may result in other nested `DebugEvent` callbacks.</span></span>  
  
 <span data-ttu-id="038b1-116">Llame a [ICorDebugProcess:: ClearCurrentException (](icordebugprocess-clearcurrentexception-method.md) en el proceso para omitir un evento de excepción antes de continuar con el proceso.</span><span class="sxs-lookup"><span data-stu-id="038b1-116">Call [ICorDebugProcess::ClearCurrentException](icordebugprocess-clearcurrentexception-method.md) on the process to ignore an exception event before continuing the process.</span></span> <span data-ttu-id="038b1-117">Al llamar a este método, se envía DBG_CONTINUE en lugar de DBG_EXCEPTION_NOT_HANDLED en la solicitud continue y se borran automáticamente los puntos de interrupción fuera de banda y las excepciones de un solo paso.</span><span class="sxs-lookup"><span data-stu-id="038b1-117">Calling this method sends DBG_CONTINUE instead of DBG_EXCEPTION_NOT_HANDLED on the continue request, and automatically clears out-of-band breakpoints and single-step exceptions.</span></span> <span data-ttu-id="038b1-118">Los eventos fuera de banda pueden aparecer en cualquier momento, incluso cuando la aplicación que se está depurando aparece detenida y cuando ya existe un evento en banda pendiente.</span><span class="sxs-lookup"><span data-stu-id="038b1-118">Out-of-band events can come at any time, even when the application being debugged appears stopped and when an outstanding in-band event already exists.</span></span>  
  
 <span data-ttu-id="038b1-119">En el .NET Framework versión 2,0, el depurador debe continuar inmediatamente después de un evento de punto de interrupción fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="038b1-119">In the .NET Framework version 2.0, the debugger should immediately continue past an out-of-band breakpoint event.</span></span> <span data-ttu-id="038b1-120">El depurador debe utilizar los métodos [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md) y [ICorDebugProcess2:: ClearUnmanagedBreakpoint (](icordebugprocess2-clearunmanagedbreakpoint-method.md) para agregar y quitar puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="038b1-120">The debugger should be using the [ICorDebugProcess2::SetUnmanagedBreakpoint](icordebugprocess2-setunmanagedbreakpoint-method.md) and [ICorDebugProcess2::ClearUnmanagedBreakpoint](icordebugprocess2-clearunmanagedbreakpoint-method.md) methods to add and remove breakpoints.</span></span> <span data-ttu-id="038b1-121">Estos métodos omitirán automáticamente los puntos de interrupción fuera de banda.</span><span class="sxs-lookup"><span data-stu-id="038b1-121">These methods will skip over any out-of-band breakpoints automatically.</span></span> <span data-ttu-id="038b1-122">Por lo tanto, los únicos puntos de interrupción fuera de banda que se envían deben ser puntos de interrupción sin formato que ya estén en el flujo de instrucciones, como una llamada a la `DebugBreak` función de Win32.</span><span class="sxs-lookup"><span data-stu-id="038b1-122">Thus, the only out-of-band breakpoints that get dispatched should be raw breakpoints that are already in the instruction stream, such as a call to the Win32 `DebugBreak` function.</span></span> <span data-ttu-id="038b1-123">No intente usar `ICorDebugProcess::ClearCurrentException` , [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)o cualquier otro miembro de la [API de depuración](index.md).</span><span class="sxs-lookup"><span data-stu-id="038b1-123">Do not try to use `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess::GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess::SetThreadContext](icordebugprocess-setthreadcontext-method.md), or any other member of the [debugging API](index.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="038b1-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="038b1-124">Requirements</span></span>  

 <span data-ttu-id="038b1-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="038b1-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="038b1-126">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="038b1-126">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="038b1-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="038b1-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="038b1-128">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="038b1-128">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="038b1-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="038b1-129">See also</span></span>

- [<span data-ttu-id="038b1-130">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="038b1-130">ICorDebugUnmanagedCallback Interface</span></span>](icordebugunmanagedcallback-interface.md)
