---
title: ICorDebugValue Interfaz1
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0fe53490014a2a7d9acc0a426613af54867599e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422128"
---
# <a name="icordebugvalue-interface1"></a>ICorDebugValue Interfaz1
Representa un valor en el proceso que se está depurando. El valor puede ser un valor de escritura o lectura.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateBreakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-createbreakpoint-method.md)|Este método no está implementado actualmente.|  
|[GetAddress (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getaddress-method.md)|Obtiene la dirección de este `ICorDebugValue` objeto, que se está depurando.|  
|[GetSize (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-getsize-method.md)|Obtiene el tamaño, en bytes, de este `ICorDebugValue` objeto.|  
|[GetType (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md)|Obtiene el tipo primitivo de este `ICorDebugValue` objeto.|  
  
## <a name="remarks"></a>Comentarios  
 En general, la propiedad de un objeto de valor se pasa cuando se devuelve. El destinatario es responsable de quitar una referencia del objeto cuando haya terminado con el objeto.  
  
 Dependiendo de dónde se recupera el valor de, el valor puede no sigue siendo válido después de que se reanude el proceso. Por lo tanto, en general, el valor no debe ser mantenido a lo largo de una llamada de la [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) método.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
    
    
    
    
 [ICorDebugValue3 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue3-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
