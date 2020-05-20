---
title: COR_GC_STAT_TYPES (enumeración)
ms.date: 03/30/2017
api_name:
- COR_GC_STAT_TYPES
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STAT_TYPES
helpviewer_keywords:
- COR_GC_STAT_TYPES enumeration [.NET Framework hosting]
ms.assetid: fc51d6db-f7f8-408b-b93d-c166fc712c99
topic_type:
- apiref
ms.openlocfilehash: cca393ae34144787ab7800baec7c58209394f30e
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616723"
---
# <a name="cor_gc_stat_types-enumeration"></a>COR_GC_STAT_TYPES (enumeración)
Especifica las estadísticas que se van a registrar para una recolección de elementos no utilizados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Observaciones  
 Esta enumeración especifica qué estadísticas de la estructura de [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](iclrgcmanager-getstats-method.md) .  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.|  
|`COR_GC_MEMORYUSAGE`|Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [COR_GC_STATS (Estructura)](cor-gc-stats-structure.md)
- [Enumeraciones para hosts](hosting-enumerations.md)
