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
ms.openlocfilehash: 9d5f0bb07498203d3db57ac3948efddce4f050a2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54533720"
---
# <a name="iclrtask-interface"></a>ICLRTask (Interfaz)
Proporciona métodos que permiten al host para realizar solicitudes de common language runtime (CLR), o para proporcionar una notificación al CLR acerca de la tarea asociada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-abort-method.md)|Solicita que el CLR anule la tarea que actual `ICLRTask` representa la instancia.|  
|[ExitTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md)|Notifica a CLR que la tarea asociada con el actual `ICLRTask` instancia está finalizando e intenta cerrar la tarea correctamente.|  
|[GetMemStats (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-getmemstats-method.md)|Obtiene información estadística sobre el uso de recursos de memoria por la tarea representada por el actual `ICLRTask` instancia.|  
|[LocksHeld (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-locksheld-method.md)|Obtiene el número de bloqueos mantenidos en la tarea.|  
|[NeedsPriorityScheduling (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-needspriorityscheduling-method.md)|Obtiene un valor que indica si el host debe asignar una prioridad alta a volver a programar la tarea representada por el actual `ICLRTask` instancia.|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-reset-method.md)|Informa a CLR que el host ha completado una tarea y permite a CLR reutilizar actual `ICLRTask` instancia para representar otra tarea.|  
|[RudeAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-rudeabort-method.md)|Hace que el CLR anular la tarea representada por el actual `ICLRTask` instancia inmediatamente, sin ninguna garantía de que los finalizadores se ejecutarán.|  
|[SetTaskIdentifier (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-settaskidentifier-method.md)|Establece un identificador único para la tarea representada por el actual `ICLRTask` instancia, para su uso en la depuración.|  
|[SwitchIn (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchin-method.md)|Notifica a CLR que la tarea representada por el actual `ICLRTask` instancia está en un estado operable.|  
|[SwitchOut (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md)|Notifica a CLR que la tarea representada por el actual `ICLRTask` instancia ya no está en un estado operable.|  
|[YieldTask (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-yieldtask-method.md)|Solicita el tiempo de procesador de make CLR disponible para otras tareas. El CLR no ofrece ninguna garantía de que la tarea se colocarán en un estado donde puede producir tiempo de procesamiento.|  
  
## <a name="remarks"></a>Comentarios  
 Un `ICLRTask` es la representación de una tarea de CLR. En cualquier momento durante la ejecución de código, una tarea se puede describir como corriendo o esperando para ejecutarse. El host llame a la `ICLRTask::SwitchIn` método para informar a CLR que la tarea que actual `ICLRTask` instancia representa ahora está en un estado operable. Después de llamar a `ICLRTask::SwitchIn`, el host puede programar la tarea en cualquier subproceso del sistema operativo, excepto en los casos donde el tiempo de ejecución requiere afinidad de subprocesos, tal como se especifica mediante llamadas a la [IHostTaskManager:: BeginThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md) y [IHostTaskManager:: EndThreadAffinity](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md) métodos. Poco después, el sistema operativo podría decidir quitar la tarea del subproceso y lo coloca en un estado de no ejecución. Por ejemplo, esto podría suceder siempre que la tarea se bloquea en las primitivas de sincronización, o espera a que finalicen las operaciones de E/S. El host llama [SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md) para notificar a CLR que la tarea representada por el actual `ICLRTask` instancia ya no está en un estado operable.  
  
 Normalmente, una tarea finaliza al final de la ejecución de código. En ese momento, el host llama `ICLRTask::ExitTask` destruir asociado `ICLRTask`. Sin embargo, las tareas también se pueden reciclar mediante el uso de una llamada a `ICLRTask::Reset`, lo que permite el `ICLRTask` instancia volver a usarse. Este enfoque evita la sobrecarga que supone crear y destruir instancias repetidamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
