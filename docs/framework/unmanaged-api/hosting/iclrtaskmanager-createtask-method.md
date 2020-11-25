---
title: ICLRTaskManager::CreateTask (Método)
ms.date: 03/30/2017
api_name:
- ICLRTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTaskManager::CreateTask
helpviewer_keywords:
- ICLRTaskManager::CreateTask method [.NET Framework hosting]
- CreateTask method, ICLRTaskManager interface [.NET Framework hosting]
ms.assetid: eea570d9-2e53-4320-9ea0-eb777bf9dcf3
topic_type:
- apiref
ms.openlocfilehash: c8d18b78cf0185271eae763892610d13f76e42ab
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734002"
---
# <a name="iclrtaskmanagercreatetask-method"></a>ICLRTaskManager::CreateTask (Método)

Solicita explícitamente que el Common Language Runtime (CLR) cree una nueva tarea.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateTask (  
    [out] ICLRTask **pTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pTask`  
 enuncia Puntero a la dirección de una [ICLRTask](iclrtask-interface.md)recién creada, o null si no se pudo crear la tarea.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No hay suficiente memoria disponible para asignar el recurso solicitado.|  
  
## <a name="remarks"></a>Comentarios  

 CLR crea una nueva tarea automáticamente durante la inicialización, cuando el código de usuario crea un subproceso mediante los tipos del <xref:System.Threading> espacio de nombres o cuando aumenta el tamaño del grupo de subprocesos. También crea tareas cuando el código no administrado realiza una llamada a una función administrada.  
  
 `CreateTask` permite al host realizar una solicitud explícita de que CLR cree una nueva tarea. Por ejemplo, el host puede invocar este método para preinicializar las estructuras de datos.  
  
> [!IMPORTANT]
> La nueva tarea se devuelve en un estado suspendido y permanece suspendida hasta que el host llama explícitamente a [IHostTask:: Start](ihosttask-start-method.md).  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
