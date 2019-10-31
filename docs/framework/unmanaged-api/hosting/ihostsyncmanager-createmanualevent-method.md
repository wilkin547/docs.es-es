---
title: IHostSyncManager::CreateManualEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateManualEvent
helpviewer_keywords:
- CreateManualEvent method [.NET Framework hosting]
- IHostSyncManager::CreateManualEvent method [.NET Framework hosting]
ms.assetid: 68661fbd-09cf-46dc-890b-e694f8a3880a
topic_type:
- apiref
ms.openlocfilehash: 13679b4d40e660dfdd18e6fbafe19226b2ffda37
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195869"
---
# <a name="ihostsyncmanagercreatemanualevent-method"></a>IHostSyncManager::CreateManualEvent (Método)
Crea un objeto de evento de restablecimiento manual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateManualEvent (  
    [in]  BOOL bInitialState,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bInitialState`  
 [in] `true`, si el objeto está señalado; de lo contrario, `false`.  
  
 `ppEvent`  
 enuncia Un puntero a la dirección de una instancia de [IHostManualEvent](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md) , o null si no se pudo crear el evento.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateManualEvent` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear el objeto de evento solicitado.|  
  
## <a name="remarks"></a>Comentarios  
 `CreateManualEvent` crea un `IHostManualEvent`, un objeto de evento de restablecimiento manual que requiere una llamada al método [IHostManualEvent:: RESET](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md) para establecerlo en un estado no señalado. `CreateManualEvent` refleja la función de `CreateEvent` de Win32 con un valor de `true` especificado para el parámetro `bManualReset`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostManualEvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
