---
title: ICLRTask (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask
helpviewer_keywords:
- ICLRTask interface [.NET Framework hosting]
ms.assetid: b3a44df3-578a-4451-b55e-70c8e7695f5e
topic_type:
- apiref
ms.openlocfilehash: c4f27a73022b0495b2772c0485c14a1b007dc883
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132645"
---
# <a name="iclrtask-interface"></a>ICLRTask (Interfaz)
Proporciona métodos que permiten al host realizar solicitudes del Common Language Runtime (CLR) o proporcionar una notificación al CLR sobre la tarea asociada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Solicita que CLR anule la tarea que la instancia de `ICLRTask` actual representa.|  
|[ExitTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Notifica a CLR que la tarea asociada a la instancia de `ICLRTask` actual está finalizando e intenta cerrar la tarea correctamente.|  
|[GetMemStats (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Obtiene información estadística sobre el uso de recursos de memoria por parte de la tarea representada por la instancia de `ICLRTask` actual.|  
|[LocksHeld (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Obtiene el número de bloqueos mantenidos actualmente en la tarea.|  
|[NeedsPriorityScheduling (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Obtiene un valor que indica si el host debe asignar una prioridad alta para volver a programar la tarea representada por la instancia de `ICLRTask` actual.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informa al CLR de que el host ha completado una tarea y permite al CLR volver a usar la instancia de `ICLRTask` actual para representar otra tarea.|  
|[RudeAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Hace que CLR anule inmediatamente la tarea representada por la instancia de `ICLRTask` actual, sin ninguna garantía de que se ejecuten los finalizadores.|  
|[SetTaskIdentifier (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Establece un identificador único para la tarea representada por la instancia de `ICLRTask` actual, para su uso en la depuración.|  
|[SwitchIn (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Notifica a CLR que la tarea representada por la instancia de `ICLRTask` actual está en un estado operativo.|  
|[SwitchOut (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Notifica a CLR que la tarea representada por la instancia de `ICLRTask` actual ya no se encuentra en un estado operativo.|  
|[YieldTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Solicita que el CLR haga que el tiempo de procesador esté disponible para otras tareas. CLR no ofrece ninguna garantía de que la tarea se ponga en un estado en el que pueda dar lugar a un tiempo de procesamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICLRTask` es la representación de una tarea para el CLR. En cualquier momento durante la ejecución del código, una tarea puede describirse como en ejecución o en espera para ejecutarse. El host llama al método `ICLRTask::SwitchIn` para notificar a CLR que la tarea que la instancia de `ICLRTask` actual representa ahora está en un estado operativo. Después de una llamada a `ICLRTask::SwitchIn`, el host puede programar la tarea en cualquier subproceso del sistema operativo, excepto en los casos en que el tiempo de ejecución requiere la afinidad de subprocesos, como se especifica en las llamadas a los métodos [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) y [IHostTaskManager:: Métodos EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) . En algún momento posterior, el sistema operativo podría decidir quitar la tarea del subproceso y colocarla en un estado de no ejecución. Por ejemplo, esto puede ocurrir cuando la tarea se bloquea en primitivas de sincronización o espera a que se completen las operaciones de e/s. El host llama a [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) para notificar a CLR que la tarea representada por la instancia de `ICLRTask` actual ya no se encuentra en un estado operativo.  
  
 Normalmente, una tarea finaliza al final de la ejecución del código. En ese momento, el host llama a `ICLRTask::ExitTask` para destruir el `ICLRTask`asociado. Sin embargo, las tareas también se pueden reciclar mediante una llamada a `ICLRTask::Reset`, lo que permite volver a usar la instancia de `ICLRTask`. Este enfoque evita la sobrecarga que supone la creación y destrucción repetidas de instancias.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
