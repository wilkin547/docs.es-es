---
title: ICorDebugObjectValue::GetClass (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugObjectValue.GetClass
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugObjectValue::GetClass
helpviewer_keywords:
- ICorDebugObjectValue::GetClass method [.NET Framework debugging]
- GetClass method, ICorDebugObjectValue interface [.NET Framework debugging]
ms.assetid: 5be25292-8357-445f-a09b-f997c0de761c
topic_type:
- apiref
ms.openlocfilehash: 4719f155957f04471d4ad2b8d71bec9c0f0d30c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73096097"
---
# <a name="icordebugobjectvaluegetclass-method"></a>ICorDebugObjectValue::GetClass (Método)
Obtiene la clase de este valor de objeto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetClass (  
    [out] ICorDebugClass     **ppClass  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppClass`  
 enuncia Puntero a la dirección de un objeto "ICorDebugClass" que representa la clase del valor del objeto representado por este objeto "ICorDebugObjectValue".  
  
## <a name="remarks"></a>Comentarios  
 Los métodos `GetClass` e [ICorDebugValue:: GetType](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue-gettype-method.md) devuelven información sobre el tipo de un valor. ambos se sustituyen por el [ICorDebugValue2:: GetExactType (](../../../../docs/framework/unmanaged-api/debugging/icordebugvalue2-getexacttype-method.md)compatible con genéricos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
