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
ms.openlocfilehash: bc488e55bf64468eb62e2dc6eaedca62ebde3310
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73098983"
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
|`BLOCKING_MONITOR_CRITICAL_SECTION`|Un subproceso está intentando adquirir la sección crítica asociada al bloqueo de monitor en un objeto. Normalmente, esto sucede cuando se llama a uno de los métodos <xref:System.Threading.Monitor.Enter%2A?displayProperty=nameWithType> o <xref:System.Threading.Monitor.TryEnter%2A?displayProperty=nameWithType>.|  
|`BLOCKING_MONITOR_EVENT`|Un subproceso está esperando en el evento que está asociado a un bloqueo de monitor para un objeto. Normalmente, esto sucede cuando se llama a uno de los métodos de `Wait` de <xref:System.Threading.Monitor?displayProperty=nameWithType>.|  
  
## <a name="remarks"></a>Comentarios  
 Cuando se utiliza el miembro `BLOCKING_MONITOR_CRITICAL_SECTION` o `BLOCKING_MONITOR_EVENT` en una estructura [CorDebugBlockingObject](cordebugblockingobject-structure.md) , el miembro `pBlockingObject` de la estructura apunta a una interfaz "ICorDebugValue" que representa el objeto que se va a especificar. También se garantiza la implementación de la interfaz [ICorDebugHeapValue3](icordebugheapvalue3-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones de depuración](debugging-enumerations.md)
- [Depuración](index.md)
