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
ms.openlocfilehash: faf1be65d308b223490f3ae67eed3d8a2b1688b9
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59223074"
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
|`start`|La dirección de inicio de la región de memoria.|  
|`end`|La dirección final de la región de memoria.|  
|`gen`|Un miembro de la enumeración [CorDebugGenerationTypes](../../../../docs/framework/unmanaged-api/debugging/cordebuggenerationtypes-enumeration.md) que indica la generación de la región de memoria.|  
|`heap`|El número de montón en el que reside la región de memoria. Vea la sección Comentarios para obtener más información.|  
  
## <a name="remarks"></a>Comentarios  
 La estructura `COR_SEGMENTS` representa una región de memoria en el montón administrado.  `COR_SEGMENTS` los objetos son miembros de la [ICorDebugHeapRegionEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapsegmentenum-interface.md) objeto de colección, que se rellena mediante una llamada a la [Icordebugprocess5](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-enumerateheapregions-method.md) método.  
  
 El campo `heap` es el número de procesador, que se corresponde con el montón que se va a notificar. Para los recolectores de elementos no utilizados de la estación de trabajo, su valor siempre es cero, porque las estaciones de trabajo tienen solo un montón de recolección de elementos no utilizados. Para los recolectores de elementos no utilizados de servidor, su valor se corresponde con el procesador al que está vinculado el montón. Tenga en cuenta que podría haber más o menos montones de recolección de elementos no utilizados que procesadores reales debido a los detalles de implementación del recolector de elementos no utilizados.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Estructuras de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
