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
ms.openlocfilehash: a9b65449747fde42f9cd770e33741ef34d33fbb8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121031"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaz ICorDebugVariableHomeEnum
Proporciona un enumerador para las variables locales y los argumentos de una función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md)|Obtiene el número especificado de instancias de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugVariableHomeEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugVariableHomeEnum` se rellena con instancias de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](../../../../docs/framework/unmanaged-api/debugging/icordebugcode4-enumeratevariablehomes-method.md) . Cada instancia de [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función. Los objetos [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableHome (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
