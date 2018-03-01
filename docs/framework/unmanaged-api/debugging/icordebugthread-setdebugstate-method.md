---
title: "ICorDebugThread::SetDebugState (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICorDebugThread.SetDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugThread::SetDebugState
helpviewer_keywords:
- ICorDebugThread::SetDebugState method [.NET Framework debugging]
- SetDebugState method [.NET Framework debugging]
ms.assetid: 6382bdf6-d488-4952-b653-cb09b6e1c6c2
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: f2754caf11f89358b3e81e6324835d5b2e12f17e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState (Método)
Establece marcas que describen el estado de depuración de esta instancia de ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `state`  
 [in] Una combinación bit a bit de valores de enumeración CorDebugThreadState que especifican el estado de depuración de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 `SetDebugState`establece el estado de depuración actual del subproceso. (El "estado de depuración actual" representa el estado de depuración si el proceso puede continuar, no el estado actual real). El valor normal para esto es THREAD_RUNNING. Sólo el depurador puede afectar el estado de depuración de un subproceso. Estados de depuración durante las continuaciones, por lo que si desea mantener un subproceso THREAD_SUSPENDed en varias continuaciones, puede establecerlo una vez y después no tienen que preocuparse sobre él. Subprocesos de suspender y reanudar el proceso pueden causar interbloqueos, aunque es poco probable que normalmente. Esto es una cualidad intrínseca de subprocesos y procesos y es por diseño. Un depurador asincrónicamente puede interrumpir y reanudar los subprocesos para romper el interbloqueo. Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, a continuación, el subproceso puede bloquear una colección de elementos no utilizados (GC). Esto significa que el subproceso suspendido tiene una probabilidad mucho más alta de producir un interbloqueo. Esto puede no afectar al depurar eventos ya está en cola. Por lo tanto, un depurador debe purgar la cola de eventos completa (mediante una llamada a [ICorDebugController:: HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar subprocesos. Else pueden obtener los eventos en un subproceso que cree que ya ha suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
