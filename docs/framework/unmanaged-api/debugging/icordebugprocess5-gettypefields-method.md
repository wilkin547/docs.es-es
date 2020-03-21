---
title: ICorDebugProcess5::GetTypeFields (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeFields
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeFields
helpviewer_keywords:
- GetTypeFields method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::GetTypeFields method [.NET Framework debugging]
ms.assetid: 6a0ad3ee-dacb-47e9-abae-4536bcc4804b
topic_type:
- apiref
ms.openlocfilehash: 29006eba3d3a523fd24a461207ab12222a639782
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178591"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields (Método)
Proporciona información sobre los campos que pertenecen a un tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 [en] Identificador del tipo cuya información de campo se recupera.  
  
 `celt`  
 [en] El número de [objetos COR_FIELD](cor-field-structure.md) cuya información de campo se va a recuperar.  
  
 `fields`  
 [fuera] Matriz de [objetos COR_FIELD](cor-field-structure.md) que proporcionan información sobre los campos que pertenecen al tipo.  
  
 `pceltNeeded`  
 [fuera] Puntero al número de [objetos COR_FIELD](cor-field-structure.md) incluidos en `fields`.  
  
## <a name="remarks"></a>Observaciones  
 El `celt` parámetro, que especifica el número de campos cuya `fields`información de campo utiliza `COR_TYPE_LAYOUT::numFields` el método para rellenar , debe corresponder al valor del campo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
