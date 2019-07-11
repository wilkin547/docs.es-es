---
title: IHostSyncManager::CreateCrstWithSpinCount (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateCrstWithSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateCrstWithSpinCount
helpviewer_keywords:
- CreateCrstWithSpinCount method [.NET Framework hosting]
- IHostSyncManager::CreateCrstWithSpinCount method [.NET Framework hosting]
ms.assetid: 7280fa8c-3639-4abf-91cb-bc343da742d1
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 16fcc631e7e734e1bce4566f31d209a8433fbfdf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67753443"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a>IHostSyncManager::CreateCrstWithSpinCount (Método)
Crea un objeto de sección crítica con recuento de rotación para la sincronización.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `dwSpinCount`  
 [in] Especifica el recuento circular para el objeto de sección crítica.  
  
 `ppCrst`  
 [out] Un puntero a la dirección de un [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) de instancia, o null si no se pudo crear la sección crítica.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|DESCRIPCIÓN|  
|-------------|-----------------|  
|S_OK|`CreateCrstWithSpinCount` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear la sección crítica solicitada.|  
  
## <a name="remarks"></a>Comentarios  
 Un recuento de rotación se usa solo en un sistema multiprocesador. El recuento circular especifica el número de veces que un subproceso que realiza la llamada debe girar antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no está disponible. Si la sección crítica deja de estar disponible durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera. `CreateCrstWithSpinCount` refleja el Win32 `InitializeCriticalSectionAndSpinCount` función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostSemaphore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
