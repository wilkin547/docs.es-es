---
description: 'Más información acerca de: IHostSecurityManager:: RevertToSelf (método)'
title: IHostSecurityManager::RevertToSelf (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.RevertToSelf
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::RevertToSelf
helpviewer_keywords:
- RevertToSelf method [.NET Framework hosting]
- IHostSecurityManager::RevertToSelf method [.NET Framework hosting]
ms.assetid: 189f28f8-f9a1-4192-aedc-91084e4f8b99
topic_type:
- apiref
ms.openlocfilehash: f3488653bcb498c7521de0e368b33bc444967f21
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671508"
---
# <a name="ihostsecuritymanagerreverttoself-method"></a>IHostSecurityManager::RevertToSelf (Método)

Finaliza la suplantación de la identidad del usuario actual y devuelve el token del subproceso original.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RevertToSelf ();  
```  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`RevertToSelf` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 `RevertToSelf` se llama a para volver al token del subproceso original, después de una llamada anterior al método [ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostSecurityContext (Interfaz)](ihostsecuritycontext-interface.md)
- [IHostSecurityManager (Interfaz)](ihostsecuritymanager-interface.md)
- [Método ImpersonateLoggedOnUser](ihostsecuritymanager-impersonateloggedonuser-method.md)
