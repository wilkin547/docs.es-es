---
title: ICLRTaskManager::GetCurrentTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.GetCurrentTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::GetCurrentTask
helpviewer_keywords:
- GetCurrentTask method, ICLRTaskManager interface [.NET Framework hosting]
- ICLRTaskManager::GetCurrentTask method [.NET Framework hosting]
ms.assetid: c0b82a9f-edc6-4878-9c81-48de53c02142
topic_type:
- apiref
ms.openlocfilehash: a57610d1b41d80d54a245b9744aafd78a1e88177
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195906"
---
# <a name="iclrtaskmanagergetcurrenttask-method"></a>ICLRTaskManager::GetCurrentTask (Método)
Obtiene la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada al método.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCurrentTask (  
    [out] ICLRTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ppTask`  
 enuncia Puntero a la dirección de una instancia de `ICLRTask` que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se originó la llamada, o null si no hay ninguna tarea que se esté ejecutando actualmente en este subproceso.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 La instancia de `ICLRTask` a la que apunta el parámetro `ppTask` representa la tarea que se está ejecutando actualmente para CLR. La instancia de `ICLRTask` está asociada a una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) correspondiente que representa la tarea para el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
