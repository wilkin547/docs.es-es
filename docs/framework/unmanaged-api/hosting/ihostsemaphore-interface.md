---
title: IHostSemaphore (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostSemaphore
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSemaphore
helpviewer_keywords:
- IHostSemaphore interface [.NET Framework hosting]
ms.assetid: c0765321-656c-441e-bab5-58176292be1e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2d7d4a295832a958fb6a8fe2e6c43a09135500d3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59182291"
---
# <a name="ihostsemaphore-interface"></a>IHostSemaphore (Interfaz)
Representa la implementación del host de un semáforo para el subprocesamiento.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ReleaseSemaphore](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-releasesemaphore-method.md)|Aumenta el recuento de actual `IHostSemaphore` instancia en la cantidad especificada.|  
|[Método Wait](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-wait-method.md)|Hace que el actual `IHostSemaphore` instancia espere hasta que es propietario o la cantidad de tiempo especificada.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostManualEvent (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)
- [IHostSyncManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
