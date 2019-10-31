---
title: CorDebugThreadState (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugThreadState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugThreadState
helpviewer_keywords:
- CorDebugThreadState enumeration [.NET Framework debugging]
ms.assetid: a3ccdf18-4ec6-494d-9024-48e5c8c724f5
topic_type:
- apiref
ms.openlocfilehash: 1ff36e8ef6b7c02eea5b02bc22587bc3889df093
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133689"
---
# <a name="cordebugthreadstate-enumeration"></a>CorDebugThreadState (Enumeración)
Especifica el estado de un subproceso de depuración.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum CorDebugThreadState {  
    THREAD_RUN,  
    THREAD_SUSPEND  
} CorDebugThreadState;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`THREAD_RUN`|El subproceso se ejecuta libremente, a menos que se produzca un evento de depuración.|  
|`THREAD_SUSPEND`|No se puede ejecutar el subproceso.|  
  
## <a name="remarks"></a>Comentarios  
 El depurador utiliza la enumeración `CorDebugThreadState` para controlar la ejecución de un subproceso. El estado de un subproceso se puede establecer mediante el método [ICorDebugThread:: setdebugstate (](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: setallthreadsdebugstate (](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) .  
  
 Una devolución de llamada proporcionada a la [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite el suministro de mensajes, por lo que no se necesita un estado interrumpido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
