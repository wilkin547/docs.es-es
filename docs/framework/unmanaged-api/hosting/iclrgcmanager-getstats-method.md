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
ms.openlocfilehash: 9e8b65c735028029f4fb44c2640df74ef171d9de
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141144"
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
 [in, out] Instancia de [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) que contiene las estadísticas solicitadas.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetStats` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 CLR calcula y devuelve solo las estadísticas especificadas por el campo `Flags` de `pStats`.  
  
 Establezca el campo `Flags` en uno o varios valores de la enumeración [COR_GC_STAT_TYPES](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md) para especificar qué estadísticas de la estructura [COR_GC_STATS](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md) se van a establecer.  
  
 A continuación se muestra un ejemplo de uso:  
  
```cpp  
COR_GC_STATS GCStats;  
GCStats.Flags = COR_GC_COUNTS | COR_GC_MEMORYUSAGE;  
pCLRGCManager->GetStats(&GCStats);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Administración automática de la memoria](../../../standard/automatic-memory-management.md)
- [COR_GC_STATS (estructura)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stats-structure.md)
- [COR_GC_STAT_TYPES (enumeración)](../../../../docs/framework/unmanaged-api/hosting/cor-gc-stat-types-enumeration.md)
- [Recolección de elementos no utilizados](../../../standard/garbage-collection/index.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRGCManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md)
- [Interfaces de hospedaje de CLR](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
