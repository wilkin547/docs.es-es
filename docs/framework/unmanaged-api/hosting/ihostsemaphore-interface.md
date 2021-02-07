---
description: 'Más información sobre: interfaz IHostSemaphore'
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
ms.openlocfilehash: 682f1f70925310e93f88f1dc314052e801a5e87b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671365"
---
# <a name="ihostsemaphore-interface"></a>IHostSemaphore (Interfaz)

Representa la implementación del host de un semáforo para el subprocesamiento.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ReleaseSemaphore](ihostsemaphore-releasesemaphore-method.md)|Aumenta el recuento de la `IHostSemaphore` instancia actual en la cantidad especificada.|  
|[Wait (Método)](ihostsemaphore-wait-method.md)|Hace que la `IHostSemaphore` instancia actual espere hasta que sea propiedad o transcurra la cantidad de tiempo especificada.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostManualEvent (Interfaz)](ihostmanualevent-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
