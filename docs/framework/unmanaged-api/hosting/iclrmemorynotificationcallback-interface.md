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
ms.openlocfilehash: 5762a354bec485cb382b5460dfd2a337f79bee1a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95689542"
---
# <a name="iclrmemorynotificationcallback-interface"></a>ICLRMemoryNotificationCallback (Interfaz)

Permite al host notificar las condiciones de presión de memoria mediante un enfoque similar al de la función de Win32 `CreateMemoryResourceNotification` .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método OnMemoryNotification](iclrmemorynotificationcallback-onmemorynotification-method.md)|Notifica al Common Language Runtime (CLR) la carga de memoria en el equipo.|  
  
## <a name="remarks"></a>Comentarios  

 El host usa la `ICLRMemoryNotificationCallback` interfaz para solicitar que los recursos de memoria de CLR liberen.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IHostMemoryManager (Interfaz)](ihostmemorymanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
