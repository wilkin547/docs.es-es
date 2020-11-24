---
title: ICLRSyncManager::CreateRWLockOwnerIterator (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.CreateRWLockOwnerIterator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator
helpviewer_keywords:
- ICLRSyncManager::CreateRWLockOwnerIterator method [.NET Framework hosting]
- CreateRWLockOwnerIterator method [.NET Framework hosting]
ms.assetid: b5535b87-9439-424e-b9b3-7d6fafb9819e
topic_type:
- apiref
ms.openlocfilehash: 2b6a2082d27fca4c78dcb15a13cfd87e8066e388
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95687221"
---
# <a name="iclrsyncmanagercreaterwlockowneriterator-method"></a>ICLRSyncManager::CreateRWLockOwnerIterator (Método)

Solicita que el Common Language Runtime (CLR) cree un iterador para que lo use el host con el fin de determinar el conjunto de tareas que esperan en un bloqueo de lectura y escritura.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateRWLockOwnerIterator (  
    [in]  SIZE_T    cookie,  
    [out] SIZE_T   *pIterator  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `cookie`  
 de Cookie asociada con el bloqueo de lector-escritor deseado.  
  
 `pIterator`  
 enuncia Un puntero a un iterador que se puede pasar a los métodos [GetRWLockOwnerNext (](iclrsyncmanager-getrwlockownernext-method.md) y [DeleteRWLockOwnerIterator (](iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateRWLockOwnerIterator` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|HOST_E_INVALIDOPERATION|`CreateRWLockOwnerIterator` se llamó a en un subproceso que está ejecutando código administrado actualmente.|  
  
## <a name="remarks"></a>Comentarios  

 Normalmente, los hosts llaman a los `CreateRWLockOwnerIterator` `DeleteRWLockOwnerIterator` métodos, y `GetRWLockOwnerNext` durante la detección de interbloqueos. El host es responsable de garantizar que el bloqueo de lector-Writer sigue siendo válido, porque CLR no realiza ningún intento de mantener activo el bloqueo del sistema de lectura. Hay varias estrategias disponibles para que el host garantice la validez del bloqueo:  
  
- El host puede bloquear las llamadas de liberación en el bloqueo de lectura y escritura (por ejemplo, [IHostSemaphore:: ReleaseSemaphore (](ihostsemaphore-releasesemaphore-method.md)) al tiempo que se garantiza que este bloque no cause interbloqueos.  
  
- El host puede impedir que la salida espere en el objeto de evento asociado al bloqueo lector-escritor, asegurándose de nuevo de que este bloque no cause ningún interbloqueo.  
  
> [!NOTE]
> `CreateRWLockOwnerIterator` solo se debe llamar a en subprocesos que ejecutan actualmente código no administrado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
