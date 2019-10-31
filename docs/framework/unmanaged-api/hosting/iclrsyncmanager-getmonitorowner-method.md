---
title: ICLRSyncManager::GetMonitorOwner (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetMonitorOwner
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetMonitorOwner
helpviewer_keywords:
- ICLRSyncManager::GetMonitorOwner method [.NET Framework hosting]
- GetMonitorOwner method [.NET Framework hosting]
ms.assetid: 840983a4-396d-47b4-86a0-d35f9b437cdb
topic_type:
- apiref
ms.openlocfilehash: 3aec11674275769bb5c4b68521a40a72a1d68a22
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124678"
---
# <a name="iclrsyncmanagergetmonitorowner-method"></a>ICLRSyncManager::GetMonitorOwner (Método)
Obtiene la instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) que posee el monitor identificado por la cookie especificada.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMonitorOwner (  
    [in]  SIZE_T     cookie,  
    [out] IHostTask *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `cookie`  
 de Cookie asociada al monitor.  
  
 `ppOwnerHostTask`  
 enuncia Puntero al `IHostTask` que posee actualmente el monitor, o null si ninguna tarea tiene propiedad.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetMonitorOwner` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Normalmente, el host llama a `GetMonitorOwner` como parte de un mecanismo de detección de interbloqueos. La cookie está asociada a un monitor cuando se crea mediante una llamada a [IHostSyncManager:: CreateMonitorEvent (](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md).  
  
> [!NOTE]
> Una llamada para liberar el evento subyacente al monitor podría bloquearse, pero no interbloqueará, si una llamada a este método está actualmente en vigor en la cookie asociada a ese monitor. Otras tareas también podrían bloquearse si intentan adquirir este monitor.  
  
 `GetMonitorOwner` devuelve siempre inmediatamente y se le puede llamar en cualquier momento después de una llamada a `CreateMonitorEvent`. No es necesario que el host espere hasta que una tarea esté esperando en el evento.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
