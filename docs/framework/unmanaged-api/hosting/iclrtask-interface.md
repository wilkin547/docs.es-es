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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 94ba53e4af114773a347d15b7308dc4c3567154e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33435711"
---
# <a name="iclrtask-interface"></a>ICLRTask (Interfaz)
Proporciona métodos que permiten al host para realizar solicitudes de common language runtime (CLR), o para proporcionar una notificación a CLR de la tarea asociada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Solicita que CLR anule la tarea que actual `ICLRTask` instancia representa.|  
|[ExitTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Notifica a CLR que la tarea asociada a la actual `ICLRTask` instancia está finalizando e intenta cerrar la tarea correctamente.|  
|[GetMemStats (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Obtiene información estadística sobre el uso de recursos de memoria por la tarea representada por el actual `ICLRTask` instancia.|  
|[LocksHeld (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Obtiene el número de bloqueos mantenidos en la tarea.|  
|[NeedsPriorityScheduling (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Obtiene un valor que indica si el host debe asignar una prioridad alta para volver a programar la tarea representada por el actual `ICLRTask` instancia.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informa a CLR que el host ha finalizado una tarea y permite a CLR reutilizar actual `ICLRTask` instancia para representar otra tarea.|  
|[RudeAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Hace que el CLR debe anular la tarea representada por el actual `ICLRTask` instancia inmediatamente, sin ninguna garantía de que se ejecutarán los finalizadores.|  
|[SetTaskIdentifier (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Establece un identificador único para la tarea representada por el actual `ICLRTask` instancia, para su uso en la depuración.|  
|[SwitchIn (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Notifica a CLR que la tarea representa el actual `ICLRTask` instancia está en un estado operativo.|  
|[SwitchOut (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Notifica a CLR que la tarea representa el actual `ICLRTask` instancia ya no está en un estado operativo.|  
|[YieldTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Solicita el CLR ponga tiempo de procesador disponible para otras tareas. El CLR no ofrece ninguna garantía de que la tarea se colocará en un estado donde puede producir tiempo de procesamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICLRTask` es la representación de una tarea de CLR. En cualquier momento durante la ejecución de código, una tarea se puede describir como ejecutando o esperando para ejecutarse. El host llama el `ICLRTask::SwitchIn` método para informar a CLR que la tarea que actual `ICLRTask` instancia representa ahora está en un estado operativo. Después de llamar a `ICLRTask::SwitchIn`, el host puede programar la tarea en cualquier subproceso de sistema operativo, excepto en casos donde el tiempo de ejecución requiere la afinidad del subproceso, tal como se especifica mediante llamadas a la [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) y [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) métodos. Poco después, el sistema operativo podría decidir quitar la tarea del subproceso y lo coloca en un estado no están en ejecución. Por ejemplo, esto puede ocurrir cuando la tarea se bloquea en primitivas de sincronización o espera a que finalicen operaciones de E/S. El host llama [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) para notificar a CLR que la tarea representa el actual `ICLRTask` instancia ya no está en un estado operativo.  
  
 Normalmente, una tarea finaliza al final de la ejecución de código. En ese momento, el host llama al método `ICLRTask::ExitTask` para destruir asociado `ICLRTask`. Sin embargo, las tareas también se pueden reciclar mediante una llamada a `ICLRTask::Reset`, lo que permite el `ICLRTask` instancia que se utilizará de nuevo. Este enfoque evita la sobrecarga que supone crear y destruir instancias repetidamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
