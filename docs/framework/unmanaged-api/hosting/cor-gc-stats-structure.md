---
title: COR_GC_STATS (Estructura)
ms.date: 03/30/2017
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
ms.openlocfilehash: 2ab0c38645a8e5fbd9e71b3c1787e88bfe2c0604
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176531"
---
# <a name="cor_gc_stats-structure"></a>COR_GC_STATS (Estructura)
Proporciona estadísticas sobre el mecanismo de recolección de elementos no utilizados de Common Language Runtime (CLR).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`Flags`|Indica qué valores de campo se deben calcular y devolver.|  
|`ExplicitGCCount`|Indica el número de recolecciones de elementos no utilizados forzadas por solicitud externa.|  
|`GenCollectionsTaken`|Indica el número de recolecciones de elementos no utilizados realizadas para cada generación.|  
|`CommittedKBytes`|El número total de kilobytes confirmados en todos los montones.|  
|`ReservedKBytes`|El número total de kilobytes reservados en todos los montones.|  
|`Gen0HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación cero.|  
|`Gen1HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación uno.|  
|`Gen2HeapSizeKBytes`|El tamaño, en kilobytes, del montón de generación dos.|  
|`LargeObjectHeapSizeKBytes`|El tamaño, en kilobytes, del montón de objetos grandes.|  
|`KBytesPromotedFromGen0`|El tamaño, en kilobytes, de los objetos promovidos de generación cero a generación uno.|  
|`KBytesPromotedFromGen1`|El tamaño, en kilobytes, de los objetos promovidos de generación uno a generación dos.|  
  
## <a name="remarks"></a>Observaciones  
 El método [ICLRGCManager::GetStats](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-getstats-method.md) `Flags` requiere que `COR_GC_STATS` el campo de la estructura se establezca en uno o varios valores de la [enumeración COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) para especificar qué estadísticas se deben establecer.  
  
 En la tabla siguiente se asignan las estadísticas proporcionadas `COR_GC_MEMORYUSAGE`por esta estructura a los dos [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) valores de enumeración `COR_GC_COUNTS` y .  
  
|Especificado por COR_GC_COUNTS|Especificado por COR_GC_MEMORYUSAGE|  
|----------------------------------|---------------------------------------|  
|`ExplicitGCCount`<br /><br /> `GenCollectionsTaken`|`CommittedKBytes`<br /><br /> `ReservedKBytes`<br /><br /> `Gen0HeapSizeKBytes`<br /><br /> `Gen1HeapSizeKBytes`<br /><br /> `Gen2HeapSizeKBytes`<br /><br /> `LargeObjectHeapSizeKBytes`<br /><br /> `KBytesPromotedFromGen0`<br /><br /> `KBytesPromotedFromGen1`|  
  
 Un ejemplo del uso es el siguiente:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** GCHost.idl  
  
 **Biblioteca:** Incluido como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Estructuras de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-structures.md)
- [Gestión automática de la memoria](../../../standard/automatic-memory-management.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
