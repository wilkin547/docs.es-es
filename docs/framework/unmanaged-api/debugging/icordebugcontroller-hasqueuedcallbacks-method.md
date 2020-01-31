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
ms.openlocfilehash: c33193bd64030852441c7ca60cee4a000b09156c
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788922"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a><span data-ttu-id="3c356-102">ICorDebugController::HasQueuedCallbacks (Método)</span><span class="sxs-lookup"><span data-stu-id="3c356-102">ICorDebugController::HasQueuedCallbacks Method</span></span>
<span data-ttu-id="3c356-103">Obtiene un valor que indica si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado.</span><span class="sxs-lookup"><span data-stu-id="3c356-103">Gets a value that indicates whether any managed callbacks are currently queued for the specified thread.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3c356-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3c356-104">Syntax</span></span>  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3c356-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="3c356-105">Parameters</span></span>  
 `pThread`  
 <span data-ttu-id="3c356-106">de Un puntero a un objeto "ICorDebugThread" que representa el subproceso.</span><span class="sxs-lookup"><span data-stu-id="3c356-106">[in] A pointer to an "ICorDebugThread" object that represents the thread.</span></span>  
  
 `pbQueued`  
 <span data-ttu-id="3c356-107">enuncia Puntero a un valor que se `true` si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="3c356-107">[out] A pointer to a value that is `true` if any managed callbacks are currently queued for the specified thread; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="3c356-108">Si se especifica null para el parámetro `pThread`, `HasQueuedCallbacks` devolverá `true` si hay devoluciones de llamada actualmente administradas en cola para cualquier subproceso.</span><span class="sxs-lookup"><span data-stu-id="3c356-108">If null is specified for the `pThread` parameter, `HasQueuedCallbacks` will return `true` if there are currently managed callbacks queued for any thread.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3c356-109">Notas</span><span class="sxs-lookup"><span data-stu-id="3c356-109">Remarks</span></span>  
 <span data-ttu-id="3c356-110">Las devoluciones de llamada se enviarán de una en una, cada vez que se llame a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .</span><span class="sxs-lookup"><span data-stu-id="3c356-110">Callbacks will be dispatched one at a time, each time [ICorDebugController::Continue](icordebugcontroller-continue-method.md) is called.</span></span> <span data-ttu-id="3c356-111">El depurador puede comprobar esta marca si desea notificar varios eventos de depuración que se producen simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="3c356-111">The debugger can check this flag if it wants to report multiple debugging events that occur simultaneously.</span></span>  
  
 <span data-ttu-id="3c356-112">Cuando se ponen en cola los eventos de depuración, ya se han producido, por lo que el depurador debe agotar toda la cola para estar seguro del estado de la depuración.</span><span class="sxs-lookup"><span data-stu-id="3c356-112">When debugging events are queued, they have already occurred, so the debugger must drain the entire queue to be sure of the state of the debuggee.</span></span> <span data-ttu-id="3c356-113">(Llame `ICorDebugController::Continue` para purgar la cola). Por ejemplo, si la cola contiene dos eventos de depuración en el subproceso *x*, y el depurador suspende el subproceso *x* después del primer evento de depuración y, a continuación, llama a `ICorDebugController::Continue`, se enviará el segundo evento de depuración para el subproceso *x* , aunque el subproceso se haya suspendido.</span><span class="sxs-lookup"><span data-stu-id="3c356-113">(Call `ICorDebugController::Continue` to drain the queue.) For example, if the queue contains two debugging events on thread *X*, and the debugger suspends thread *X* after the first debugging event and then calls `ICorDebugController::Continue`, the second debugging event for thread *X* will be dispatched although the thread has been suspended.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3c356-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="3c356-114">Requirements</span></span>  
 <span data-ttu-id="3c356-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c356-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c356-116">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3c356-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3c356-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c356-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c356-118">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c356-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c356-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c356-119">See also</span></span>
