---
description: 'Más información acerca de: IHostSyncManager (interfaz)'
title: IHostSyncManager (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostSyncManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager
helpviewer_keywords:
- IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type:
- apiref
ms.openlocfilehash: c3bd2928315567605d320c772de8ff824ad3cd09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784735"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager (Interfaz)

Proporciona métodos que permiten al Common Language Runtime (CLR) crear primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método CreateAutoEvent](ihostsyncmanager-createautoevent-method.md)|Crea un objeto de evento de restablecimiento automático.|  
|[Método CreateCrst](ihostsyncmanager-createcrst-method.md)|Crea un objeto de sección crítica para la sincronización.|  
|[Método CreateCrstWithSpinCount](ihostsyncmanager-createcrstwithspincount-method.md)|Crea un objeto de sección crítica con el recuento de giros para la sincronización.|  
|[Método CreateManualEvent](ihostsyncmanager-createmanualevent-method.md)|Crea un objeto de evento de restablecimiento manual.|  
|[Método CreateMonitorEvent](ihostsyncmanager-createmonitorevent-method.md)|Crea un objeto de evento de restablecimiento automático supervisado.|  
|[Método CreateRWLockReaderEvent](ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.|  
|[Método CreateRWLockWriterEvent](ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.|  
|[Método CreateSemaphore](ihostsyncmanager-createsemaphore-method.md)|Crea un objeto [IHostSemaphore](ihostsemaphore-interface.md) para que el CLR lo use como semáforo para los eventos de espera.|  
|[Método SetCLRSyncManager](ihostsyncmanager-setclrsyncmanager-method.md)|Establece la instancia de [ICLRSyncManager](iclrsyncmanager-interface.md) que se va a asociar a la `IHostSyncManager` instancia actual.|  
  
## <a name="remarks"></a>Observaciones  

 CLR detecta la implementación del host de llamando al `IHostSyncManager` método [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) con una `IID` de IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
