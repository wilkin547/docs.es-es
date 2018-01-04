---
title: IHostTaskManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostTaskManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostTaskManager
helpviewer_keywords: IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9573891a2c27a2a92eccd0522f84175effa8037a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para trabajar con tareas a través del host en lugar de utilizar las funciones de sistema operativo estándar de subprocesos o fibras.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginDelayAbort (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica al host que el código administrado está entrando en un período en el que no se debe anular la tarea actual.|  
|[BeginThreadAffinity (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se mueven a otro subproceso del sistema operativo.|  
|[CallNeedsHostHook (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Permite al host especificar si common language runtime puede procesar en línea la llamada especificada a una función no administrada.|  
|[CreateTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Solicita que el host cree una nueva tarea.|  
|[EndDelayAbort (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica al host que el código administrado está saliendo del período en el que no se debe anular la tarea actual, después de una llamada anterior a `BeginDelayAbort`.|  
|[EndThreadAffinity (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se mueven a otro subproceso del sistema operativo, después de una llamada anterior a `BeginThreadAffinity`.|  
|[EnterRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica al host que una llamada a un método no administrado, como método de invocación de plataforma está devolviendo el control de la ejecución a CLR.|  
|[GetCurrentTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso de sistema operativo desde el que se realiza esta llamada.|  
|[GetStackGuarantee (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Obtiene la cantidad de espacio de pila que está garantizado que estén disponibles cuando se complete una operación de pila, pero antes del cierre de un proceso.|  
|[LeaveRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica al host que el código administrado está a punto de realizar una llamada a una función no administrada.|  
|[ReverseEnterRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica al host que se está realizando una llamada en common language runtime (CLR) de código no administrado.|  
|[ReverseLeaveRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica al host que control está abandonando CLR y escribir una función no administrada que a su vez, se ha llamado desde el código administrado.|  
|[SetCLRTaskManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Proporciona el host con un puntero de interfaz a una [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) instancia implementada por CLR.|  
|[SetLocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica al host que CLR ha cambiado la configuración regional en la tarea actual.|  
|[SetStackGuarantee (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Reservado para uso interno.|  
|[SetUILocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica al host que se ha cambiado la configuración regional de interfaz de usuario en la tarea actual.|  
|[Sleep (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica al host que la tarea actual se va a suspender.|  
|[SwitchToTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica al host que debe cambiar la tarea actual.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostTaskManager`permite que el CLR para crear y administrar tareas, proporcionar enlaces para el host para realizar una acción cuando transfiera el control del código administrado al código no administrado y viceversa y para especificar determinadas acciones el host puede y no se puede realizar durante la ejecución del código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
