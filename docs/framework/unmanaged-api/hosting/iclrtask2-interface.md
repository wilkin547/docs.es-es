---
title: ICLRTask2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRTask2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2
helpviewer_keywords:
- ICLRTask2 interface [.NET Framework hosting]
ms.assetid: b5a22ebc-0582-49de-91f9-97a3d9789290
topic_type:
- apiref
ms.openlocfilehash: 47c6dd9045636bcfbe07c909fec3fda515d28ee8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124527"
---
# <a name="iclrtask2-interface"></a>ICLRTask2 (Interfaz)
Proporciona toda la funcionalidad de la interfaz [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) ; Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Retrasa nuevas solicitudes de anulación de subprocesos en el subproceso actual.|  
|[EndPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICLRTask2` hereda la interfaz de `ICLRTask` y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no se debe producir un error. La llamada a `BeginPreventAsyncAbort` incrementa el contador Delay-Thread-Abort para el subproceso actual y la llamada a `EndPreventAsyncAbort` lo reduce. Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar. Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.  
  
 Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no están emparejadas, es posible llegar a un estado en el que no se puedan entregar las anulaciones de subprocesos al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anule.  
  
 La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM). El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, la llamada a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado previamente. Del mismo modo, no se comprueba el desbordamiento del contador interno. Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.  
  
 Para obtener información sobre los miembros heredados de `ICLRTask` y sobre los otros usos de esta interfaz, vea la interfaz [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
