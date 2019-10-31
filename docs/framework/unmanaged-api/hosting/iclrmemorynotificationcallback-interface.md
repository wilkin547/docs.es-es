---
title: ICLRMemoryNotificationCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRMemoryNotificationCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMemoryNotificationCallback
helpviewer_keywords:
- ICLRMemoryNotificationCallback interface [.NET Framework hosting]
ms.assetid: 873639e2-4837-4568-83b3-4493e67e4174
topic_type:
- apiref
ms.openlocfilehash: e980356ad592e137df7d08dadd77431b0e295380
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141004"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback (Interfaz)
Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función `CreateMemoryResourceNotification` de Win32.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OnMemoryNotification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.|  
  
## <a name="remarks"></a>Comentarios  
 El host usa la interfaz `ICLRMemoryNotificationCallback` para solicitar que los recursos de memoria de CLR liberen.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
