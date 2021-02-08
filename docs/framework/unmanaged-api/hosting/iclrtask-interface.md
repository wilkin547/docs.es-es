---
description: 'Más información acerca de: ICLRTask (interfaz)'
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
ms.openlocfilehash: f48216b19dd2c1d0d0ba64117169b74767dbdf2b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799558"
---
# <a name="iclrtask-interface"></a>ICLRTask (Interfaz)

Proporciona métodos que permiten al host realizar solicitudes del Common Language Runtime (CLR) o proporcionar una notificación al CLR sobre la tarea asociada.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Abort (Método)](iclrtask-abort-method.md)|Solicita que CLR anule la tarea que la instancia actual `ICLRTask` representa.|  
|[Método ExitTask](iclrtask-exittask-method.md)|Notifica a CLR que la tarea asociada a la instancia actual `ICLRTask` está finalizando e intenta cerrar la tarea correctamente.|  
|[Método GetMemStats](iclrtask-getmemstats-method.md)|Obtiene información estadística sobre el uso de recursos de memoria por parte de la tarea representada por la `ICLRTask` instancia actual.|  
|[Método LocksHeld](iclrtask-locksheld-method.md)|Obtiene el número de bloqueos mantenidos actualmente en la tarea.|  
|[Método NeedsPriorityScheduling](iclrtask-needspriorityscheduling-method.md)|Obtiene un valor que indica si el host debe asignar una prioridad alta para volver a programar la tarea representada por la `ICLRTask` instancia actual.|  
|[Reset (Método)](iclrtask-reset-method.md)|Informa a CLR de que el host ha completado una tarea y permite al CLR volver a usar la instancia actual `ICLRTask` para representar otra tarea.|  
|[RudeAbort (Método)](iclrtask-rudeabort-method.md)|Hace que CLR anule inmediatamente la tarea representada por la `ICLRTask` instancia actual, sin ninguna garantía de que se ejecuten los finalizadores.|  
|[Método SetTaskIdentifier](iclrtask-settaskidentifier-method.md)|Establece un identificador único para la tarea representada por la `ICLRTask` instancia actual, para su uso en la depuración.|  
|[Método SwitchIn](iclrtask-switchin-method.md)|Notifica a CLR que la tarea representada por la `ICLRTask` instancia actual está en un estado operativo.|  
|[Método SwitchOut](iclrtask-switchout-method.md)|Notifica a CLR que la tarea representada por la `ICLRTask` instancia actual ya no se encuentra en un estado operativo.|  
|[Método YieldTask](iclrtask-yieldtask-method.md)|Solicita que el CLR haga que el tiempo de procesador esté disponible para otras tareas. CLR no ofrece ninguna garantía de que la tarea se ponga en un estado en el que pueda dar lugar a un tiempo de procesamiento.|  
  
## <a name="remarks"></a>Observaciones  

 `ICLRTask`Es la representación de una tarea para el CLR. En cualquier momento durante la ejecución del código, una tarea puede describirse como en ejecución o en espera para ejecutarse. El host llama al `ICLRTask::SwitchIn` método para notificar a CLR que la tarea que la `ICLRTask` instancia actual representa está ahora en un estado operativo. Después de una llamada a `ICLRTask::SwitchIn` , el host puede programar la tarea en cualquier subproceso del sistema operativo, excepto en los casos en que el tiempo de ejecución requiere la afinidad de subprocesos, tal y como se especifica en las llamadas a los métodos [IHostTaskManager:: BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md) y [IHostTaskManager:: EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md) . En algún momento posterior, el sistema operativo podría decidir quitar la tarea del subproceso y colocarla en un estado de no ejecución. Por ejemplo, esto puede ocurrir cuando la tarea se bloquea en primitivas de sincronización o espera a que se completen las operaciones de e/s. El host llama a [SwitchOut](iclrtask-switchout-method.md) para notificar a CLR que la tarea representada por la instancia actual ya `ICLRTask` no se encuentra en un estado operativo.  
  
 Normalmente, una tarea finaliza al final de la ejecución del código. En ese momento, el host llama `ICLRTask::ExitTask` a para destruir el objeto asociado `ICLRTask` . Sin embargo, las tareas también se pueden reciclar mediante una llamada a `ICLRTask::Reset` , lo que permite `ICLRTask` volver a usar la instancia. Este enfoque evita la sobrecarga que supone la creación y destrucción repetidas de instancias.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
- [ICLRTask2 (Interfaz)](iclrtask2-interface.md)
