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
ms.openlocfilehash: 8345d85502087568cb05dd262cccf181e3ca07ac
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803700"
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
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRSyncManager (Interfaz)](iclrsyncmanager-interface.md)
- [IHostAutoEvent (Interfaz)](ihostautoevent-interface.md)
- [IHostManualEvent (Interfaz)](ihostmanualevent-interface.md)
- [IHostSyncManager (Interfaz)](ihostsyncmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
