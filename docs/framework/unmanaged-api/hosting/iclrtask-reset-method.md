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
ms.openlocfilehash: 15004238ee296e44ae77cd8739b7f62ea2a7a100
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762976"
---
# <a name="iclrtaskreset-method"></a>ICLRTask::Reset (Método)
Informa al Common Language Runtime (CLR) de que el host ha completado una tarea y permite al CLR volver a usar la instancia de [ICLRTask](iclrtask-interface.md) actual para representar otra tarea.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT Reset (  
    [in] BOOL fFull  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fFull`  
 [in] `true` , si el tiempo de ejecución debe restablecer todos los valores estáticos relacionados con subprocesos, además de la información de seguridad y configuración regional relacionada con la `ICLRTask` instancia actual; de lo contrario, `false` .  
  
 Si el valor es `true` , el tiempo de ejecución restablece los datos almacenados mediante <xref:System.Threading.Thread.AllocateDataSlot%2A> o <xref:System.Threading.Thread.AllocateNamedDataSlot%2A> .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`Reset`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada. successfully|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 CLR puede reciclar `ICLRTask` las instancias creadas previamente para evitar la sobrecarga que supone crear instancias nuevas de forma repetida cada vez que necesita una nueva tarea. El host habilita esta característica llamando a `ICLRTask::Reset` en lugar de a [ICLRTask:: ExitTask](iclrtask-exittask-method.md) cuando ha completado una tarea. En la lista siguiente se resume el ciclo de vida normal de una `ICLRTask` instancia de:  
  
1. El tiempo de ejecución crea una nueva `ICLRTask` instancia de.  
  
2. El Runtime llama a [IHostTaskManager:: getcurrenttask (](ihosttaskmanager-getcurrenttask-method.md) para obtener una referencia a la tarea de host actual.  
  
3. El Runtime llama a [IHostTask:: SetCLRTask (](ihosttask-setclrtask-method.md) para asociar la nueva instancia de a la tarea de host.  
  
4. La tarea se ejecuta y completa.  
  
5. El host destruye la tarea mediante una llamada a `ICLRTask::ExitTask` .  
  
 `Reset`modifica este escenario de dos maneras. En el paso 5 anterior, el host llama `Reset` a para restablecer la tarea a un estado limpio y, a continuación, desacopla la `ICLRTask` instancia de su instancia de [IHostTask](ihosttask-interface.md) asociada. Si lo desea, el host también puede almacenar en caché la `IHostTask` instancia para su reutilización. En el paso 1 anterior, el tiempo de ejecución extrae un reciclado `ICLRTask` de la memoria caché en lugar de crear una nueva instancia.  
  
 Este enfoque funciona bien cuando el host también tiene un grupo de tareas de trabajo reutilizables. Cuando el host destruye una de sus `IHostTask` instancias, destruye el correspondiente `ICLRTask` mediante una llamada a `ExitTask` .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
