---
title: ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectValue.EnumerateExceptionCallStack
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack
helpviewer_keywords:
- EnumerateExceptionCallStack method, ICorDebugExceptionObjectValue interface [.NET Framework debugging]
- ICorDebugExceptionObjectValue::EnumerateExceptionCallStack method [.NET Framework debugging]
ms.assetid: 00c64533-15dd-47f4-bb97-fe80a1ebadef
topic_type:
- apiref
ms.openlocfilehash: 101151469e2eece20afe289c9d95387ce6dc7c6a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672128"
---
# <a name="icordebugexceptionobjectvalueenumerateexceptioncallstack-method"></a>ICorDebugExceptionObjectValue::EnumerateExceptionCallStack (Método)

Obtiene un enumerador para la pila de llamadas incrustada en un objeto de excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateExceptionCallStack(  
    [out] ICorDebugExceptionObjectCallStackEnum **ppCallStackEnum  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 ppCallStackEnum  
 enuncia Un puntero a la dirección de un objeto de interfaz [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) que es un enumerador de seguimiento de pila para un objeto de excepción administrado.  
  
## <a name="remarks"></a>Comentarios  

 Si no hay información disponible sobre la pila de llamadas, el método devuelve `S_OK` y [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es un enumerador válido con una longitud de 0. Si el método no puede recuperar la información de seguimiento de la pila, el valor devuelto es `E_FAIL` y no se devuelve ningún enumerador.  
  
 El objeto [icordebugexceptionobjectcallstackenum (](icordebugexceptionobjectcallstackenum-interface.md) es responsable de descodificar los datos de seguimiento de la pila del `_stackTrace` campo del objeto de excepción.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugExceptionObjectValue (Interfaz)](icordebugexceptionobjectvalue-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
