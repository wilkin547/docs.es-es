---
title: IHostManualEvent (Interfaz)
ms.date: 03/30/2017
api_name:
- IHostManualEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostManualEvent
helpviewer_keywords:
- IHostManualEvent interface [.NET Framework hosting]
ms.assetid: 300c2661-b7d1-4c39-b080-9ebdef0fd523
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eb09422872a0d9565be286c25ca1b28d1c45e08f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54501703"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent (Interfaz)
Proporciona la implementación del host de una representación de un evento de restablecimiento manual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Reset (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-reset-method.md)|Restablece el actual `IHostManualEvent` instancia a un estado no señalado.|  
|[Set (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-set-method.md)|Establece el actual `IHostManualEvent` instancia en un estado señalado.|  
|[Wait (método)](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-wait-method.md)|Hace que el actual `IHostManualEvent` instancia espere hasta que sea propiedad o un período de tiempo especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICLRSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)
- [IHostAutoEvent (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)
- [IHostSemaphore (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsemaphore-interface.md)
- [IHostSyncManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
