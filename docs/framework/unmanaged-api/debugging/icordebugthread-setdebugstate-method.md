---
description: 'Más información acerca de: ICorDebugThread:: Setdebugstate ((método)'
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
ms.openlocfilehash: 40339cbce8d30617738151c0a32466c2361e3a14
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99658807"
---
# <a name="icordebugthreadsetdebugstate-method"></a>ICorDebugThread::SetDebugState (Método)

Establece marcas que describen el estado de depuración de esta ICorDebugThread.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetDebugState (  
    [in] CorDebugThreadState state  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `state`  
 de Combinación bit a bit de los valores de enumeración CorDebugThreadState (que especifican el estado de depuración de este subproceso.  
  
## <a name="remarks"></a>Observaciones  

 `SetDebugState` establece el estado de depuración actual del subproceso. (El "estado de depuración actual" representa el estado de depuración si se va a continuar el proceso, no el estado actual real). El valor normal es THREAD_RUN. Solo el depurador puede afectar al estado de depuración de un subproceso. Los Estados de depuración continúan en el pasado, por lo que si desea mantener una THREAD_SUSPENDed de subprocesos en varias continuaciones, puede establecerla una vez y, a partir de ese momento, no tendrá que preocuparse por ella. La suspensión de subprocesos y la reanudación del proceso pueden provocar interbloqueos, aunque normalmente es improbable. Se trata de una calidad intrínseca de subprocesos y procesos y es por diseño. Un depurador puede interrumpir y reanudar asincrónicamente los subprocesos para interrumpir el interbloqueo. Si el estado de usuario del subproceso incluye USER_UNSAFE_POINT, el subproceso puede bloquear una recolección de elementos no utilizados (GC). Esto significa que el subproceso suspendido tiene una probabilidad mucho mayor de provocar un interbloqueo. Esto puede no afectar a los eventos de depuración ya en cola. Por lo tanto, un depurador debe purgar toda la cola de eventos (llamando a [ICorDebugController:: HasQueuedCallbacks (](icordebugcontroller-hasqueuedcallbacks-method.md)) antes de suspender o reanudar los subprocesos. En caso contrario, puede recibir eventos en un subproceso que cree que ya se ha suspendido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
