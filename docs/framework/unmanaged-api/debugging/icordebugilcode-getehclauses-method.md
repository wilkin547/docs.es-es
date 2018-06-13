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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8eca550130a22532cb781e09ec59c60c11a5ba33
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33416041"
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
  
#### <a name="parameters"></a>Parámetros  
 `cClauses`  
 [in] Capacidad de almacenamiento de la matriz `clauses`. Vea la sección Comentarios para obtener más información.  
  
 `pcClauses`  
 [out] Número de cláusulas para las cuales se escribe información en la matriz `clauses`.  
  
 clauses  
 [out] Una matriz de [CorDebugEHClause](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md) objetos que contienen información sobre las cláusulas definidas para este IL. de control de excepciones.  
  
## <a name="remarks"></a>Comentarios  
 Si `cClauses` es 0 y `pcClauses` no es**null**, `pcClauses` se establece en el número de cláusulas de control de excepciones disponible. Si `cClauses` no es cero, representa la capacidad de almacenamiento de la matriz `clauses`. Cuando el método vuelve, `clauses` contiene un máximo de elementos `cClauses` y `pcClauses` se establece en el número de cláusulas escritas realmente en la matriz `clauses`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugILCode (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode-interface.md)  
 [CorDebugEHClause (estructura)](../../../../docs/framework/unmanaged-api/debugging/cordebugehclause-structure.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
