---
title: ICorDebugGCReferenceEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugGCReferenceEnum
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGCReferenceEnum
helpviewer_keywords:
- ICorDebugGCReferenceEnum interface [.NET Framework debugging]
ms.assetid: 5f3c91c9-c035-454f-96cc-011cab1ea06b
topic_type:
- apiref
ms.openlocfilehash: 49f89f7d36e74b1fa5921230d7dc6d271d4c0883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134630"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum (Interfaz)
Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Obtiene el número especificado de instancias de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elemento no utilizado.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugGCReferenceEnum` implementa la interfaz "ICorDebugEnum".  
  
 Una instancia de `ICorDebugGCReferenceEnum` se rellena con instancias de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) llamando al método [ICorDebugProcess5:: enumerategcreferences (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) . Los objetos [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) se pueden enumerar llamando al método [ICorDebugGCReference:: Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) .  
  
 Los objetos [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) de la colección rellenados por este método representan tres tipos de objetos:  
  
- Objetos de todas las pilas administradas. Esto incluye las referencias dinámicas en código administrado, así como los objetos creados por el Common Language Runtime.  
  
- Objetos de la tabla de identificadores. Esto incluye referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y variables estáticas en un módulo.  
  
- Objetos de la cola del finalizador. Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
