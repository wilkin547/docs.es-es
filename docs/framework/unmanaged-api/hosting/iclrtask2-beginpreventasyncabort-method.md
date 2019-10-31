---
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
ms.openlocfilehash: 67841bbcd796e41b3b81f922020fe6c3677730c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124563"
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
  
## <a name="remarks"></a>Comentarios  
 Al llamar a este método, se incrementa el contador Delay-Thread-Abort del subproceso actual en uno.  
  
 Las llamadas a `BeginPreventAsyncAbort` y [ICLRTask2:: EndPreventAsyncAbort (](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) se pueden anidar. Siempre que el contador sea mayor que cero, se retrasarán las anulaciones de subproceso para el subproceso actual. Si esta llamada no se empareja con una llamada al método `EndPreventAsyncAbort`, es posible llegar a un estado en el que las anulaciones de subprocesos no se puedan entregar al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anule.  
  
 La funcionalidad que expone esta característica se usa internamente en la máquina virtual (VM). El uso incorrecto de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, la llamada a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador en cero cuando la máquina virtual lo ha incrementado previamente. Del mismo modo, no se comprueba el desbordamiento del contador interno. Si supera su límite entero porque lo incrementa el host y la máquina virtual, el comportamiento resultante no se especifica.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EndPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
