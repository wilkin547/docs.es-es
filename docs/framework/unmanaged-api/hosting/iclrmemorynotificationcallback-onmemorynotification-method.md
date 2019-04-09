---
title: ICLRMemoryNotificationCallback::OnMemoryNotification (Método)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback.OnMemoryNotification
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification
helpviewer_keywords:
- ICLRMemoryNotificationCallback::OnMemoryNotification method [.NET Framework hosting]
- OnMemoryNotification method [.NET Framework hosting]
ms.assetid: 5612a44d-56cc-4f34-af31-8c9809ba9431
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c7866e0ecc62f037284a5329cb5785be90088f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115848"
---
# <a name="iclrmemorynotificationcallbackonmemorynotification-method"></a>ICLRMemoryNotificationCallback::OnMemoryNotification (Método)
Notifica a common language runtime (CLR) de la carga de memoria en el equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT OnMemoryNotification (  
    [in] EMemoryAvailable eMemoryAvailable  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `eMemoryAvailable`  
 [in] Uno de los [EMemoryAvailable](../../../../docs/framework/unmanaged-api/hosting/ememoryavailable-enumeration.md) valores, que indica la presión de memoria del equipo está experimentando.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`OnMemoryNotification` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR registra una devolución de llamada `OnMemoryNotification` mediante una llamada a la [IHostMemoryManager:: RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md) método. El runtime usa la información devuelta en la devolución de llamada para liberar memoria adicional cuando el host informa de que los recursos se ejecutan bajo la memoria.  
  
> [!NOTE]
>  Las llamadas a `OnMemoryNotification` nunca se bloqueará. Siempre devuelven inmediatamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Método RegisterMemoryNotificationCallback](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-registermemorynotificationcallback-method.md)
- [ICLRMemoryNotificationCallback (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-interface.md)
