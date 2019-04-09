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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7c2725c62105e92996bb2d8e79e8ff504904e9c7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107957"
---
# <a name="icordebugprocess5gettypefields-method"></a>ICorDebugProcess5::GetTypeFields (Método)
Proporciona información sobre los campos que pertenecen a un tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeFields(  
    [in] COR_TYPEID id,  
    [in] ULONG32 celt,  
    [out] COR_FIELD fields[],   
    [out] ULONG32 *pceltNeeded  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 [in] El identificador del tipo cuya información de campo se recupera.  
  
 `celt`  
 [in] El número de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos cuya información de campo que se va a recuperar.  
  
 `fields`  
 [out] Una matriz de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos que proporcionan información sobre los campos que pertenecen al tipo.  
  
 `pceltNeeded`  
 [out] Un puntero al número de [COR_FIELD](../../../../docs/framework/unmanaged-api/debugging/cor-field-structure.md) objetos incluidos en `fields`.  
  
## <a name="remarks"></a>Comentarios  
 El `celt` parámetro, que especifica el número de campos cuya información de campo, el método se usa para rellenar `fields`, debe corresponder al valor de la `COR_TYPE_LAYOUT::numFields` campo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugProcess5 (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
