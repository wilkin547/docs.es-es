---
title: ICorDebugILCode::GetEHClauses (Método)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode.GetEHClauses
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: cf7a0e00-06ae-47a5-8037-598b26196802
topic_type:
- apiref
ms.openlocfilehash: 38936a57944e9a0920c374f473c4cbe8e8d70abb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728672"
---
# <a name="icordebugilcodegetehclauses-method"></a>ICorDebugILCode::GetEHClauses (Método)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Devuelve un puntero a una lista de cláusulas de control de excepciones (EH) definidas para este lenguaje intermedio (IL).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetEHClauses(  
   [in] ULONG32 cClauses,  
   [out] ULONG32 * pcClauses,  
   [out, size_is(cClauses), length_is(*pcClauses)] CorDebugEHClause clauses[]);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cClauses`  
 [in] Capacidad de almacenamiento de la matriz `clauses`. Vea la sección Comentarios para obtener más información.  
  
 `pcClauses`  
 [out] Número de cláusulas para las cuales se escribe información en la matriz `clauses`.  
  
 cláusulas  
 enuncia Matriz de objetos [cordebugehclause (](cordebugehclause-structure.md) que contienen información sobre las cláusulas de control de excepciones definidas para este Il.  
  
## <a name="remarks"></a>Comentarios  

 Si `cClauses` es 0 y `pcClauses` no es **null**, `pcClauses` se establece en el número de cláusulas de control de excepciones disponibles. Si `cClauses` no es cero, representa la capacidad de almacenamiento de la matriz `clauses`. Cuando el método vuelve, `clauses` contiene un máximo de elementos `cClauses` y `pcClauses` se establece en el número de cláusulas escritas realmente en la matriz `clauses`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugILCode (Interfaz)](icordebugilcode-interface.md)
- [CorDebugEHClause (Estructura)](cordebugehclause-structure.md)
- [Interfaces para depuración](debugging-interfaces.md)
