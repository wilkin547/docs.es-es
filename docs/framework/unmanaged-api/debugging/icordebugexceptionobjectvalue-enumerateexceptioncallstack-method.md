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
ms.openlocfilehash: 9f54fdfe16bc24394503ba6f5a9b906a32ec2c8b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091103"
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
 enuncia Un puntero a la dirección de un objeto de interfaz [icordebugexceptionobjectcallstackenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) que es un enumerador de seguimiento de pila para un objeto de excepción administrado.  
  
## <a name="remarks"></a>Comentarios  
 Si no hay información disponible sobre la pila de llamadas, el método devuelve `S_OK`y [icordebugexceptionobjectcallstackenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) es un enumerador válido con una longitud de 0. Si el método no puede recuperar la información de seguimiento de la pila, el valor devuelto es `E_FAIL` y no se devuelve ningún enumerador.  
  
 El objeto [icordebugexceptionobjectcallstackenum (](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md) es responsable de descodificar los datos de seguimiento de la pila del campo `_stackTrace` del objeto de excepción.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugExceptionObjectValue (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectvalue-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
