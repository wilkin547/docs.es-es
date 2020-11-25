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
ms.openlocfilehash: 1170b29c01275b108a6ccdf6e324c96d97c10c82
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732455"
---
# <a name="iclrtaskmanager-interface"></a>ICLRTaskManager (Interfaz)

Proporciona métodos que permiten al host solicitar explícitamente que el Common Language Runtime (CLR) cree una nueva tarea, obtenga la tarea que se está ejecutando actualmente y establezca el idioma geográfico y la referencia cultural de la tarea.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateTask (Método)](iclrtaskmanager-createtask-method.md)|Solicita explícitamente que CLR cree una nueva instancia de [ICLRTask](iclrtask-interface.md) .|  
|[Método GetCurrentTask](iclrtaskmanager-getcurrenttask-method.md)|Obtiene la `ICLRTask` instancia de que representa la tarea que se está ejecutando actualmente.|  
|[Método GetCurrentTaskType](iclrtaskmanager-getcurrenttasktype-method.md)|Obtiene el tipo de la tarea que se está ejecutando actualmente.|  
|[Método SetLocale](iclrtaskmanager-setlocale-method.md)|Notifica a CLR que el host ha modificado el identificador de configuración regional en la tarea que se está ejecutando actualmente.|  
|[Método SetUILocale](iclrtaskmanager-setuilocale-method.md)|Notifica a la Common Language Runtime que el host ha modificado el identificador de configuración regional de la interfaz de usuario en la tarea que se está ejecutando actualmente.|  
  
## <a name="remarks"></a>Comentarios  

 Cada tarea que se ejecuta en un entorno hospedado tiene representaciones tanto en el lado host (una instancia de [IHostTask](ihosttask-interface.md)) como en el lado de CLR (una instancia de [ICLRTask](iclrtask-interface.md)). Tanto el host como el CLR pueden iniciar la creación de una tarea, pero la representación en el host debe estar asociada a una representación del lado del CLR correspondiente para garantizar una comunicación correcta entre el host y el CLR con respecto a la tarea. Los dos objetos deben crearse y crearse instancias antes de que el código administrado pueda ejecutarse en un subproceso del sistema operativo.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
