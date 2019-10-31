---
title: ICorDebugValue (Interfaz)
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
ms.openlocfilehash: 77d28d8eef97a934c15ac29725f856f4bf39e6ce
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140159"
---
# <a name="icordebugvalue-interface"></a>ICorDebugValue (Interfaz)
Representa un valor en el proceso que se está depurando. El valor puede ser un valor de lectura o de escritura.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Este método no está implementado actualmente.|  
|[GetAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Obtiene la dirección de este objeto `ICorDebugValue`, que se encuentra en el proceso de depuración.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue`.|  
|[GetType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Obtiene el tipo primitivo de este objeto `ICorDebugValue`.|  
  
## <a name="remarks"></a>Comentarios  
 En general, la propiedad de un objeto de valor se pasa cuando se devuelve. El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.  
  
 Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso. Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
