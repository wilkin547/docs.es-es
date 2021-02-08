---
description: 'Más información acerca de: IHostSyncManager:: CreateCrstWithSpinCount ((método)'
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
ms.openlocfilehash: 3c43f1a3d52eb7174844ecb4079cf54413f20853
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784826"
---
# <a name="ihostsyncmanagercreatecrstwithspincount-method"></a>IHostSyncManager::CreateCrstWithSpinCount (Método)

Crea un objeto de sección crítica con el recuento de giros para la sincronización.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateCrstWithSpinCount (  
    [in]  DWORD dwSpinCount,  
    [out] IHostCrst** ppCrst  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwSpinCount`  
 de Especifica el recuento de giros para el objeto de sección crítica.  
  
 `ppCrst`  
 enuncia Un puntero a la dirección de una instancia de [IHostCrst](ihostcrst-interface.md) o null si no se pudo crear la sección crítica.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateCrstWithSpinCount` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear la sección crítica solicitada.|  
  
## <a name="remarks"></a>Observaciones  

 Un recuento de giros solo se utiliza en un sistema de varios procesadores. El recuento de giros especifica el número de veces que un subproceso de llamada debe girar antes de realizar una operación de espera en un semáforo que está asociado a una sección crítica no disponible. Si la sección crítica se vuelve gratuita durante la operación de giro, el subproceso que realiza la llamada evita la operación de espera. `CreateCrstWithSpinCount` refleja la función de Win32 `InitializeCriticalSectionAndSpinCount` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostSemaphore (Interfaz)](ihostsemaphore-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
