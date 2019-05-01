---
title: 'Icordebugtype2:: GetTypeId (método)'
ms.date: 03/30/2017
api_name:
- ICorDebugType2.GetTypeID
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugType::GetTypeID
helpviewer_keywords:
- GetTypeID method, ICorDebugType2 interface [.NET Framework debugging]
- ICorDebugType2.GetTypeID method [.NET Framework debugging]
ms.assetid: 0b933686-226e-4373-92b7-fac579ee7b1a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2b19efdedc21f66e4692ce1850eb3947f856e436
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61993803"
---
# <a name="icordebugtype2gettypeid-method"></a>Icordebugtype2:: GetTypeId (método)
Obtiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 [out] Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para esta instancia de ICorDebugType.  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. El `HRESULT` códigos incluyen lo siguiente:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El método ha recuperado válido [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|El tipo no se ha cargado.|  
|`CORDBG_E_UNSUPPORTED`|No se admite el tipo.|  
  
## <a name="remarks"></a>Comentarios  
 Este método proporciona una asignación de ICorDebugType, que representa un tipo que puede o es posible que no se han cargado en el tiempo de ejecución a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), controlar que actúa como opaco que identifica un tipo que se cargan en el tiempo de ejecución.  
  
 Cuando el tipo que representa la instancia de ICorDebugType aún no se ha cargado, este método devuelve `CORDBG_E_CLASS_NOT_LOADED`.  Si no se admite el tipo, devuelve `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugType2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
