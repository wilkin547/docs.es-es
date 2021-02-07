---
description: 'Más información acerca de: IHostMemoryManager:: RegisterMemoryNotificationCallback ((método)'
title: IHostMemoryManager::RegisterMemoryNotificationCallback (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.RegisterMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback
helpviewer_keywords:
- IHostMemoryManager::RegisterMemoryNotificationCallback method [.NET Framework hosting]
- RegisterMemoryNotificationCallback method [.NET Framework hosting]
ms.assetid: 65d301f6-4dbb-4b5f-8eff-82540e2b6465
topic_type:
- apiref
ms.openlocfilehash: 26a7468aba4f473eebff78a8c67eeb5b3e866e9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707772"
---
# <a name="ihostmemorymanagerregistermemorynotificationcallback-method"></a>IHostMemoryManager::RegisterMemoryNotificationCallback (Método)

Registra un puntero a una función de devolución de llamada que invoca el host para notificar a la Common Language Runtime (CLR) de la carga de memoria actual en el equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RegisterMemoryNotificationCallback (  
    [in] ICLRMemoryNotificationCallback* pCallback  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pCallback`  
 de Puntero de interfaz a una instancia de [ICLRMemoryNotificationCallback](iclrmemorynotificationcallback-interface.md) implementada por CLR.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`RegisterMemoryNotificationCallback` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Observaciones  

 Dado que la `ICLRMemoryNotificationCallback` interfaz define solo un método ([ICLRMemoryNotificationCallback:: OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)), y dado `pCallback` que es un puntero a una `ICLRMemoryNotificationCallback` instancia proporcionada por CLR, el registro es eficaz para la función de devolución de llamada. El host invoca `OnMemoryNotification` para informar de las condiciones de presión de memoria, en lugar de utilizar la función estándar de Win32 `CreateMemoryResourceNotification` . Para obtener más información, vea la documentación de la plataforma Windows.  
  
> [!NOTE]
> Las llamadas a no se `OnMemoryNotification` bloquean nunca. Siempre devuelven inmediatamente.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMemoryNotificationCallback (Interfaz)](iclrmemorynotificationcallback-interface.md)
- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
