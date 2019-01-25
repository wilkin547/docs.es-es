---
title: IHostTaskManager::SetUILocale (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.SetUILocale
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::SetUILocale
helpviewer_keywords:
- SetUILocale method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::SetUILocale method [.NET Framework hosting]
ms.assetid: d0c87a9c-ea81-4237-a16b-c22b36ec9dc8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7a263410e898ee5805ce2a3dc9d534c25f6b9106
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54496158"
---
# <a name="ihosttaskmanagersetuilocale-method"></a>IHostTaskManager::SetUILocale (Método)
Notifica al host que common language runtime (CLR) ha cambiado la configuración regional del usuario (UI) de la interfaz, o la referencia cultural en la tarea está ejecuta actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetUILocale (  
    [in] LCID lcid  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `lcid`  
 [in] El valor de identificador de configuración regional que se asigna a la cultura geográfica recién asignado y el idioma.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetUILocale` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_NOTIMPL|El host no admite el código de usuario administrado para cambiar la referencia cultural de interfaz de usuario.|  
  
## <a name="remarks"></a>Comentarios  
 El runtime llama a `SetUILocale` cuando el valor de la <xref:System.Threading.Thread.CurrentUICulture%2A?displayProperty=nameWithType> propiedad se modifica mediante código administrado. Este método proporciona una oportunidad para que el host ejecutar los mecanismos que sean necesarios para la sincronización de configuraciones regionales. Si un host no admite la configuración regional de interfaz de usuario se puede cambiar desde el código administrado o no implementa un mecanismo para sincronizar las configuraciones regionales, debe devolver E_NOTIMPL desde este método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [SetLocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)
