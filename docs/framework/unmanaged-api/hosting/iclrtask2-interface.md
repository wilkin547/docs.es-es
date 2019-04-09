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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 518248651de6d8afdf25692c5f48da52b11eb0f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59172476"
---
# <a name="iclrtask2-interface"></a>ICLRTask2 (Interfaz)
Proporciona toda la funcionalidad de la [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz; además, proporciona métodos que permiten las anulaciones de subprocesos para que se retrasa en el subproceso actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)|Subproceso nuevo retrasos anular las solicitudes en el subproceso actual.|  
|[Método EndPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)|Permite nuevas o pendiente de solicitudes de anulación de subproceso como resultado en el subproceso se anula en el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  
 El `ICLRTask2` interfaz hereda el `ICLRTask` interfaz y agrega los métodos que permiten al host retrasar las anulaciones de subproceso, para proteger una región de código que no debe sufrir un error. Una llamada a `BeginPreventAsyncAbort` incrementa el contador de anulaciones de subprocesos con retraso para el subproceso actual y llamar al método `EndPreventAsyncAbort` disminuye lo. Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar. Siempre que el contador es mayor que cero, se retrasan las anulaciones de subproceso del subproceso actual.  
  
 Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` están emparejados no, es posible obtener acceso a un estado en que el subproceso no se puede entregar anulaciones al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anula a sí mismo.  
  
 La funcionalidad que se expone mediante esta característica se usa internamente por la máquina virtual (VM). Uso inadecuado de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, al llamar a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual ha incrementado previamente. De forma similar, no se comprueba el contador interno de desbordamiento. Si supera el límite de entero dado que se incrementa en el host y la máquina virtual, el comportamiento resultante no está especificado.  
  
 Para obtener información acerca de los miembros que hereda de `ICLRTask` y sobre otros usos de esta interfaz, vea el [ICLRTask](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
