---
title: ICorDebugThread::SetDebugState (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 66f60b2342b6ff64f1329cbe57032291d5139384
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67770592"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState (Método)
Establece las marcas que describen el estado de depuración de este ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `state`  
 [in] Una combinación bit a bit de valores de enumeración CorDebugThreadState que especifican el estado de depuración de este subproceso.  
  
## <a name="remarks"></a>Comentarios  
 `SetDebugState` establece el estado de depuración actual del subproceso. (El "estado de depuración actual" representa el estado de depuración si el proceso se puede continuar, no el estado actual real). El valor normal es THREAD_RUNNING. Solo el depurador puede afectar el estado de depuración de un subproceso. Estados de depuración continuaciones, por lo que si desea mantener un subproceso THREAD_SUSPENDed en varias continuaciones, puede configurarla una vez y no volver a preocuparse. Subprocesos de suspender y reanudar el proceso pueden provocar interbloqueos, aunque es poco probable que normalmente. Esto es una cualidad intrínseca de procesos y subprocesos y es por diseño. Forma asincrónica, un depurador puede interrumpir y reanudar los subprocesos para interrumpir el interbloqueo. Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, el subproceso puede bloquear una colección de elementos no utilizados (GC). Esto significa que el subproceso suspendido tiene una probabilidad mucho más alta de producir un interbloqueo. Esto puede no afectar a ya está en cola los eventos de depuración. Por lo tanto, un depurador debe purgar la cola de eventos completo (mediante una llamada a [HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar subprocesos. Lo contrario, pueden obtener los eventos de un subproceso que cree que ya ha suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
