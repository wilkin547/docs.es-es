---
description: 'Más información acerca de: CorDebugBlockingObject (estructura)'
title: CorDebugBlockingObject (Estructura)
ms.date: 03/30/2017
api_name:
- CorDebugBlockingObject Structure
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- CorDebugBlockingObject
helpviewer_keywords:
- CorDebugBlockingObject structure [.NET Framework debugging]
ms.assetid: 5944edd1-0914-4efa-aba0-d5a277c38b1a
topic_type:
- apiref
ms.openlocfilehash: 2b16af5eecb01067c2ee6811613f964af391f345
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712225"
---
# <a name="cordebugblockingobject-structure"></a>CorDebugBlockingObject (Estructura)

Define un objeto que está bloqueando un subproceso y el motivo concreto por el que el subproceso está bloqueado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
Typedef struct CorDebugBlockingObject  
{  
ICorDebugValue pBlockingObject;  
DWORD dwTimeout;  
CorDebugBlockingReason blockingReason;  
}  CorDebugBlockingObject;  
```  
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`pBlockingObject`|Objeto en el que el subproceso está bloqueando. Este objeto solo es válido para la duración del estado sincronizado actual. Si dos subprocesos se bloquean en el mismo objeto dentro del mismo estado sincronizado, puede esperar que el método [ICorDebugValue:: GetAddress](icordebugvalue-getaddress-method.md) devuelva el mismo valor. Sin embargo, las interfaces pueden o no ser equivalentes del puntero.|  
|`dwTimeout`|El número de milisegundos antes de que se agote el tiempo de espera de la operación de bloqueo o el valor infinito, lo que indica que no se agotará el tiempo de espera. El valor de tiempo de espera especifica la duración total de la operación de bloqueo, no el tiempo que todavía permanece.|  
|`blockingReason`|Motivo por el que el subproceso está bloqueado en este objeto.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cordebug. idl  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](debugging-structures.md)
- [Depuración](index.md)
