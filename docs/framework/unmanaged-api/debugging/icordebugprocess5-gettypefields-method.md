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
ms.openlocfilehash: 0045285a3da22f468c2426bb3b9c4ae7e3e1d7c7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132670"
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
 de Identificador del tipo cuya información de campo se recupera.  
  
 `celt`  
 de El número de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) cuya información de campo se va a recuperar.  
  
 `fields`  
 enuncia Matriz de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) que proporcionan información sobre los campos que pertenecen al tipo.  
  
 `pceltNeeded`  
 enuncia Puntero al número de objetos [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) incluidos en `fields`.  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `celt`, que especifica el número de campos cuya información de campo utiliza el método para rellenar `fields`, debe corresponder al valor del campo `COR_TYPE_LAYOUT::numFields`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
