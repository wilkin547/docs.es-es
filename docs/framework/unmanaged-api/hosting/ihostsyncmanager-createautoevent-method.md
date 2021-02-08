---
description: 'Más información acerca de: IHostSyncManager:: CreateAutoEvent ((método)'
title: IHostSyncManager::CreateAutoEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateAutoEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateAutoEvent
helpviewer_keywords:
- IHostSyncManager::CreateAutoEvent method [.NET Framework hosting]
- CreateAutoEvent method [.NET Framework hosting]
ms.assetid: 3153643e-cf5c-4b44-8e0e-c2b22cb08208
topic_type:
- apiref
ms.openlocfilehash: 69767f1e01ead93c874eecf01c3167a5dc0e4b82
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784852"
---
# <a name="ihostsyncmanagercreateautoevent-method"></a>IHostSyncManager::CreateAutoEvent (Método)

Crea un objeto de evento de restablecimiento automático.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateAutoEvent (  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `ppEvent`  
 enuncia Un puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) implementada por el host, o null si no se pudo crear el objeto de evento.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateAutoEvent` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear el objeto de evento solicitado.|  
  
## <a name="remarks"></a>Observaciones  

 `CreateAutoEvent` crea un objeto de evento automático cuyo estado se cambia automáticamente a no señalizado después de que se haya liberado el subproceso en espera. Este método refleja la `CreateEvent` función de Win32 con el valor `false` especificado para el `bManualReset` parámetro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
