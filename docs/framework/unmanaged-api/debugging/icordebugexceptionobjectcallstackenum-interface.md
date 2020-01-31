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
ms.openlocfilehash: 9d98bccdfb83cec547b185693c28f25017d3225f
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782804"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum (Interfaz)
Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ICorDebugExceptionObjectCallStackEnum::Next](icordebugexceptionobjectcallstackenum-next-method.md)|Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorDebugExceptionObjectCallStackEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugExceptionObjectCallStackEnum` se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [Icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
- [Depuración](index.md)
