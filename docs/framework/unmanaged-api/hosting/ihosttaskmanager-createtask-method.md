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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0a154aeafed9bc4de63dea3fe7fc32e2daee7b96
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67749726"
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
 [in] El tamaño solicitado, en bytes, de la pila solicitada, o 0 (cero) para el tamaño predeterminado.  
  
 `pStartAddress`  
 [in] Un puntero a la función de la tarea consiste en ejecutar.  
  
 `pParameter`  
 [in] Un puntero a los datos de usuario que se pasará a la función, o null si la función no toma ningún parámetro.  
  
 `ppTask`  
 [out] Un puntero a la dirección de un [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md) instancia creada por el host, o null si no se puede crear la tarea. La tarea permanece en estado suspendido hasta que se inicia explícitamente mediante una llamada a [IHostTask](../../../../docs/framework/unmanaged-api/hosting/ihosttask-start-method.md).  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`CreateTask` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear la tarea solicitada.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a `CreateTask` para solicitar que el host cree una nueva tarea. El host devuelve un puntero de interfaz a un `IHostTask` instancia. La tarea devuelta debe permanecer suspendida hasta que se inicia explícitamente mediante una llamada a `IHostTask::Start`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
