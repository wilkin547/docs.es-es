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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa8c3160dc779b2475dec63be896af5283cf5346
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebuggcreferenceenum-interface"></a>ICorDebugGCReferenceEnum (Interfaz)
Proporciona un enumerador para los objetos que se recolectarán como elementos no utilizados.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Next (método)](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md)|Obtiene el número especificado de [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias que contienen información acerca de los objetos que se recolectarán como elementos no utilizados.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICorDebugGCReferenceEnum` interfaz implementa la interfaz "ICorDebugEnum".  
  
 Un `ICorDebugGCReferenceEnum` instancia se rellena con [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) instancias mediante una llamada a la [icordebugprocess5:: Enumerategcreferences](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerategcreferences-method.md) método. [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) pueden enumerar objetos mediante una llamada a la [ICorDebugGCReference::Next](../../../../docs/framework/unmanaged-api/debugging/icordebuggcreferenceenum-next-method.md) método.  
  
 El [COR_GC_REFERENCE](../../../../docs/framework/unmanaged-api/debugging/cor-gc-reference-structure.md) objetos de la colección que se rellena con este método representan tres tipos de objetos:  
  
-   Objetos de todas las pilas administradas. Esto incluye referencias directas en código administrado, así como los objetos creados por common language runtime.  
  
-   Objetos de la tabla de identificadores. Esto incluye las referencias fuertes (`HNDTYPE_STRONG` y `HNDTYPE_REFCOUNT`) y las variables estáticas en un módulo.  
  
-   Objetos de la cola del finalizador. La cola del finalizador raíces de objetos hasta que ha ejecutado el finalizador.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
