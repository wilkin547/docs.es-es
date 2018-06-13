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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f489ab29726292f6c55151169ad9efc6f0fbfbcf
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33407799"
---
# <a name="cordebuguserstate-enumeration"></a>CorDebugUserState (Enumeración)
Indica el estado de uso de un subproceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
## <a name="members"></a>Miembros  
  
|Valor|Descripción|  
|-----------|-----------------|  
|`USER_STOP_REQUESTED`|Se ha solicitado una finalización del subproceso.|  
|`USER_SUSPEND_REQUESTED`|Se ha solicitado una suspensión del subproceso.|  
|`USER_BACKGROUND`|Se está ejecutando el subproceso en segundo plano.|  
|`USER_UNSTARTED`|El subproceso no ha iniciado la ejecución.|  
|`USER_STOPPED`|El subproceso ha terminado.|  
|`USER_WAIT_SLEEP_JOIN`|El subproceso está esperando a otro subproceso completar una tarea.|  
|`USER_SUSPENDED`|Se ha suspendido el subproceso.|  
|`USER_UNSAFE_POINT`|El subproceso está en un punto no seguro. Es decir, el subproceso está en un punto de ejecución donde puede bloquear la colección de elementos no utilizados.<br /><br /> Depurar eventos se pueden enviar desde puntos no seguros, pero la suspensión de un subproceso en un punto no seguro provocará muy probablemente un interbloqueo hasta que se reanuda el subproceso. Los puntos seguros y se determinan por el just-in-time (JIT) y la implementación de la colección de elementos no utilizados.|  
|`USER_THREADPOOL`|Es el subproceso del grupo de subprocesos.|  
  
## <a name="remarks"></a>Comentarios  
 El estado de usuario de un subproceso es el estado que tiene el subproceso cuando lo examina el depurador. Un subproceso puede tener una combinación de Estados de usuario.  
  
 Use la [ICorDebugThread:: GetUserState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md) método para recuperar el estado de usuario de un subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
