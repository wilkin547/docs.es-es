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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2c5cf7e17989f3c083c7c4e52fa8cfc09c00bc7d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431524"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback (Interfaz)
Permite al host situaciones de presión de memoria de informe mediante un enfoque similar de Win32 `CreateMemoryResourceNotification` función.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OnMemoryNotification (método)](../../../../docs/framework/unmanaged-api/hosting/iclrmemorynotificationcallback-onmemorynotification-method.md)|Notifica a common language runtime (CLR) de la carga de memoria en el equipo.|  
  
## <a name="remarks"></a>Comentarios  
 El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar a CLR que libere recursos de memoria.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IHostMemoryManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
