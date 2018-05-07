---
title: COR_SEGMENT (Estructura)
ms.date: 03/30/2017
api_name:
- COR_SEGMENT
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- COR_SEGMENT
helpviewer_keywords:
- COR_SEGMENT structure [.NET Framework debugging]
ms.assetid: 93aeecb9-7fef-4545-8daf-f566dfc47084
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b816087f54e652f07dc791b7d66eb1af8f52f55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corsegment-structure"></a>COR_SEGMENT (Estructura)
Contiene información sobre una región de memoria en el montón administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_SEGMENT {  
    CORDB_ADDRESS start;            
    CORDB_ADDRESS end;              
    CorDebugGenerationTypes gen;    
    ULONG heap;                     
} COR_SEGMENT;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`start`|La dirección inicial de la región de memoria.|  
|`end`|La dirección final de la región de memoria.|  
|`gen`|A [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) miembro de enumeración que indica la generación de la región de memoria.|  
|`heap`|El número de montón en el que reside la región de memoria. Vea la sección Comentarios para obtener más información.|  
  
## <a name="remarks"></a>Comentarios  
 El `COR_SEGMENTS` estructura representa una región de memoria en el montón administrado.  `COR_SEGMENTS` los objetos son miembros de la [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de colección, que se rellena mediante una llamada a la[icordebugprocess5:: Enumerateheapregions](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) método.  
  
 El `heap` campo es el número de procesador, que se corresponde con el montón que se va a notificar. Para los recolectores de elementos no utilizados de estación de trabajo, su valor siempre es cero, porque las estaciones de trabajo tienen solo un montón de elementos no utilizados. Para recolectores de elementos no utilizados de servidor, su valor se corresponde con el procesador que está vinculado del montón. Tenga en cuenta que puede haber más o menos recolección montones de procesadores reales debido a los detalles de implementación del recolector de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
