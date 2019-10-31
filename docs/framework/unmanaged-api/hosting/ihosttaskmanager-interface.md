---
title: IHostTaskManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostTaskManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager
helpviewer_keywords:
- IHostTaskManager interface [.NET Framework hosting]
ms.assetid: 4a0b05b9-3ef1-4607-b7c8-bd4dd43647a0
topic_type:
- apiref
ms.openlocfilehash: 470e2ac06f433dc12d66f6cac97337a6de1d8183
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133021"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager (Interfaz)
Proporciona métodos que permiten al Common Language Runtime (CLR) trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginDelayAbort (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-begindelayabort-method.md)|Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.|  
|[BeginThreadAffinity (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-beginthreadaffinity-method.md)|Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo.|  
|[CallNeedsHostHook (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-callneedshosthook-method.md)|Permite al host especificar si el Common Language Runtime puede alinear la llamada especificada a una función no administrada.|  
|[CreateTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-createtask-method.md)|Solicita que el host cree una nueva tarea.|  
|[EndDelayAbort (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enddelayabort-method.md)|Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe anular, siguiendo una llamada anterior a `BeginDelayAbort`.|  
|[EndThreadAffinity (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-endthreadaffinity-method.md)|Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo, siguiendo una llamada anterior a `BeginThreadAffinity`.|  
|[EnterRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-enterruntime-method.md)|Notifica al host que una llamada a un método no administrado, como un método de invocación de plataforma, devuelve el control de la ejecución a CLR.|  
|[GetCurrentTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md)|Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.|  
|[GetStackGuarantee (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getstackguarantee-method.md)|Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.|  
|[LeaveRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-leaveruntime-method.md)|Notifica al host que el código administrado está a punto de hacer una llamada a una función no administrada.|  
|[ReverseEnterRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseenterruntime-method.md)|Notifica al host que se está realizando una llamada en el Common Language Runtime (CLR) desde el código no administrado.|  
|[ReverseLeaveRuntime (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-reverseleaveruntime-method.md)|Notifica al host que el control está saliendo del CLR y entra en una función no administrada que, a su vez, se llama desde el código administrado.|  
|[SetCLRTaskManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setclrtaskmanager-method.md)|Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md) implementada por CLR.|  
|[SetLocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setlocale-method.md)|Notifica al host que CLR ha cambiado la configuración regional en la tarea actual.|  
|[SetStackGuarantee (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setstackguarantee-method.md)|Reservado para uso interno.|  
|[SetUILocale (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-setuilocale-method.md)|Notifica al host que se ha cambiado la configuración regional de la interfaz de usuario en la tarea actual.|  
|[Sleep (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-sleep-method.md)|Notifica al host que la tarea actual va a entrar en suspensión.|  
|[SwitchToTask (método)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-switchtotask-method.md)|Notifica al host que debe desactivar la tarea actual.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostTaskManager` permite que CLR cree y administre tareas, para proporcionar enlaces para que el host tome medidas cuando el control se transfiere del código administrado al código no administrado y viceversa, y para especificar ciertas acciones que el host puede y no puede realizar durante la ejecución del código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
