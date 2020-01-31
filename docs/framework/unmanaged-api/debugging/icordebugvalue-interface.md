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
ms.openlocfilehash: e1044386bd6251132703c4e98a0cf2ed267d34e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791138"
---
# <a name="icordebugvalue-interface"></a>Interfaz ICorDebugValue
Representa un valor en el proceso que se está depurando. El valor puede ser un valor de lectura o de escritura.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](icordebugvalue-createbreakpoint-method.md)|Este método no se encuentra implementado actualmente.|  
|[GetAddress (método)](icordebugvalue-getaddress-method.md)|Obtiene la dirección de este objeto `ICorDebugValue`, que se encuentra en el proceso de depuración.|  
|[GetSize (método)](icordebugvalue-getsize-method.md)|Obtiene el tamaño, en bytes, de este objeto `ICorDebugValue`.|  
|[GetType (método)](icordebugvalue-gettype-method.md)|Obtiene el tipo primitivo de este objeto `ICorDebugValue`.|  
  
## <a name="remarks"></a>Notas  
 En general, la propiedad de un objeto de valor se pasa cuando se devuelve. El destinatario es responsable de quitar una referencia del objeto cuando ha terminado con el objeto.  
  
 Dependiendo de dónde se haya recuperado el valor, es posible que el valor no siga siendo válido después de que se reanude el proceso. Por lo tanto, en general, el valor no se debe mantener en una llamada del método [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) .  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugValue3 (interfaz)](icordebugvalue3-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
