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
ms.openlocfilehash: 10efe853c9a7ad7676058bc01b07063c557623d8
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95699227"
---
# <a name="ihosttask-interface"></a>IHostTask (Interfaz)

Proporciona métodos que permiten al Common Language Runtime (CLR) comunicarse con el host para administrar tareas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Alert](ihosttask-alert-method.md)|Solicita que el host reactive la tarea representada por la `IHostTask` instancia actual, por lo que se puede anular la tarea.|  
|[Método GetPriority](ihosttask-getpriority-method.md)|Obtiene el nivel de prioridad del subproceso de la tarea representada por la `IHostTask` instancia actual.|  
|[Método Join](ihosttask-join-method.md)|Bloquea la tarea que realiza la llamada hasta que se completa la tarea representada por la `IHostTask` instancia actual, el intervalo de tiempo especificado transcurre o se llama a [IHostTask:: Alert](ihosttask-alert-method.md) .|  
|[Método SetCLRTask](ihosttask-setclrtask-method.md)|Asocia una instancia de la [interfaz ICLRTask](iclrtask-interface.md) a la `IHostTask` instancia actual.|  
|[Método SetPriority](ihosttask-setpriority-method.md)|Solicita que el host ajuste el nivel de prioridad del subproceso para la tarea representada por la `IHostTask` instancia actual.|  
|[Método Start](ihosttask-start-method.md)|Solicita que el host mueva la tarea representada por la `IHostTask` instancia actual de un estado suspendido a un estado activo, en el que se puede ejecutar el código.|  
  
## <a name="remarks"></a>Comentarios  

 CLR llama a los métodos definidos por `IHostTask` para iniciar una tarea, establecer su nivel de prioridad de subprocesos, etc.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
