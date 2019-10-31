---
title: ICLROnEventManager::RegisterActionOnEvent (Método)
ms.date: 03/30/2017
api_name:
- ICLROnEventManager.RegisterActionOnEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLROnEventManager::RegisterActionOnEvent
helpviewer_keywords:
- ICLROnEventManager::RegisterActionOnEvent method [.NET Framework hosting]
- RegisterActionOnEvent method [.NET Framework hosting]
ms.assetid: b944cf49-918d-4c4e-993b-77d097a52550
topic_type:
- apiref
ms.openlocfilehash: 4068166438c524ad1c0ed4efe455b1f66b6641d5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140828"
---
# <a name="iclroneventmanagerregisteractiononevent-method"></a>ICLROnEventManager::RegisterActionOnEvent (Método)
Registra un puntero de devolución de llamada para el evento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RegisterActionOnEvent (  
    [in] EClrEvent event,  
    [in] IActionOnCLREvent *pAction  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `event`  
 de Uno de los valores de [EClrEvent](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md) , que indica el evento para el que se va a registrar el puntero de devolución de llamada descrito por `pAction`.  
  
 `pAction`  
 de Un puntero a un objeto [IActionOnCLREvent](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md) al que se llama cuando se activa el evento registrado.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`RegisterActionOnEvent` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 El host puede registrar devoluciones de llamada para uno o ambos de los dos tipos de eventos descritos por `EClrEvent`. El host obtiene la interfaz de `ICLROnEventManager` llamando al método [ICLRControl:: GetCLRManager (](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) .  
  
> [!NOTE]
> Los eventos que `RegisterActionOnEvent` registra se pueden desencadenar más de una vez y desde distintos subprocesos para indicar una descarga o la deshabilitación de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EClrEvent (enumeración)](../../../../docs/framework/unmanaged-api/hosting/eclrevent-enumeration.md)
- [IActionOnCLREvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iactiononclrevent-interface.md)
- [ICLRControl (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [ICLROnEventManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md)
