---
description: 'Más información sobre: ICorDebugILCode:: Getehclauses ((método)'
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
ms.openlocfilehash: e790f0f1f69a38d3a1be9e98eacfc5e37be0fd05
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660666"
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
  
## <a name="remarks"></a>Observaciones  

 Si `cClauses` es 0 y `pcClauses` no es **null**, `pcClauses` se establece en el número de cláusulas de control de excepciones disponibles. Si `cClauses` no es cero, representa la capacidad de almacenamiento de la matriz `clauses`. Cuando el método vuelve, `clauses` contiene un máximo de elementos `cClauses` y `pcClauses` se establece en el número de cláusulas escritas realmente en la matriz `clauses`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugILCode (Interfaz)](icordebugilcode-interface.md)
- [CorDebugEHClause (Estructura)](cordebugehclause-structure.md)
- [Interfaces para depuración](debugging-interfaces.md)
