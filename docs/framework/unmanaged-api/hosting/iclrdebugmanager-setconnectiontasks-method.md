---
title: ICLRDebugManager::SetConnectionTasks (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.SetConnectionTasks
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::SetConnectionTasks
helpviewer_keywords:
- SetConnectionTasks method [.NET Framework hosting]
- ICLRDebugManager::SetConnectionTasks method [.NET Framework hosting]
ms.assetid: b38bbc9a-872c-41a9-b8c3-ca011d25456a
topic_type:
- apiref
ms.openlocfilehash: 5df01ac929874d00a5fddda83f532927dc46d67b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719845"
---
# <a name="iclrdebugmanagersetconnectiontasks-method"></a>ICLRDebugManager::SetConnectionTasks (Método)

Asocia una lista de instancias de [ICLRTask](iclrtask-interface.md) con un identificador y un nombre descriptivo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetConnectionTasks (  
    [in] CONNID id,  
    [in] DWORD dwCount,  
    [in, size_is(dwCount)] ICLRTask **ppCLRTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `id`  
 de Identificador específico del host para la conexión a la que se va a asociar la `ppCLRTask` matriz.  
  
 `dwCount`  
 de Número de miembros de `ppCLRTask` . Este número debe ser mayor que cero.  
  
 `ppCLRTask`  
 de Matriz de `ICLRTask` punteros que se va a asociar a la conexión identificada por `id` . Esta matriz debe contener al menos un miembro.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetConnectionTasks` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|No se ha llamado a [BeginConnection](iclrdebugmanager-beginconnection-method.md) con este valor de `id` , o `dwCount` o `id` es cero, o uno de los elementos de `ppCLRTask` es NULL.|  
  
## <a name="remarks"></a>Comentarios  

 [ICLRDebugManager](iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection` , `SetConnectionTasks` y [EndConnection](iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.  
  
> [!IMPORTANT]
> Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas. `BeginConnection` se llama primero a para establecer una nueva conexión. `SetConnectionTasks` se llama a junto a para proporcionar el conjunto de tareas que se van a asociar a esa conexión. `EndConnection` se llama a Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRControl (Interfaz)](iclrcontrol-interface.md)
- [ICLRDebugManager (Interfaz)](iclrdebugmanager-interface.md)
- [Método BeginConnection](iclrdebugmanager-beginconnection-method.md)
- [Método EndConnection](iclrdebugmanager-endconnection-method.md)
- [IHostControl (Interfaz)](ihostcontrol-interface.md)
