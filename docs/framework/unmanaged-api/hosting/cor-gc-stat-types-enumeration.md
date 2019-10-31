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
ms.openlocfilehash: b0fbc462283ef1577de8100e60fd09caa53db539
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131914"
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
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración especifica qué estadísticas de la estructura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) se van a establecer mediante el método [ICLRGCManager:: getstats (](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) .  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.|  
|`COR_GC_MEMORYUSAGE`|Registra las estadísticas de uso de memoria y de tamaño de recolección de elementos no utilizados.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost. idl, GCHost. h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [COR_GC_STATS (estructura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
