---
title: ICorDebugExceptionObjectCallStackEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugExceptionObjectCallStackEnum::Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next
helpviewer_keywords:
- ICorDebugExceptionObjectCallStackEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugExceptionObjectCallStackEnum interface [.NET Framework debugging]
ms.assetid: 3328a2c0-1e48-4a54-802a-9b474cf82c21
topic_type:
- apiref
ms.openlocfilehash: 6c742f541b358b40e6e2fd44ca437b0dd72e29b8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73091084"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a>ICorDebugExceptionObjectCallStackEnum::Next (Método)
Obtiene el número especificado de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) que contienen información de la pila de llamadas de un objeto de excepción.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] CorDebugExceptionObjectStackFrame values[],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `celt`  
 de El número de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) que se van a recuperar.  
  
 `values`  
 enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) .  
  
 `pceltFetched`  
 enuncia Un puntero al número de instancias de [cordebugexceptionobjectstackframe (](../../../../docs/framework/unmanaged-api/debugging/cordebugexceptionobjectstackframe-structure.md) devueltas realmente.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugExceptionObjectCallStackEnum (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugexceptionobjectcallstackenum-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
