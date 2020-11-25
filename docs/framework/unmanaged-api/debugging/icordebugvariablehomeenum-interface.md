---
title: Interfaz ICorDebugVariableHomeEnum
ms.date: 03/30/2017
api_name:
- ICorDebugVariableHomeEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugVariableHomeEnum
helpviewer_keywords:
- ICorDebugVariableHomeEnum interface [.NET Framework debugging]
ms.assetid: c312ae6d-c8dc-48d6-9f1e-ead515c88fdf
topic_type:
- apiref
ms.openlocfilehash: 8e8caad9f0fc60121dbd1c738a6024da3e4d02f6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95726007"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaz ICorDebugVariableHomeEnum

Proporciona un enumerador para las variables locales y los argumentos de una función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (Método)](icordebugvariablehomeenum-next-method.md)|Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.|  
  
## <a name="remarks"></a>Comentarios  

 La `ICorDebugVariableHomeEnum` interfaz implementa la interfaz ICorDebugEnum.  
  
 Una `ICorDebugVariableHomeEnum` instancia se rellena con instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) . Cada instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función. Los objetos  [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugVariableHome](icordebugvariablehome-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
