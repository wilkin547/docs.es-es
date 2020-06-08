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
ms.openlocfilehash: 190908c675b96b8ea2d81fb0203aa16a80d6a8b4
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501409"
---
# <a name="ihosttaskmanager-interface"></a>IHostTaskManager (Interfaz)
Proporciona métodos que permiten al Common Language Runtime (CLR) trabajar con tareas a través del host en lugar de usar las funciones de fibra o de subprocesos estándar del sistema operativo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginDelayAbort](ihosttaskmanager-begindelayabort-method.md)|Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe anular.|  
|[Método BeginThreadAffinity](ihosttaskmanager-beginthreadaffinity-method.md)|Notifica al host que el código administrado está entrando en un período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo.|  
|[Método CallNeedsHostHook](ihosttaskmanager-callneedshosthook-method.md)|Permite al host especificar si el Common Language Runtime puede alinear la llamada especificada a una función no administrada.|  
|[CreateTask (Método)](ihosttaskmanager-createtask-method.md)|Solicita que el host cree una nueva tarea.|  
|[Método EndDelayAbort](ihosttaskmanager-enddelayabort-method.md)|Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe anular, siguiendo una llamada anterior a `BeginDelayAbort` .|  
|[Método EndThreadAffinity](ihosttaskmanager-endthreadaffinity-method.md)|Notifica al host que el código administrado está saliendo del período en el que la tarea actual no se debe pasar a otro subproceso del sistema operativo, siguiendo una llamada anterior a `BeginThreadAffinity` .|  
|[Método EnterRuntime](ihosttaskmanager-enterruntime-method.md)|Notifica al host que una llamada a un método no administrado, como un método de invocación de plataforma, devuelve el control de la ejecución a CLR.|  
|[Método GetCurrentTask](ihosttaskmanager-getcurrenttask-method.md)|Obtiene un puntero de interfaz a la tarea que se está ejecutando actualmente en el subproceso del sistema operativo desde el que se realiza esta llamada.|  
|[Método GetStackGuarantee](ihosttaskmanager-getstackguarantee-method.md)|Obtiene la cantidad de espacio de pila que se garantiza que está disponible después de que se complete una operación de pila, pero antes del cierre de un proceso.|  
|[Método LeaveRuntime](ihosttaskmanager-leaveruntime-method.md)|Notifica al host que el código administrado está a punto de hacer una llamada a una función no administrada.|  
|[Método ReverseEnterRuntime](ihosttaskmanager-reverseenterruntime-method.md)|Notifica al host que se está realizando una llamada en el Common Language Runtime (CLR) desde el código no administrado.|  
|[Método ReverseLeaveRuntime](ihosttaskmanager-reverseleaveruntime-method.md)|Notifica al host que el control está saliendo del CLR y entra en una función no administrada que, a su vez, se llama desde el código administrado.|  
|[Método SetCLRTaskManager](ihosttaskmanager-setclrtaskmanager-method.md)|Proporciona al host un puntero de interfaz a una instancia de [ICLRTaskManager](iclrtaskmanager-interface.md) implementada por CLR.|  
|[Método SetLocale](ihosttaskmanager-setlocale-method.md)|Notifica al host que CLR ha cambiado la configuración regional en la tarea actual.|  
|[Método SetStackGuarantee](ihosttaskmanager-setstackguarantee-method.md)|Reservado para uso interno.|  
|[Método SetUILocale](ihosttaskmanager-setuilocale-method.md)|Notifica al host que se ha cambiado la configuración regional de la interfaz de usuario en la tarea actual.|  
|[Método Sleep](ihosttaskmanager-sleep-method.md)|Notifica al host que la tarea actual va a entrar en suspensión.|  
|[Método SwitchToTask](ihosttaskmanager-switchtotask-method.md)|Notifica al host que debe desactivar la tarea actual.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostTaskManager`permite que CLR cree y administre tareas, para proporcionar enlaces para que el host tome medidas cuando el control se transfiere del código administrado al código no administrado y viceversa, y para especificar determinadas acciones que el host puede y no puede realizar durante la ejecución del código.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
