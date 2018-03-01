---
title: ICLRTask2 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 8701cff3400e46660fac90486cf5648d29aa9972
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrtask2-interface"></a>ICLRTask2 (Interfaz)
Proporciona toda la funcionalidad de la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz; además, proporciona métodos que permiten anulaciones de subprocesos para se retrasa en el subproceso actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Nuevo subproceso de retrasos anular las solicitudes en el subproceso actual.|  
|[EndPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso que se anula en el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICLRTask2` interfaz hereda el `ICLRTask` de interfaz y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no debe producir un error. Al llamar a `BeginPreventAsyncAbort` incrementa el contador de anulaciones de subprocesos con retraso para el subproceso actual y llamar al método `EndPreventAsyncAbort` disminuye lo. Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar. Siempre que el contador sea mayor que cero, se retrasan las anulaciones de subprocesos para el subproceso actual.  
  
 Si llama a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no son emparejados, es posible llegar a un estado en el subproceso no se puede entregar anulaciones para el subproceso actual.  
  
 No se respeta el retraso para un subproceso que se anula a sí mismo.  
  
 La funcionalidad que se expone mediante esta característica se utiliza internamente por la máquina virtual (VM). Uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, al llamar a `EndPreventAsyncAbort` sin antes de llamar a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual lo ha incrementado previamente. De forma similar, no se comprueba el contador interno de desbordamiento. Si supera el límite de entero dado que se incrementa por el host y la máquina virtual, el comportamiento resultante no está especificado.  
  
 Para obtener información acerca de los miembros se hereda de `ICLRTask` y sobre los otros usos de esta interfaz, vea la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)  
 [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
