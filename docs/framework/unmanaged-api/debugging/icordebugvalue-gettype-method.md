---
title: ICorDebugValue::GetType (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugValue.GetType
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugValue::GetType
helpviewer_keywords:
- ICorDebugValue::GetType method [.NET Framework debugging]
- GetType method, ICorDebugValue interface [.NET Framework debugging]
ms.assetid: 41e2d503-e1f1-407b-abe0-6a29adb3e0d1
topic_type:
- apiref
ms.openlocfilehash: 284a74823b01305f8c6e025f70bb9209c8607b7b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73137075"
---
# <a name="icordebugvaluegettype-method"></a>ICorDebugValue::GetType (Método)
Obtiene el tipo primitivo de este objeto "ICorDebugValue".  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetType (  
    [out] CorElementType   *pType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pType`  
 enuncia Un puntero a un valor de la enumeración "CorElementType" que indica el tipo del valor.  
  
## <a name="remarks"></a>Comentarios  
 Si el objeto es un tipo complejo en tiempo de ejecución, ese tipo se puede examinar en las subclases adecuadas de la interfaz `ICorDebugValue`. Por ejemplo, "ICorDebugObjectValue", que hereda de `ICorDebugValue`, representa un tipo complejo.  
  
 Los métodos `GetType` e [ICorDebugObjectValue:: GetClass](../../../../docs/framework/unmanaged-api/debugging/icordebugobjectvalue-getclass-method.md) devuelven información sobre el tipo de un valor. Ambos se sustituyen por el método [ICorDebugValue2:: GetExactType (](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md) compatible con genéricos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
