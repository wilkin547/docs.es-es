---
description: 'Más información acerca de: interfaz ICLRTask2'
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
ms.openlocfilehash: 835b01e1c808c071e9393c5117d5e38415ec8eba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728656"
---
# <a name="iclrtask2-interface"></a>ICLRTask2 (Interfaz)

Proporciona toda la funcionalidad de la interfaz [ICLRTask](iclrtask-interface.md) ; Además, proporciona métodos que permiten que las anulaciones de subprocesos se retrasen en el subproceso actual.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginPreventAsyncAbort](iclrtask2-beginpreventasyncabort-method.md)|Retrasa nuevas solicitudes de anulación de subprocesos en el subproceso actual.|  
|[Método EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md)|Permite que las solicitudes de anulación de subprocesos nuevas o pendientes produzcan anulaciones de subprocesos en el subproceso actual.|  
  
## <a name="remarks"></a>Observaciones  

 La `ICLRTask2` interfaz hereda la `ICLRTask` interfaz y agrega métodos que permiten al host retrasar las anulaciones de subprocesos, para proteger una región de código que no se debe producir un error. La llamada a `BeginPreventAsyncAbort` incrementa el contador Delay-Thread-Abort para el subproceso actual y la llamada a `EndPreventAsyncAbort` lo reduce. Las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` se pueden anidar. Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual.  
  
 Si las llamadas a `BeginPreventAsyncAbort` y `EndPreventAsyncAbort` no están emparejadas, es posible llegar a un estado en el que las anulaciones de subprocesos no se puedan entregar al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anule.  
  
 La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM). El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente. Del mismo modo, no se comprueba el desbordamiento del contador interno. Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.  
  
 Para obtener información sobre los miembros heredados de `ICLRTask` y sobre los otros usos de esta interfaz, vea la interfaz [ICLRTask](iclrtask-interface.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRTask (Interfaz)](iclrtask-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
