---
title: "ICorDebugController::HasQueuedCallbacks (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.HasQueuedCallbacks
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::HasQueuedCallbacks
helpviewer_keywords:
- HasQueuedCallbacks method [.NET Framework debugging]
- ICorDebugController::HasQueuedCallbacks method [.NET Framework debugging]
ms.assetid: 0d6a1cd9-370b-4462-adbf-e3980e897ea7
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 03d52bb31a81876a00e1af33494b14fb99fee0fa
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugcontrollerhasqueuedcallbacks-method"></a>ICorDebugController::HasQueuedCallbacks (Método)
Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT HasQueuedCallbacks (  
    [in] ICorDebugThread *pThread,  
    [out] BOOL           *pbQueued  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pThread`  
 [in] Un puntero a un objeto de "ICorDebugThread" que representa el subproceso.  
  
 `pbQueued`  
 [out] Un puntero a un valor que es `true` si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado; en caso contrario, `false`.  
  
 Si se especifica null para la `pThread` parámetro, `HasQueuedCallbacks` devolverá `true` si actualmente no hay devoluciones de llamada administradas en la cola para cualquier subproceso.  
  
## <a name="remarks"></a>Comentarios  
 Las devoluciones de llamada será enviado a la vez, cada vez que [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) se llama. El depurador puede comprobar este marcador si desea informar de varios eventos de depuración que se producen al mismo tiempo.  
  
 Cuando se ponen en cola los eventos de depuración, hayan podido, por lo que el depurador debe vaciar la cola completa para estar seguro del estado del código depurado. (Llame a `ICorDebugController::Continue` para purgar la cola.) Por ejemplo, si la cola contiene dos eventos de depuración en el subproceso *X*, y el depurador suspende el subproceso *X* después del primer evento de depuración y, a continuación, llamadas `ICorDebugController::Continue`, el segundo evento de depuración para subproceso *X* se enviarán aunque se ha suspendido el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
