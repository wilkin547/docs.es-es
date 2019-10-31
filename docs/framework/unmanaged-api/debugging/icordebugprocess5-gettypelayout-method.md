---
title: ICorDebugProcess5::GetTypeLayout (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetTypeLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetTypeLayout
helpviewer_keywords:
- ICorDebugProcess5::GetTypeLayout method [.NET Framework debugging]
- GetTypeLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: bd62f5d1-e874-41f1-81e5-a29a7572c15d
topic_type:
- apiref
ms.openlocfilehash: a348c3b2ad33a5d68b1bc46e9a284f2d2a9c7304
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121283"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout (Método)
Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parámetros  
 `id`  
 de Un token [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md) que especifica el tipo cuyo diseño se desea.  
  
 `pLayout`  
 enuncia Puntero a una estructura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) que contiene información sobre el diseño del objeto en memoria.  
  
## <a name="remarks"></a>Comentarios  
 El método `ICorDebugProcess5::GetTypeLayout` proporciona información sobre un objeto basado en su [COR_TYPEID](../../../../docs/framework/unmanaged-api/debugging/cor-typeid-structure.md), que es devuelto por una serie de otros métodos [ICorDebugProcess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md) . La información se proporciona mediante una estructura [COR_TYPE_LAYOUT](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md) que rellena el método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [COR_TYPE_LAYOUT (estructura)](../../../../docs/framework/unmanaged-api/debugging/cor-type-layout-structure.md)
- [ICorDebugProcess5 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
