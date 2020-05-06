---
title: CorDebugUserState (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugUserState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugUserState
helpviewer_keywords:
- CorDebugUserState enumeration [.NET Framework debugging]
ms.assetid: 5f6c2bcd-8102-4e3b-abc5-86ab0bd62def
topic_type:
- apiref
ms.openlocfilehash: d502b4098016fb14793bccd6feb641e92e3c2611
ms.sourcegitcommit: de7f589de07a9979b6ac28f54c3e534a617d9425
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2020
ms.locfileid: "82795643"
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState (Enumeración)
Indica el estado de uso de un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugUserState {  
    USER_STOP_REQUESTED     =  0x01,  
    USER_SUSPEND_REQUESTED  =  0x02,  
    USER_BACKGROUND         =  0x04,  
    USER_UNSTARTED          =  0x08,  
    USER_STOPPED            =  0x10,  
    USER_WAIT_SLEEP_JOIN    =  0x20,  
    USER_SUSPENDED          =  0x40,  
    USER_UNSAFE_POINT       =  0x80,  
    USER_THREADPOOL         = 0x100  
} CorDebugUserState;  
```  
  
## <a name="members"></a>Members  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Se ha solicitado una terminación del subproceso.|  
|`USER_SUSPEND_REQUESTED`|Se ha solicitado una suspensión del subproceso.|  
|`USER_BACKGROUND`|El subproceso se ejecuta en segundo plano.|  
|`USER_UNSTARTED`|El subproceso no ha empezado a ejecutarse.|  
|`USER_STOPPED`|El subproceso ha finalizado.|  
|`USER_WAIT_SLEEP_JOIN`|El subproceso está esperando a que otro subproceso complete una tarea.|  
|`USER_SUSPENDED`|El subproceso se ha suspendido.|  
|`USER_UNSAFE_POINT`|El subproceso está en un punto no seguro. Es decir, el subproceso está en un punto de la ejecución donde puede bloquear la recolección de elementos no utilizados.<br /><br /> Los eventos de depuración se pueden enviar desde puntos no seguros, pero si se suspende un subproceso en un punto no seguro, es muy probable que se produzca un interbloqueo hasta que se reanude el subproceso. Los puntos Safe y Unsafe se determinan mediante la implementación Just-in-Time (JIT) y la recolección de elementos no utilizados.|  
|`USER_THREADPOOL`|El subproceso procede del grupo de subprocesos.|  
  
## <a name="remarks"></a>Comentarios  
 El estado de usuario de un subproceso es el estado que tiene el subproceso cuando el depurador lo examina. Un subproceso puede tener una combinación de Estados de usuario.  
  
 Use el método [ICorDebugThread:: getuserstate (](icordebugthread-getuserstate-method.md) para recuperar el estado de usuario de un subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
