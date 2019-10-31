---
title: ICorDebugHeapSegmentEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHealRegionEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapSegmentEnum
helpviewer_keywords:
- ICorDebugHeapSegmentEnum interface [.NET Framework debugging]
ms.assetid: 20fc1b9d-e228-4107-bd76-53934c1724b9
topic_type:
- apiref
ms.openlocfilehash: e9679029cd54ac44832add9bc4f47f8c8e9a26a2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138449"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum (Interfaz)
Proporciona un enumerador para las regiones de memoria del montón administrado. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md)|Obtiene el número especificado de instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que contienen información sobre las regiones del montón administrado.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugHeapSegmentEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugHeapSegmentEnum` se rellena con instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) llamando al método [ICorDebugProcess5:: enumerateheapregions (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) . Los objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapsegmentenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-next-method.md) .  
  
 Un objeto de colección `ICorDebugHeapSegmentEnum` enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residan realmente en esas regiones. Puede incluir información sobre las regiones de memoria vacía o reservada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
