---
title: IHostMemoryManager::RegisterMemoryNotificationCallback (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 87dfbe85d279aa191253857887c1d9b5b5f8c7cc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59088527"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>IHostMemoryManager::RegisterMemoryNotificationCallback (Método)
Registra un puntero a una función de devolución de llamada que el host invoca para notificar a common language runtime (CLR) de la carga de memoria actual en el equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pCallback`  
 [in] Un puntero de interfaz a un [ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md) instancia que está implementado por CLR.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Dado que el `ICLRMemoryNotificationCallback` interfaz define solo un método ([ICLRMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)) y porque `pCallback` es un puntero a un `ICLRMemoryNotificationCallback` instancia proporcionada por CLR, el registro de forma eficaz es para la propia función de devolución de llamada. El host invoca `OnMemoryNotification` a comunicar condiciones de presión de memoria, en lugar de utilizar Win32 estándar `CreateMemoryResourceNotification` función. Para obtener más información, consulte la documentación de la plataforma de Windows.  
  
> [!NOTE]
>  Las llamadas a `OnMemoryNotification` nunca se bloqueará. Siempre devuelven inmediatamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMemoryNotificationCallback (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
- [IHostMemoryManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
