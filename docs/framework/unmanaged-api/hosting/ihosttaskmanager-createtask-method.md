---
title: IHostTaskManager::CreateTask (Método)
ms.date: 03/30/2017
api_name:
- IHostTaskManager.CreateTask
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostTaskManager::CreateTask
helpviewer_keywords:
- CreateTask method, IHostTaskManager interface [.NET Framework hosting]
- IHostTaskManager::CreateTask method [.NET Framework hosting]
ms.assetid: a6f8ad36-61e1-42b0-9db2-add575646d18
topic_type:
- apiref
ms.openlocfilehash: 4037ffe63d8ebfca67cbd0b3293d36be7481b1bd
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501422"
---
# <a name="ihosttaskmanagercreatetask-method"></a>IHostTaskManager::CreateTask (Método)
Solicita que el host cree una nueva tarea.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateTask (  
    [in]  DWORD stacksize,
    [in]  LPTHREAD_START_ROUTINE pStartAddress,  
    [in]  PVOID pParameter,  
    [out] IHostTask **ppTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `stacksize`  
 de Tamaño solicitado, en bytes, de la pila solicitada o 0 (cero) para el tamaño predeterminado.  
  
 `pStartAddress`  
 de Puntero a la función que va a ejecutar la tarea.  
  
 `pParameter`  
 de Un puntero a los datos de usuario que se van a pasar a la función, o null si la función no toma ningún parámetro.  
  
 `ppTask`  
 enuncia Un puntero a la dirección de una instancia de [IHostTask](ihosttask-interface.md) creada por el host, o null si no se puede crear la tarea. La tarea permanece en estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask:: Start](ihosttask-start-method.md).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateTask`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear la tarea solicitada.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama `CreateTask` a para solicitar que el host cree una nueva tarea. El host devuelve un puntero de interfaz a una `IHostTask` instancia de. La tarea devuelta debe permanecer suspendida hasta que se inicie explícitamente mediante una llamada a `IHostTask::Start` .  
  
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
