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
ms.openlocfilehash: 74b3c7bed54f3735efbd5d2c56962d427518f71a
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790944"
---
# <a name="icordebugvariablehomeenum-interface"></a>Interfaz ICorDebugVariableHomeEnum
Proporciona un enumerador para las variables locales y los argumentos de una función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](icordebugvariablehomeenum-next-method.md)|Obtiene el número especificado de instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) que contienen información sobre las variables locales y los argumentos de una función.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorDebugVariableHomeEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugVariableHomeEnum` se rellena con instancias de [ICorDebugVariableHome](icordebugvariablehome-interface.md) llamando al método [interfaces icordebugcode4:: EnumerateVariableHomes](icordebugcode4-enumeratevariablehomes-method.md) . Cada instancia de [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección representa una variable local o un argumento de una función. Los objetos [ICorDebugVariableHome](icordebugvariablehome-interface.md) de la colección se pueden enumerar llamando al método [ICorDebugVariableHomeEnum:: Next](icordebugvariablehomeenum-next-method.md) .  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugVariableHome (interfaz)](icordebugvariablehome-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
