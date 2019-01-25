---
title: IHostTask (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTask
helpviewer_keywords:
- IHostTask interface [.NET Framework hosting]
ms.assetid: a71dbbd5-64b8-47eb-9f03-8e8c85fbe2bc
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d862c02e96487049fb88f80665d32caf6939ed1e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54555951"
---
# <a name="ihosttask-interface"></a>IHostTask (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para comunicarse con el host para administrar las tareas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alert (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Las solicitudes que el host reactive la tarea representada por el actual `IHostTask` de instancia, por lo que se puede anular la tarea.|  
|[GetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.|  
|[Join (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Bloquea la tarea que realiza la llamada hasta que la tarea representada por el actual `IHostTask` instancia se haya completado, transcurre el intervalo de tiempo especificado, o [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.|  
|[SetCLRTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Asocia un [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia con el actual `IHostTask` instancia.|  
|[SetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Solicita que el host ajuste la prioridad del subproceso de nivel de la tarea representada por el actual `IHostTask` instancia.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Solicita que el host mueva la tarea representada por el actual `IHostTask` instancia desde un estado suspendido al estado activo, en el que se puede ejecutar el código.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establezca la prioridad de subproceso nivel, y así sucesivamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
