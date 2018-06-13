---
title: ICorDebugController::HasQueuedCallbacks (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.HasQueuedCallbacks
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eba265b727d00690ab77c6ae831e954d59df7c50
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411615"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="ed846-102">ICorDebugController::HasQueuedCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="ed846-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="ed846-103">Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="ed846-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ed846-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ed846-104">Syntax</span></span>  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="ed846-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ed846-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="ed846-106">[in] Un puntero a un objeto de "ICorDebugThread" que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ed846-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="ed846-107">[out] Un puntero a un valor que es `true` si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="ed846-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="ed846-108">Si se especifica null para la `pThread` parámetro, `HasQueuedCallbacks` devolverá `true` si actualmente no hay devoluciones de llamada administradas en la cola para cualquier subproceso.</span><span class="sxs-lookup"><span data-stu-id="ed846-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ed846-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ed846-109">Remarks</span></span>  
 <span data-ttu-id="ed846-110">Las devoluciones de llamada será enviado a la vez, cada vez que [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se llama.</span><span class="sxs-lookup"><span data-stu-id="ed846-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="ed846-111">El depurador puede comprobar este marcador si desea informar de varios eventos de depuración que se producen al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="ed846-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="ed846-112">Cuando se ponen en cola los eventos de depuración, hayan podido, por lo que el depurador debe vaciar la cola completa para estar seguro del estado del código depurado.</span><span class="sxs-lookup"><span data-stu-id="ed846-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="ed846-113">(Llame a `ICorDebugController::Continue` para purgar la cola.) Por ejemplo, si la cola contiene dos eventos de depuración en el subproceso *X*, y el depurador suspende el subproceso *X* después del primer evento de depuración y, a continuación, llamadas `ICorDebugController::Continue`, el segundo evento de depuración para subproceso *X* se enviarán aunque se ha suspendido el subproceso.</span><span class="sxs-lookup"><span data-stu-id="ed846-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ed846-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ed846-114">Requirements</span></span>  
 <span data-ttu-id="ed846-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ed846-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ed846-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ed846-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ed846-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ed846-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ed846-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ed846-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ed846-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="ed846-119">See Also</span></span>  
 
