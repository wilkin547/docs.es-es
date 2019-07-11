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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ce252f5a4b5fbcdbbc7b70c8b1c829490f8f63e5
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67739529"
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
  
|Member|DESCRIPCIÓN|  
|------------|-----------------|  
|`THREAD_RUN`|El subproceso se ejecuta de forma gratuita, a menos que se produce un evento de depuración.|  
|`THREAD_SUSPEND`|No se puede ejecutar el subproceso.|  
  
## <a name="remarks"></a>Comentarios  
 El depurador usa el `CorDebugThreadState` enumeración para controlar la ejecución de un subproceso. El estado de un subproceso puede establecerse mediante el [SetDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md) o [ICorDebugController:: SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md) método.  
  
 Una devolución de llamada proporcionada para el [API de hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md) permite la distribución de mensajes, por lo que no es necesario un estado interrumpido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
