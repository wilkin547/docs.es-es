---
title: COR_GC_STATS (Estructura)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- COR_GC_STATS
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_GC_STATS
helpviewer_keywords:
- COR_GC_STATS structure [.NET Framework hosting]
ms.assetid: 8d4ff73e-739b-40f6-9349-359fbc99c2f9
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 02a775be4976760b354a492e7252a67ef04eace9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corgcstats-structure"></a>COR_GC_STATS (Estructura)
Proporciona estadísticas sobre el mecanismo de recopilación de elementos no utilizados de common language runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef struct _COR_GC_STATS {  
    ULONG   Flags;   
    SIZE_T  ExplicitGCCount;  
    SIZE_T  GenCollectionsTaken[3];  
    SIZE_T  CommittedKBytes;   
    SIZE_T  ReservedKBytes;  
    SIZE_T  Gen0HeapSizeKBytes;  
    SIZE_T  Gen1HeapSizeKBytes;  
    SIZE_T  Gen2HeapSizeKBytes;  
    SIZE_T  LargeObjectHeapSizeKBytes;  
    SIZE_T  KBytesPromotedFromGen0;  
    SIZE_T  KBytesPromotedFromGen1;  
} COR_GC_STATS;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`Flags`|Indica qué valores de campo deben ser calcula y devuelve.|  
|`ExplicitGCCount`|Indica el número de recolecciones de elementos no utilizados forzadas por solicitud externa.|  
|`GenCollectionsTaken`|Indica el número de recolecciones de elementos no utilizados lleva a cabo para cada generación.|  
|`CommittedKBytes`|El número total de kilobytes confirmados en todos los montones.|  
|`ReservedKBytes`|El número total de kilobytes reservados en todos los montones.|  
|`Gen0HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación de cero.|  
|`Gen1HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación 1.|  
|`Gen2HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación de dos.|  
|`LargeObjectHeapSizeKBytes`|El tamaño, en kilobytes, del montón de objetos grandes.|  
|`KBytesPromotedFromGen0`|El tamaño, en kilobytes, de los objetos que se promocionan de la generación 0 a la generación 1.|  
|`KBytesPromotedFromGen1`|El tamaño, en kilobytes, de los objetos que se promocionan de la generación 1 a generación 2.|  
  
## <a name="remarks"></a>Comentarios  
 El [ICLRGCManager:: GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) método requiere el `Flags` campo de la `COR_GC_STATS` estructura se establezca en uno o más valores de la [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) enumeración para especificar qué las estadísticas que se van a establecer.  
  
 La tabla siguiente asigna las estadísticas proporcionadas por esta estructura a los dos [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valores de enumeración, `COR_GC_COUNTS` y `COR_GC_MEMORYUSAGE`.  
  
|Especifica COR_GC_COUNTS|Especifica COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Un ejemplo del uso es como sigue:  
  
```  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)  
 [Administración automática de la memoria](../../../../docs/standard/automatic-memory-management.md)  
 [Recolección de elementos no utilizados](../../../../docs/standard/garbage-collection/index.md)
