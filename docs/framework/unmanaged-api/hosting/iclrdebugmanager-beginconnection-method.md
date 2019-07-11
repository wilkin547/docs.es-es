---
title: ICLRDebugManager::BeginConnection (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebugManager.BeginConnection
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRDebugManager::BeginConnection
helpviewer_keywords:
- ICLRDebugManager::BeginConnection method [.NET Framework hosting]
- BeginConnection method [.NET Framework hosting]
ms.assetid: bdd98146-ff4d-4150-a264-a4c1a32d31f3
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 888c9aa092d8eb01f2c0a7b915721828055a6f28
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67773171"
---
# <a name="iclrdebugmanagerbeginconnection-method"></a>ICLRDebugManager::BeginConnection (Método)
Establece una nueva conexión entre el host y el depurador para asociar una lista de tareas con un identificador y un nombre descriptivo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BeginConnection (  
    [in] CONNID dwConnectionId,  
    [in, string] wchar_t* szConnectionName  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwConnectionId`  
 [in] Un identificador para asociar a la lista de tareas de common language runtime (CLR).  
  
 `szConnectionName`  
 [in] Un nombre descriptivo para asociar a la lista de tareas CLR.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`BeginConnection` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Después de un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`dwConnectionId` es cero, o `BeginConnection` ya se ha llamado mediante este `dwConnectionId` valor, o `szConnectionName` era null.|  
|E_OUTOFMEMORY|No hay suficiente memoria podría asignar para contener la lista de tareas asociadas con esta conexión.|  
  
## <a name="remarks"></a>Comentarios  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md), y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.  
  
> [!IMPORTANT]
>  Estos tres métodos deben llamarse en un orden específico para cada conjunto de tareas. `BeginConnection` se llama en primer lugar para establecer una conexión nueva. `SetConnectionTasks` se llama a continuación para proporcionar el conjunto de tareas que se asociará con esa conexión. `EndConnection` se llama en último lugar para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar llamadas para las conexiones diferentes.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRDebugManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [EndConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [SetConnectionTasks (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
