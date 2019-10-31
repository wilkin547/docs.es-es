---
title: ICLRTask::SwitchIn (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask.SwitchIn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask::SwitchIn
helpviewer_keywords:
- ICLRTask::SwitchIn method [.NET Framework hosting]
- SwitchIn method [.NET Framework hosting]
ms.assetid: 3d37ce20-aa65-4043-8f13-7c728b5d8a52
topic_type:
- apiref
ms.openlocfilehash: fbfd44c8e20bc75638d6356fe405f02790da8ac7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124620"
---
# <a name="iclrtaskswitchin-method"></a>ICLRTask::SwitchIn (Método)
Notifica a la Common Language Runtime (CLR) que la tarea que la instancia de [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) actual representa está ahora en un estado operativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SwitchIn (  
    [in] HANDLE threadHandle  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `threadHandle`  
 de Identificador del subproceso físico en el que se está ejecutando la tarea representada por la instancia de `ICLRTask` actual.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SwitchIn` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|se llamó a `SwitchIn` sin una llamada anterior al [método SwitchOut](../../../../docs/framework/unmanaged-api/hosting/iclrtask-switchout-method.md).|  
  
## <a name="remarks"></a>Comentarios  
 El parámetro `threadHandle` representa un identificador para el subproceso del sistema operativo en el que se ha programado la tarea representada por la instancia de `ICLRTask` actual. Si se ha producido la suplantación en este subproceso, debe llamar a [IHostSecurityManager:: RevertToSelf](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-reverttoself-method.md) antes de cambiar en la tarea.  
  
> [!NOTE]
> Una llamada a `SwitchIn` sin una llamada anterior a `SwitchOut` producirá un error con un valor HRESULT de HOST_E_INVALIDOPERATION.  
  
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
