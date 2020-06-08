---
title: ICLRGCManager::GetStats (Método)
ms.date: 03/30/2017
api_name:
- ICLRGCManager.GetStats
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRGCManager::GetStats
helpviewer_keywords:
- GetStats method, ICLRGCManager interface [.NET Framework hosting]
- ICLRGCManager::GetStats method [.NET Framework hosting]
ms.assetid: ce259d1d-cd81-4490-a7a1-0d0ea0804872
topic_type:
- apiref
ms.openlocfilehash: 8622920a81f4b469361ffa879f7a4eeda697cab9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504230"
---
# <a name="iclrgcmanagergetstats-method"></a>ICLRGCManager::GetStats (Método)
Obtiene un conjunto de estadísticas actuales sobre el sistema de recolección de elementos no utilizados del Common Language Runtime.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetStats (  
    [in, out] COR_GC_STATS *pStats  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pStats`  
 [in, out] [COR_GC_STATS](cor-gc-stats-structure.md) instancia de que contiene las estadísticas solicitadas.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetStats`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 CLR calcula y devuelve solo las estadísticas especificadas por el `Flags` campo de `pStats` .  
  
 Establezca el `Flags` campo en uno o varios valores de la enumeración [COR_GC_STAT_TYPES](cor-gc-stat-types-enumeration.md) para especificar qué estadísticas de la estructura de [COR_GC_STATS](cor-gc-stats-structure.md) se van a establecer.  
  
 A continuación se muestra un ejemplo de uso:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Administración de memoria automática](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS (Estructura)](cor-gc-stats-structure.md)
- [COR_GC_STAT_TYPES (enumeración)](cor-gc-stat-types-enumeration.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLRGCManager (Interfaz)](iclrgcmanager-interface.md)
- [Interfaces de hospedaje de CLR](clr-hosting-interfaces.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](index.md)
