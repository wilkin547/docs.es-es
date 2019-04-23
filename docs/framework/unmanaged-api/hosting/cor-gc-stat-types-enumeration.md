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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9e228cfbdade420c4d5248ffd417c6131083ee74
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59110422"
---
# <a name="corgcstattypes-enumeration"></a>COR_GC_STAT_TYPES (enumeración)
Especifica las estadísticas que se registren para la recolección.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    COR_GC_COUNTS                 = 0x00000001  
    COR_GC_MEMORYUSAGE            = 0x00000002  
} COR_GC_STAT_TYPES;  
```  
  
## <a name="remarks"></a>Comentarios  
 Esta enumeración especifica las estadísticas que en el [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) estructura que se va a establecer [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método.  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_GC_COUNTS`|Registra el número de recolecciones de elementos no utilizados realizadas para cada generación.|  
|`COR_GC_MEMORYUSAGE`|Registros memoria elementos no utilizados y el uso de las estadísticas de tamaño.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: GCHost.idl, GCHost.h  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [COR_GC_STATS (estructura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [Enumeraciones para hosts](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
