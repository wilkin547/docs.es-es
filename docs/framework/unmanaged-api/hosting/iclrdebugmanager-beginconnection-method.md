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
ms.openlocfilehash: 2ac2b0dde97b883313e1bca17c5e99855484e4aa
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126573"
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
 de Identificador que se va a asociar a la lista de tareas de Common Language Runtime (CLR).  
  
 `szConnectionName`  
 de Nombre descriptivo que se va a asociar a la lista de tareas CLR.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`BeginConnection` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_INVALIDARG|`dwConnectionId` era cero o ya se llamó a `BeginConnection` con este valor de `dwConnectionId` o `szConnectionName` era null.|  
|E_OUTOFMEMORY|No se pudo asignar memoria suficiente para contener la lista de tareas asociadas a esta conexión.|  
  
## <a name="remarks"></a>Comentarios  
 [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md) proporciona tres métodos, `BeginConnection`, [SetConnectionTasks](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)y [EndConnection](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md), para asociar listas de tareas con identificadores y nombres descriptivos.  
  
> [!IMPORTANT]
> Se debe llamar a estos tres métodos en un orden específico para cada conjunto de tareas. primero se llama a `BeginConnection` para establecer una nueva conexión. a continuación, se llama a `SetConnectionTasks` a continuación para proporcionar el conjunto de tareas que se van a asociar a esa conexión. `EndConnection` se llama Last para quitar la asociación entre la lista de tareas y el identificador y el nombre descriptivo. Sin embargo, se pueden anidar las llamadas para las distintas conexiones.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLRDebugManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md)
- [EndConnection (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-endconnection-method.md)
- [SetConnectionTasks (método)](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setconnectiontasks-method.md)
- [IHostControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
