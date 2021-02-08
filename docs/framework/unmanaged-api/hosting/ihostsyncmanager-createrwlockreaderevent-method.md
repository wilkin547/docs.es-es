---
description: 'Más información acerca de: IHostSyncManager:: CreateRWLockReaderEvent ((método)'
title: IHostSyncManager::CreateRWLockReaderEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateRWLockReaderEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateRWLockReaderEvent
helpviewer_keywords:
- CreateRWLockReaderEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockReaderEvent method [.NET Framework hosting]
ms.assetid: 68c4ea19-c47c-45c6-b420-d3a2ba1c2d50
topic_type:
- apiref
ms.openlocfilehash: be20757924aa45d2a44edab9bf921026aa0247a5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784774"
---
# <a name="ihostsyncmanagercreaterwlockreaderevent-method"></a>IHostSyncManager::CreateRWLockReaderEvent (Método)

Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateRWLockReaderEvent (  
    [in]  BOOL bInitialState,  
    [in]  SIZE_T cookie,  
    [out] IHostManualEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `bInitialState`  
 [in] `true` , si `ppEvent` se debe señalizar; en caso contrario, `false` .  
  
 `cookie`  
 de Cookie que se va a asociar al bloqueo del lector.  
  
 `ppEvent`  
 enuncia Un puntero a la dirección de una instancia de [IHostManualEvent](ihostmanualevent-interface.md) , o null si no se pudo crear el objeto de evento.  
  
## <a name="return-value"></a>Valor devuelto  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|`CreateRWLockReaderEvent` se devolvió correctamente.|  
|HOST_E_CLRNOTAVAILABLE|El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.|  
|HOST_E_TIMEOUT|Se agotó el tiempo de espera de la llamada.|  
|HOST_E_NOT_OWNER|El autor de la llamada no posee el bloqueo.|  
|HOST_E_ABANDONED|Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.|  
|E_FAIL|Se produjo un error grave desconocido. Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso. Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.|  
|E_OUTOFMEMORY|No había suficiente memoria disponible para crear el objeto de evento solicitado.|  
  
## <a name="remarks"></a>Observaciones  

 CLR llama `CreateRWLockReaderEvent` a para obtener una referencia a una `IHostManualEvent` instancia de que se va a utilizar en su implementación de un bloqueo de lector. El host puede usar la cookie para determinar qué tareas están esperando en el bloqueo del lector consultando la interfaz [ICLRSyncManager](iclrsyncmanager-interface.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostManualEvent (Interfaz)](ihostmanualevent-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
