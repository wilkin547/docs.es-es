---
title: ICorDebugExceptionObjectCallStackEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 39dffa18-c71b-48c4-b11d-e814631ab1e9
topic_type:
- apiref
ms.openlocfilehash: 99a700270794ca92356cb9d134cb869d456199f9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73084426"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum (Interfaz)
Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Icordebugexceptionobjectcallstackenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)|Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugExceptionObjectCallStackEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugExceptionObjectCallStackEnum` se rellena con objetos [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) llamando al método [Icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
