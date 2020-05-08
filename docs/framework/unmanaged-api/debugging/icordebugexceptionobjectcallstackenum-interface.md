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
ms.openlocfilehash: e6dd951b0f432d455d95bb60f4c42df64d5bee24
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975997"
---
# <a name="icordebugexceptionobjectcallstackenum-interface"></a>ICorDebugExceptionObjectCallStackEnum (Interfaz)
Proporciona un enumerador para la información de la pila de llamadas que está incrustada en un objeto de excepción. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)|Obtiene un número especificado de objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información sobre la pila de llamadas de un objeto de excepción.|  
  
## <a name="remarks"></a>Observaciones  
 La `ICorDebugExceptionObjectCallStackEnum` interfaz implementa la interfaz ICorDebugEnum.  
  
 Una `ICorDebugExceptionObjectCallStackEnum` instancia se rellena con objetos [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) llamando al método [icordebugexceptionobjectvalue (:: enumerateexceptioncallstack (](icordebugexceptionobjectvalue-enumerateexceptioncallstack-method.md) . Los elementos de la pila de llamadas de la colección se pueden enumerar llamando al método [icordebugexceptionobjectcallstackenum (:: Next](icordebugexceptionobjectcallstackenum-next-method.md)  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
