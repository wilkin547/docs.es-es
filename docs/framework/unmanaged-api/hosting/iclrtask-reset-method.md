---
title: ICLRTask::Reset (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.Reset
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::Reset
helpviewer_keywords:
- ICLRTask::Reset method [.NET Framework hosting]
- Reset method, ICLRTask interface [.NET Framework hosting]
ms.assetid: 1bfb5d3a-0ffd-4bb4-9bf6-aec00cb675b7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 13bf7342157de48e0183537afea2f2e53d1498dd
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/09/2019
ms.locfileid: "59300312"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset (Método)
Informa a common language runtime (CLR) que el host ha completado una tarea y permite a CLR reutilizar actual [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) instancia para representar otra tarea.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fFull`  
 [in] `true`, si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con los subprocesos además de la información de seguridad y la configuración regional actual relacionada con `ICLRTask` instancia; en caso contrario, `false`.  
  
 Si el valor es `true`, el tiempo de ejecución restablece los datos que se almacenaron con <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Reset` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada. correctamente|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR puede reciclar creado anteriormente `ICLRTask` instancias para evitar la sobrecarga que supone crear repetidamente nuevas instancias cada vez que necesita una tarea nueva. El host habilita esta característica mediante una llamada a `ICLRTask::Reset` en lugar de [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) cuándo se ha completado una tarea. La lista siguiente resume el ciclo de vida normal de una `ICLRTask` instancia:  
  
1. El tiempo de ejecución crea un nuevo `ICLRTask` instancia.  
  
2. El runtime llama a [IHostTaskManager:: GetCurrentTask](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea actual del host.  
  
3. El runtime llama a [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) para asociar la nueva instancia de la tarea del host.  
  
4. La tarea se ejecuta y finaliza.  
  
5. El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask`.  
  
 `Reset` modifica este escenario de dos maneras. En el paso 5 anterior, el host llama `Reset` para restablecer la tarea a un estado limpio y, a continuación, se desacopla el `ICLRTask` instancia de su asociado [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia. Si lo desea, el host puede almacenar en caché también el `IHostTask` instancia para su reutilización. En el paso 1 anterior, el tiempo de ejecución extrae un reciclado `ICLRTask` desde la memoria caché en lugar de crear una nueva instancia.  
  
 Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables. Cuando el host destruye uno de sus `IHostTask` instancias, destruye el correspondiente `ICLRTask` mediante una llamada a `ExitTask`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
