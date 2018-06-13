---
title: IHostTask::Join (Método)
ms.date: 03/30/2017
api_name:
- IHostTask.Join
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask::Join
helpviewer_keywords:
- IHostTask::Join method [.NET Framework hosting]
- Join method, IHostTask interface [.NET Framework hosting]
ms.assetid: 2cffcc52-19e0-4ced-a440-fc7375078ac9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0320e365daf03703a46eb48aac74e301d47520ed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442288"
---
# <a name="ihosttaskjoin-method"></a>IHostTask::Join (Método)
La tarea que realiza la llamada se bloquea hasta que finaliza la tarea representada por el actual [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) completa de la instancia, se agota el tiempo especificado, o [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Join (  
    [in] DWORD milliseconds,  
    [in] DWORD option  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `milliseconds`  
 [in] El intervalo de tiempo, en milisegundos, para esperar a que finalice la tarea. Si este intervalo transcurre antes de que finalice la tarea, se desbloquea la tarea que realiza la llamada.  
  
 `option`  
 [in] Uno de los [WAIT_OPTION](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md) valores. Un valor de WAIT_ALERTABLE indica al host que reactivar la tarea si `Alert` se llama antes de `milliseconds` transcurre.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Join` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada agotó el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estuvo esperando en la base de datos o actual `IHostTask` instancia no está asociada a una tarea.|  
|E_FAIL|Se ha producido un error catastrófico desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [WAIT_OPTION (enumeración)](../../../../docs/framework/unmanaged-api/hosting/wait-option-enumeration.md)
