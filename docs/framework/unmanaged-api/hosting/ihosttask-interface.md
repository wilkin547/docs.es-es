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
ms.openlocfilehash: 18dfee606f3d41229aa58a5b4bb9380b87c4efa5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73121396"
---
# <a name="ihosttask-interface"></a>IHostTask (Interfaz)
Proporciona métodos que permiten al Common Language Runtime (CLR) comunicarse con el host para administrar tareas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alert (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Solicita que el host reactive la tarea representada por la instancia de `IHostTask` actual, por lo que se puede anular la tarea.|  
|[GetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Obtiene el nivel de prioridad del subproceso de la tarea representada por la instancia de `IHostTask` actual.|  
|[Join (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la instancia de `IHostTask` actual, transcurre el intervalo de tiempo especificado o se llama a [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) .|  
|[SetCLRTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Asocia una instancia de la [interfaz ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) a la instancia de `IHostTask` actual.|  
|[SetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la instancia de `IHostTask` actual.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Solicita que el host mueva la tarea representada por la instancia de `IHostTask` actual de un estado suspendido a un estado activo, en el que se puede ejecutar el código.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establecer su nivel de prioridad de subprocesos, etc.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
