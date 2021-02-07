---
description: 'Más información sobre: ICorDebugProcess5:: Gettypelayout ((método)'
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
ms.openlocfilehash: d4496fa832b048dfc0bbe792aeb8fdcd460f5158
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746287"
---
# <a name="icordebugprocess5gettypelayout-method"></a>ICorDebugProcess5::GetTypeLayout (Método)

Obtiene información sobre el diseño de un objeto en memoria basándose en su identificador de tipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetTypeLayout(    [in] COR_TYPEID id,     [out] COR_TYPE_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a>Parámetros  

 `id`  
 de [COR_TYPEID](cor-typeid-structure.md) token que especifica el tipo cuyo diseño se desea.  
  
 `pLayout`  
 enuncia Puntero a una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) que contiene información sobre el diseño del objeto en memoria.  
  
## <a name="remarks"></a>Observaciones  

 El `ICorDebugProcess5::GetTypeLayout` método proporciona información sobre un objeto basándose en su [COR_TYPEID](cor-typeid-structure.md), que es devuelto por una serie de otros métodos [ICorDebugProcess5](icordebugprocess5-interface.md) . La información se proporciona mediante una estructura de [COR_TYPE_LAYOUT](cor-type-layout-structure.md) rellenada por el método.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [COR_TYPE_LAYOUT (Estructura)](cor-type-layout-structure.md)
- [ICorDebugProcess5 (Interfaz)](icordebugprocess5-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
