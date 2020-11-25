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
ms.openlocfilehash: 12ce800cb83ef4f79710aa441b50be860526023c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728126"
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum (Interfaz)

Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (Método)](icordebuggcreferenceenum-next-method.md)|Obtiene el número especificado de instancias de [COR_GC_REFERENCE](cor-gc-reference-structure.md) que contienen información sobre los objetos que se van a recolectar como elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  

 La `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".  
  
 Una `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](cor-gc-reference-structure.md) instancias llamando al método [ICorDebugProcess5:: enumerategcreferences (](icordebugprocess5-enumerategcreferences-method.md) . [COR_GC_REFERENCE](cor-gc-reference-structure.md) objetos se pueden enumerar llamando al método [ICorDebugGCReference:: Next](icordebuggcreferenceenum-next-method.md) .  
  
 Los objetos [COR_GC_REFERENCE](cor-gc-reference-structure.md) de la colección rellenados por este método representan tres tipos de objetos:  
  
- Objetos de todas las pilas administradas. Esto incluye las referencias dinámicas en código administrado, así como los objetos creados por el Common Language Runtime.  
  
- Objetos de la tabla de identificadores. Esto incluye referencias seguras ( `HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT` ) y variables estáticas en un módulo.  
  
- Objetos de la cola del finalizador. Los objetos raíces de la cola del finalizador hasta que se haya ejecutado el finalizador.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
