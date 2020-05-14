---
title: Interfaz ICorDebugValue
ms.date: 03/30/2017
api_name:
- ICorDebugValue
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue
helpviewer_keywords:
- ICorDebugValue interface [.NET Framework debugging]
ms.assetid: b2f7007f-c446-4b18-aed1-a25cff8aee31
topic_type:
- apiref
ms.openlocfilehash: b8d2e49031e59db0527de3c848d7d390095797bf
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396788"
---
# <a name="icordebugvalue-interface"></a>Interfaz ICorDebugValue
Representa un valor en el proceso que se está depurando. El valor puede ser un valor de lectura o de escritura.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateBreakpoint](icordebugvalue-createbreakpoint-method.md)|Este método no se encuentra implementado actualmente.|  
|[Método GetAddress](icordebugvalue-getaddress-method.md)|Obtiene la dirección de este `ICorDebugValue` objeto, que se encuentra en el proceso de depuración.|  
|[Método GetSize](icordebugvalue-getsize-method.md)|Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.|  
|[Método GetType](icordebugvalue-gettype-method.md)|Obtiene el tipo primitivo de este `ICorDebugValue` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 En general, la propiedad de un objeto de valor se pasa cuando se devuelve. El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.  
  
 Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso. Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugValue3 (Interfaz)](icordebugvalue3-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
