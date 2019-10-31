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
ms.openlocfilehash: 17fca3e5a2d763277d3a5f9f72e2d35be6fc350c
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124635"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset (Método)
Informa al Common Language Runtime (CLR) de que el host ha completado una tarea y permite al CLR volver a usar la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual para representar otra tarea.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fFull`  
 [in] `true`, si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con el subproceso, además de la información de seguridad y configuración regional relacionada con la instancia de `ICLRTask` actual; de lo contrario, `false`.  
  
 Si el valor es `true`, el tiempo de ejecución restablece los datos almacenados mediante <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A>.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Reset` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada. successfully|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 CLR puede reciclar las instancias de `ICLRTask` creadas previamente para evitar la sobrecarga que supone crear instancias nuevas de forma repetida cada vez que necesita una nueva tarea. El host habilita esta característica mediante una llamada a `ICLRTask::Reset` en lugar de a [ICLRTask:: ExitTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-exittask-method.md) cuando ha completado una tarea. En la lista siguiente se resume el ciclo de vida normal de una instancia de `ICLRTask`:  
  
1. El tiempo de ejecución crea una nueva instancia de `ICLRTask`.  
  
2. El Runtime llama a [IHostTaskManager:: getcurrenttask (](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea de host actual.  
  
3. El Runtime llama a [IHostTask:: SetCLRTask (](../../../../docs/framework/unmanaged-api/hosting/ihosttask-setclrtask-method.md) para asociar la nueva instancia de a la tarea de host.  
  
4. La tarea se ejecuta y completa.  
  
5. El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask`.  
  
 `Reset` modifica este escenario de dos maneras. En el paso 5 anterior, el host llama a `Reset` para restablecer la tarea a un estado limpio y, a continuación, desacopla la instancia de `ICLRTask` de su instancia de [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) asociada. Si lo desea, el host también puede almacenar en caché la instancia de `IHostTask` para su reutilización. En el paso 1 anterior, el tiempo de ejecución extrae un `ICLRTask` reciclado de la memoria caché en lugar de crear una nueva instancia.  
  
 Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables. Cuando el host destruye una de sus instancias de `IHostTask`, destruye el `ICLRTask` correspondiente llamando a `ExitTask`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
