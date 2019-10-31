---
title: ICorDebugProcess5::GetTypeForTypeID (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeForTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeForTypeID
helpviewer_keywords:
- GetTypeForTypeID method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeForTypeID method [.NET Framework debugging]
ms.assetid: e0eed5a8-fa6d-4818-bd00-7babcea30325
topic_type:
- apiref
ms.openlocfilehash: 39f5c1813b08f4d72c610820b1434e29eb4aec8e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121275"
---
# <a name="icordebugprocess5gettypefortypeid-method"></a>ICorDebugProcess5::GetTypeForTypeID (Método)
Convierte un identificador de tipo en un valor de ICorDebugType.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeForTypeID(  
    [in] COR_TYPEID id, [  
    out] ICorDebugType **ppType  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 de El identificador de tipo.  
  
 `ppType`  
 enuncia Puntero a la dirección de un objeto ICorDebugType.  
  
## <a name="remarks"></a>Comentarios  
 En algunos casos, los métodos que devuelven un identificador de tipo pueden devolver un valor de `COR_TYPEID` null. Si este valor se pasa como el argumento `id`, se producirá un error en el método `GetTypeForTypeID` y se devolverá `E_FAIL`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
