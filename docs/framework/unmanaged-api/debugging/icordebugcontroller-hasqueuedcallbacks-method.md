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
ms.openlocfilehash: bd656445c2451d0583ddbc45e71c9e090bb80305
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2020
ms.locfileid: "82892778"
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks (Método)
Obtiene un valor que indica si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pThread`  
 de Un puntero a un objeto "ICorDebugThread" que representa el subproceso.  
  
 `pbQueued`  
 enuncia Un puntero a un valor que es `true` si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado; en caso `false`contrario,.  
  
 Si se especifica null para el `pThread` parámetro, `HasQueuedCallbacks` devolverá `true` si hay devoluciones de llamada actualmente administradas en cola para cualquier subproceso.  
  
## <a name="remarks"></a>Observaciones  
 Las devoluciones de llamada se enviarán de una en una, cada vez que se llame a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) . El depurador puede comprobar esta marca si desea notificar varios eventos de depuración que se producen simultáneamente.  
  
 Cuando se ponen en cola los eventos de depuración, ya se han producido, por lo que el depurador debe agotar toda la cola para estar seguro del estado de la depuración. (Llame `ICorDebugController::Continue` a para purgar la cola). Por ejemplo, si la cola contiene dos eventos de depuración en el subproceso *x*y el depurador suspende el subproceso *x* después del primer evento `ICorDebugController::Continue`de depuración y, a continuación, llama a, se enviará el segundo evento de depuración para el subproceso *x* , aunque el subproceso se haya suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también
