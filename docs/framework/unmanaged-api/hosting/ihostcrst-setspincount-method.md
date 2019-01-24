---
title: IHostCrst::SetSpinCount (Método)
ms.date: 03/30/2017
api_name:
- IHostCrst.SetSpinCount
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostCrst::SetSpinCount
helpviewer_keywords:
- IHostCrst::SetSpinCount method [.NET Framework hosting]
- SetSpinCount method [.NET Framework hosting]
ms.assetid: 863fc8ce-9b8a-477e-8dd8-75c8544bb43a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ddae8f64eca348afa337b986ac81d59c37e51701
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54504306"
---
# <a name="ihostcrstsetspincount-method"></a>IHostCrst::SetSpinCount (Método)
Establece el recuento circular actual [IHostCrst](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md) instancia.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetSpinCount (  
    [in] DWORD dwSpinCount  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwSpinCount`  
 [in] El nuevo recuento de rotación actual `IHostCrst` instancia.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetSpinCount` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|Common language runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|La llamada ha agotado el tiempo de espera.|  
|HOST_E_NOT_OWNER|El llamador no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.|  
|E_FAIL|Se ha producido un error irrecuperable desconocido. Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso. Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 En sistemas multiprocesador, si la sección crítica representada por el actual `IHostCrst` instancia no está disponible, un subproceso que realiza la llamada da `dwSpinCount` veces antes de llamar a [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md) en un semáforo asociado con la sección crítica. Si la sección crítica deja de estar disponible durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera.  
  
 El uso de `dwSpinCount` es idéntico al uso del parámetro del mismo nombre en Win32 `InitializeCriticalSectionAndSpinCount` función.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostCrst (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostcrst-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
