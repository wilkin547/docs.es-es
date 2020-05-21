---
title: ICLRSyncManager::GetRWLockOwnerNext (Método)
ms.date: 03/30/2017
api_name:
- ICLRSyncManager.GetRWLockOwnerNext
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRSyncManager::GetRWLockOwnerNext
helpviewer_keywords:
- ICLRSyncManager::GetRWLockOwnerNext method [.NET Framework hosting]
- GetRWLockOwnerNext method [.NET Framework hosting]
ms.assetid: 0e025b6a-280e-40a2-a2d0-b15f58777b81
topic_type:
- apiref
ms.openlocfilehash: e5a8f69e66bb4b6373aea2c753bff9351bff8128
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762492"
---
# <a name="iclrsyncmanagergetrwlockownernext-method"></a>ICLRSyncManager::GetRWLockOwnerNext (Método)
Obtiene la siguiente instancia de [IHostTask](ihosttask-interface.md) que está bloqueada en el bloqueo de lector-Writer actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
HRESULT GetRWLockOwnerNext (  
    [in] SIZE_T       Iterator,  
    [out] IHostTask  *ppOwnerHostTask  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `Iterator`  
 de Iterador que se creó mediante una llamada a [CreateRWLockOwnerIterator](iclrsyncmanager-createrwlockowneriterator-method.md).  
  
 `ppOwnerHostTask`  
 enuncia Puntero al siguiente `IHostTask` que está esperando en el bloqueo, o null si no hay ninguna tarea en espera.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`GetRWLockOwnerNext`se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
  
## <a name="remarks"></a>Comentarios  
 Si `ppOwnerHostTask` se establece en null, la iteración ha finalizado y el host debe llamar al método [DeleteRWLockOwnerIterator (](iclrsyncmanager-deleterwlockowneriterator-method.md) .  
  
> [!NOTE]
> CLR llama a `AddRef` en el `IHostTask` que `ppOwnerHostTask` señala para evitar que esta tarea se salga mientras el host contiene el puntero. El host debe llamar `Release` a para reducir el recuento de referencias cuando termine.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
