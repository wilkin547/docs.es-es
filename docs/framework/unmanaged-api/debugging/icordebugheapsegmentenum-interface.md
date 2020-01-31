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
ms.openlocfilehash: 98e3351c9c86961d11b0985117259d0ff3b609ae
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76794420"
---
# <a name="icordebugheapsegmentenum-interface"></a>ICorDebugHeapSegmentEnum (Interfaz)
Proporciona un enumerador para las regiones de memoria del montón administrado. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](icordebugheapsegmentenum-next-method.md)|Obtiene el número especificado de instancias de [COR_HEAPOBJECT](cor-heapobject-structure.md) que contienen información sobre las regiones del montón administrado.|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorDebugHeapSegmentEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugHeapSegmentEnum` se rellena con [COR_HEAPOBJECT](cor-heapobject-structure.md) instancias mediante una llamada al método [ICorDebugProcess5:: enumerateheapregions (](icordebugprocess5-enumerateheapregions-method.md) . Los objetos [COR_HEAPOBJECT](cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapsegmentenum (:: Next](icordebugheapsegmentenum-next-method.md) .  
  
 Un objeto de colección `ICorDebugHeapSegmentEnum` enumera todas las regiones de memoria que pueden contener objetos administrados, pero no garantiza que los objetos administrados residan realmente en esas regiones. Puede incluir información sobre las regiones de memoria vacía o reservada.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](debugging-interfaces.md)
