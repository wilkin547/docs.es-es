---
title: ICLRTaskManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager
helpviewer_keywords:
- ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: 2bd55e0c-001b-41fd-b29d-f01670fe8216
topic_type:
- apiref
ms.openlocfilehash: e25a6a03a836b8b4964b8260c974c8e8d8d9998d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73092184"
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager (Interfaz)
Proporciona métodos que permiten al host solicitar explícitamente que el Common Language Runtime (CLR) cree una nueva tarea, obtenga la tarea que se está ejecutando actualmente y establezca el idioma geográfico y la referencia cultural de la tarea.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-createtask-method.md)|Solicita explícitamente que CLR cree una nueva instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .|  
|[GetCurrentTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttask-method.md)|Obtiene la instancia de `ICLRTask` que representa la tarea que se está ejecutando actualmente.|  
|[GetCurrentTaskType (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-getcurrenttasktype-method.md)|Obtiene el tipo de la tarea que se está ejecutando actualmente.|  
|[SetLocale (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setlocale-method.md)|Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se está ejecutando actualmente.|  
|[SetUILocale (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-setuilocale-method.md)|Notifica a la Common Language Runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se está ejecutando actualmente.|  
  
## <a name="remarks"></a>Comentarios  
 Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado host (una instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)) como en el lado de CLR (una instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)). Tanto el host como el CLR pueden iniciar la creación de una tarea, pero la representación en el host debe estar asociada a una representación del lado del CLR correspondiente para garantizar una comunicación correcta entre el host y el CLR con respecto a la tarea. Los dos objetos deben crearse y crearse instancias antes de que el código administrado pueda ejecutarse en un subproceso del sistema operativo.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
