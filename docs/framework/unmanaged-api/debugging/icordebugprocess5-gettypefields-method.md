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
ms.openlocfilehash: 644b5ed751caaf1809250244b37badc8037b0f57
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792355"
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
  
## <a name="parameters"></a>Parameters  
 `id`  
 de Identificador del tipo cuya información de campo se recupera.  
  
 `celt`  
 de El número de objetos de [COR_FIELD](cor-field-structure.md) cuya información de campo se va a recuperar.  
  
 `fields`  
 enuncia Matriz de objetos [COR_FIELD](cor-field-structure.md) que proporcionan información sobre los campos que pertenecen al tipo.  
  
 `pceltNeeded`  
 enuncia Puntero al número de objetos [COR_FIELD](cor-field-structure.md) incluidos en `fields`.  
  
## <a name="remarks"></a>Notas  
 El parámetro `celt`, que especifica el número de campos cuya información de campo utiliza el método para rellenar `fields`, debe corresponder al valor del campo `COR_TYPE_LAYOUT::numFields`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](icordebugprocess5-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
