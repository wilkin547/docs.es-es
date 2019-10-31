---
title: IHostSecurityManager::SetThreadToken (Método)
ms.date: 03/30/2017
api_name:
- IHostSecurityManager.SetThreadToken
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSecurityManager::SetThreadToken
helpviewer_keywords:
- SetThreadToken method [.NET Framework hosting]
- IHostSecurityManager::SetThreadToken method [.NET Framework hosting]
ms.assetid: e951c345-8a86-4587-911b-a1a57bc6428a
topic_type:
- apiref
ms.openlocfilehash: aa17f637ef71373697db5ce66e4a6540c5cc5fbd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139496"
---
# <a name="ihostsecuritymanagersetthreadtoken-method"></a>IHostSecurityManager::SetThreadToken (Método)
Establece un identificador para el subproceso que se está ejecutando actualmente.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetThreadToken (  
    [in] HANDLE hToken  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hToken`  
 de Identificador del token que se va a establecer para el subproceso que se está ejecutando actualmente.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`SetThreadToken` devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 `IHostSecurityManager::SetThreadToken` se comporta de forma similar a la función de Win32 correspondiente del mismo nombre, salvo que la función de Win32 permite que el llamador pase un identificador a un subproceso arbitrario, mientras que `IHostSecurityManager::SetThreadToken` puede asociar un token solo al subproceso que se está ejecutando actualmente.  
  
 El tipo de `HANDLE` no es compatible con COM; es decir, su tamaño es específico de un sistema operativo y requiere serialización personalizada. Por lo tanto, este token solo se usa en el proceso, entre el CLR y el host.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostSecurityManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsecuritymanager-interface.md)
- [IHostThreadPoolManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
