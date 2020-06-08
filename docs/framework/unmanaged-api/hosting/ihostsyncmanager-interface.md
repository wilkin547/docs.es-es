---
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
ms.openlocfilehash: fd3c941d89fbd93f30fc1af235f6310b23758973
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501461"
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
  
## <a name="remarks"></a>Comentarios  
 CLR detecta la implementación del host de llamando al `IHostSyncManager` método [IHostControl:: GetHostManager (](ihostcontrol-gethostmanager-method.md) con una `IID` de IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
