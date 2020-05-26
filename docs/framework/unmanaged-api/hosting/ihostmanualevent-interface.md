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
ms.openlocfilehash: 7c46f00063cdf9281a5f1080594e8d6dbc6c101e
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804589"
---
# <a name="ihostmanualevent-interface"></a>IHostManualEvent (Interfaz)
Proporciona la implementación del host de una representación de un evento de restablecimiento manual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Reset (Método)](ihostmanualevent-reset-method.md)|Restablece la instancia actual `IHostManualEvent` a un estado no señalado.|  
|[Método Set](ihostmanualevent-set-method.md)|Establece la `IHostManualEvent` instancia actual en un estado señalado.|  
|[Wait (Método)](ihostmanualevent-wait-method.md)|Hace que la `IHostManualEvent` instancia actual espere hasta que sea propiedad o transcurra un período de tiempo especificado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostSemaphore (Interfaz)](ihostsemaphore-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
