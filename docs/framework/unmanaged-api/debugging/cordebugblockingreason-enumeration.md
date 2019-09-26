---
title: CorDebugBlockingReason (Enumeración)
ms.date: 03/30/2017
api_name:
- CorDebugBlockingReason
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingReason
helpviewer_keywords:
- CorDebugBlockingReason enumeration [.NET Framework debugging]
ms.assetid: a6ac2531-ddfe-46fd-88fe-8b1eabe0b255
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 99fcf160b3e3b2b238520e3db5ba2e74b270380a
ms.sourcegitcommit: 3caa92cb97e9f6c31f21769c7a3f7c4304024b39
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/25/2019
ms.locfileid: "71274139"
---
# <a name="cordebugblockingreason-enumeration"></a>CorDebugBlockingReason (Enumeración)
Especifica los motivos por lo que un subproceso se puede bloquear en un objeto determinado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
Typedef enum CorDebugBlockingReason  
{  
   BLOCKING_NONE = 0  
   BLOCKING_MONITOR_CRITICAL_SECTION = 1  
   BLOCKING_MONITOR_EVENT = 2  
}  CorDebugBlockingReason;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`BLOCKING_NONE`|Solo para uso interno.|  
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Un subproceso está intentando adquirir la sección crítica asociada al bloqueo de monitor en un objeto. Normalmente, esto sucede cuando se llama a uno de <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> los <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType> métodos o.|  
|`BLOCKING_MONITOR_EVENT`|Un subproceso está esperando en el evento que está asociado a un bloqueo de monitor para un objeto. Normalmente, esto sucede cuando se llama a uno de <xref:System.Threading.Monitor?displayProperty=nameWithType> los `Wait` métodos.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando el `BLOCKING_MONITOR_CRITICAL_SECTION` miembro `BLOCKING_MONITOR_EVENT` o se usa en una estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , el `pBlockingObject` miembro de la estructura apunta a una interfaz "ICorDebugValue" que representa el objeto que se va a especificar. También se garantiza la implementación de la interfaz [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: Cordebug. idl, Cordebug. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
