---
title: 'ICorDebugType2:: GetTypeID (método)'
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
ms.openlocfilehash: 631f605fd18559b36071964e35a15761cd4c8228
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791226"
---
# <a name="icordebugtype2gettypeid-method"></a>ICorDebugType2:: GetTypeID (método)
Obtiene un [COR_TYPEID](cor-typeid-structure.md) para este tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeID(  
    ([out] COR_TYPEID *id  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `id`  
 enuncia Puntero a la [COR_TYPEID](cor-typeid-structure.md) para esta ICorDebugType.  
  
## <a name="return-value"></a>Valor devuelto  
 El valor devuelto es `S_OK` si se realiza correctamente, o un código de error `HRESULT` en caso contrario. Entre los códigos de `HRESULT` se incluyen los siguientes:  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|`S_OK`|El método se realizó correctamente. El método ha recuperado un [COR_TYPEID](cor-typeid-structure.md)válido.|  
|`CORDBG_E_CLASS_NOT_LOADED`|No se ha cargado el tipo.|  
|`CORDBG_E_UNSUPPORTED`|El tipo no se admite.|  
  
## <a name="remarks"></a>Notas  
 Este método proporciona una asignación de la ICorDebugType, que representa un tipo que se puede o no haber cargado en el tiempo de ejecución, en una [COR_TYPEID](cor-typeid-structure.md), que actúa como un identificador opaco que identifica un tipo cargado en el tiempo de ejecución.  
  
 Cuando el tipo que representa la ICorDebugType no se ha cargado todavía, este método devuelve `CORDBG_E_CLASS_NOT_LOADED`.  Si no se admite el tipo, devuelve `CORDBG_E_UNSUPPORTED`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugType2 (interfaz)](icordebugtype2-interface.md)
