---
title: ICorDebugType2::GetTypeID (método)
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
ms.openlocfilehash: 5bc1407f8444b78154981619742bd0da188c4335
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33422076"
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2::GetTypeID (método)
Obtiene un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `id`  
 [out] Un puntero a la [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) para este ICorDebugType.  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. El `HRESULT` códigos incluyen lo siguiente:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El método ha recuperado válido [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md).|  
|`CORDBG_E_CLASS_NOT_LOADED`|No se ha cargado el tipo.|  
|`CORDBG_E_UNSUPPORTED`|No se admite el tipo.|  
  
## <a name="remarks"></a>Comentarios  
 Este método proporciona una asignación desde el ICorDebugType, que representa un tipo que puede o que no se han cargado en el tiempo de ejecución a un [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), que actúa como opaco controlar que identifica un tipo de carga en el tiempo de ejecución.  
  
 Cuando el tipo que representa el ICorDebugType aún no se ha cargado, este método devuelve `CORDBG_E_CLASS_NOT_LOADED`.  Si no se admite el tipo, devuelve `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugType2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugtype2-interface.md)
