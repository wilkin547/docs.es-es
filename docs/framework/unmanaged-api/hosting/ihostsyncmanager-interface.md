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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc58e5b7902195860505399b8222afc068fbfc23
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54713267"
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para crear a las primitivas de sincronización llamando al host en lugar de usar las funciones de sincronización de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateAutoEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Crea un objeto de evento de restablecimiento automático.|  
|[CreateCrst (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Crea un objeto de sección crítica para la sincronización.|  
|[CreateCrstWithSpinCount (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Crea un objeto de sección crítica con recuento de rotación para la sincronización.|  
|[CreateManualEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Crea un objeto de evento de restablecimiento manual.|  
|[CreateMonitorEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Crea un objeto de evento de restablecimiento automático supervisado.|  
|[CreateRWLockReaderEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.|  
|[CreateRWLockWriterEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.|  
|[CreateSemaphore (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto CLR que se usará como un semáforo para los eventos de espera.|  
|[SetCLRSyncManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Establece el [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instancia asociada con el actual `IHostSyncManager` instancia.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR detecta la implementación del host de `IHostSyncManager` mediante una llamada a la [IHostControl](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) método con un `IID` de IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
