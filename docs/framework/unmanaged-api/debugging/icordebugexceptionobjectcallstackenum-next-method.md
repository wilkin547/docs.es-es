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
ms.openlocfilehash: 6fce9f61e222d0fc1763495de162a94a7fc22689
ms.sourcegitcommit: fff146ba3fd1762c8c432d95c8b877825ae536fc
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/08/2020
ms.locfileid: "82975984"
---
# <a name="icordebugexceptionobjectcallstackenumnext-method"></a>ICorDebugExceptionObjectCallStackEnum::Next (Método)
Obtiene el número especificado de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que contienen información de la pila de llamadas de un objeto de excepción.  
  
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
 de El número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) que se van a recuperar.  
  
 `values`  
 enuncia Una matriz de punteros, cada uno de los cuales apunta a un objeto [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) .  
  
 `pceltFetched`  
 enuncia Un puntero al número de instancias de [cordebugexceptionobjectstackframe (](cordebugexceptionobjectstackframe-structure.md) devueltas realmente.  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugExceptionObjectCallStackEnum (Interfaz)](icordebugexceptionobjectcallstackenum-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
