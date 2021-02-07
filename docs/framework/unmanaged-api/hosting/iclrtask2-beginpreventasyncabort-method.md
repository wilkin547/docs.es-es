---
description: 'Más información sobre: ICLRTask2:: BeginPreventAsyncAbort ((método)'
title: ICLRTask2::BeginPreventAsyncAbort (Método)
ms.date: 03/30/2017
api_name:
- ICLRTask2.BeginPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::BeginPreventAsyncAbort
helpviewer_keywords:
- ICLRTask2::BeginPreventAsyncAbort method [.NET Framework hosting]
- BeginPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: 75754c2f-38c7-4707-85fe-559db4542729
topic_type:
- apiref
ms.openlocfilehash: 1e25cb0e6157d77efc6a04016dc49d9d5d0bf116
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99728655"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>ICLRTask2::BeginPreventAsyncAbort (Método)

Retrasa las nuevas solicitudes de anulación de subprocesos para que resulten anulaciones de subprocesos en el subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HOST_E_INVALIDOPERATION|Se llamó al método en un subproceso que no es el subproceso actual.|  
  
## <a name="remarks"></a>Observaciones  

 Al llamar a este método, se incrementa el contador Delay-Thread-Abort del subproceso actual en uno.  
  
 Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort (](iclrtask2-endpreventasyncabort-method.md) se pueden anidar. Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual. Si esta llamada no se empareja con una llamada al `EndPreventAsyncAbort` método, es posible llegar a un estado en el que no se puedan entregar las anulaciones de subprocesos al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anule.  
  
 La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM). El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, llamar a `EndPreventAsyncAbort` sin la primera llamada `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado anteriormente. Del mismo modo, no se comprueba el desbordamiento del contador interno. Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método EndPreventAsyncAbort](iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2 (Interfaz)](iclrtask2-interface.md)
- [ICLRTaskManager (Interfaz)](iclrtaskmanager-interface.md)
- [IHostTask (Interfaz)](ihosttask-interface.md)
- [IHostTaskManager (Interfaz)](ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
