---
title: IHostSyncManager (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager
helpviewer_keywords: IHostSyncManager interface [.NET Framework hosting]
ms.assetid: 2e081a37-6a28-4c93-b7ab-1c96a464637c
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b51e1dd9219c30eb4918bf1e331c96585f7c03ac
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="ihostsyncmanager-interface"></a>IHostSyncManager (Interfaz)
Proporciona métodos que permiten a common language runtime (CLR) para crear a las primitivas de sincronización llamando al host en lugar de utilizar las funciones de sincronización de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[CreateAutoEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createautoevent-method.md)|Crea un objeto de evento de restablecimiento automático.|  
|[CreateCrst (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrst-method.md)|Crea un objeto de sección crítica para la sincronización.|  
|[CreateCrstWithSpinCount (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createcrstwithspincount-method.md)|Crea un objeto de sección crítica con recuento circular para la sincronización.|  
|[CreateManualEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmanualevent-method.md)|Crea un objeto de evento de restablecimiento manual.|  
|[CreateMonitorEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createmonitorevent-method.md)|Crea un objeto de evento de restablecimiento automático supervisado.|  
|[CreateRWLockReaderEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockreaderevent-method.md)|Crea un objeto de evento de restablecimiento manual para la implementación de un bloqueo de lector.|  
|[CreateRWLockWriterEvent (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createrwlockwriterevent-method.md)|Crea un objeto de evento de restablecimiento automático para la implementación de un bloqueo de escritor.|  
|[CreateSemaphore (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-createsemaphore-method.md)|Crea un [IHostSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md) objeto para el CLR que se usará como un semáforo para los eventos de espera.|  
|[SetCLRSyncManager (método)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-setclrsyncmanager-method.md)|Establece el [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) instancia asociada con el actual `IHostSyncManager` instancia.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR detecta la implementación del host de `IHostSyncManager` mediante una llamada a la [IHostControl:: GetHostManager](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-gethostmanager-method.md) método con un `IID` de IID_IHostSyncManager.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
