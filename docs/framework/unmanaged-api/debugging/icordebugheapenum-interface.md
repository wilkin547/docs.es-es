---
title: ICorDebugHeapEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugHeapEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugHeapEnum
helpviewer_keywords:
- ICorDebugHeapEnum interface [.NET Framework debugging]
ms.assetid: 99cbc1eb-d539-4f76-a0d8-b93348112f14
topic_type:
- apiref
ms.openlocfilehash: e8d1948a7d0ff23410ba8670628424a4067fb47d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138486"
---
# <a name="icordebugheapenum-interface"></a>ICorDebugHeapEnum (Interfaz)
Proporciona un enumerador para los objetos del montón administrado. Esta interfaz es una subclase de la interfaz ICorDebugEnum.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md)|Obtiene el número especificado de instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) que contienen información sobre los objetos del montón administrado.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugHeapEnum` implementa la interfaz ICorDebugEnum.  
  
 Una instancia de `ICorDebugHeapEnum` se rellena con instancias de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) llamando al método [ICorDebugProcess5:: enumerateheap (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheap-method.md) . Cada instancia de [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) de la colección representa un objeto activo en el montón o un objeto que no está raíz de ningún objeto y que el recolector de elementos no utilizados aún no ha recopilado. Los objetos [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) de la colección se pueden enumerar llamando al método [Icordebugheapenum (:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-next-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
