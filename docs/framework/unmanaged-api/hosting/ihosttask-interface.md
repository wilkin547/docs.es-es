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
ms.openlocfilehash: df1fb24c4003f77523ef01a4029fd19cc55a3fef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33442226"
---
# <a name="ihosttask-interface"></a>IHostTask (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para comunicarse con el host para administrar las tareas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Alert (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md)|Las solicitudes que el host reactive la tarea representada por el actual `IHostTask` instancia, por lo que se puede anular la tarea.|  
|[GetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-getpriority-method.md)|Obtiene el nivel de prioridad de subproceso de la tarea representada por el actual `IHostTask` instancia.|  
|[Join (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-join-method.md)|La tarea que realiza la llamada se bloquea hasta que finaliza la tarea representada por el actual `IHostTask` completa de la instancia, se agota el tiempo especificado, o [IHostTask:: Alert](../../../../docs/framework/unmanaged-api/hosting/ihosttask-alert-method.md) se llama.|  
|[SetCLRTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md)|Asocia un [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia con el actual `IHostTask` instancia.|  
|[SetPriority (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setpriority-method.md)|Solicita que el host ajuste la prioridad del subproceso de nivel para la tarea representada por el actual `IHostTask` instancia.|  
|[Start (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md)|Solicita que el host mueva la tarea representada por el actual `IHostTask` instancia desde un estado suspendido al estado activo, en el que se puede ejecutar código.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a métodos definidos por `IHostTask` para iniciar una tarea, establece su prioridad de subproceso nivel, y así sucesivamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
