---
title: IHostTaskManager::BeginThreadAffinity (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.BeginThreadAffinity
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::BeginThreadAffinity
helpviewer_keywords:
- IHostTaskManager::BeginThreadAffinity method [.NET Framework hosting]
- BeginThreadAffinity method [.NET Framework hosting]
ms.assetid: fea3ab88-ce41-4c5a-847b-bb78cd748da6
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7eb5c7ec85c0adb301fb722155caaed3c14e0e19
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59137727"
---
# <a name="ihosttaskmanagerbeginthreadaffinity-method"></a>IHostTaskManager::BeginThreadAffinity (Método)
Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se mueve a otro subproceso del sistema operativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT BeginThreadAffinity ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`BeginThreadAffinity` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama normalmente `IHostTaskManager::BeginThreadAffinity` en el contexto de una llamada a <xref:System.Threading.Thread.BeginThreadAffinity%2A?displayProperty=nameWithType>. No se debe programar la tarea actual hasta que se realiza una llamada correspondiente a [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md). Pueden salir de las tareas, pero cuando se cambie iniciarla, deben asignarse al mismo subproceso del sistema operativo desde el que estaban. Anidar las llamadas a `BeginThreadAffinity` no tienen ningún efecto, porque la llamada hace referencia a la tarea actual.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
