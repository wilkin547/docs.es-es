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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 85a43fef7f6dfa6dbe0bb9f1c4caec2c9c224b93
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61763436"
---
# <a name="iclrtask2beginpreventasyncabort-method"></a>ICLRTask2::BeginPreventAsyncAbort (Método)
Subproceso nuevo retrasos solicitudes de anulación de lo que las anulaciones de subproceso en el subproceso actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT BeginPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|HOST_E_INVALIDOPERATION|Se llamó al método en un subproceso que no es el subproceso actual.|  
  
## <a name="remarks"></a>Comentarios  
 Llamar a este método, el contador de anulaciones de subprocesos con retraso para el subproceso actual incrementa en uno.  
  
 Las llamadas a `BeginPreventAsyncAbort` y [Iclrtask2](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md) se pueden anidar. Siempre que el contador es mayor que cero, se retrasan las anulaciones de subproceso del subproceso actual. Si esta llamada no se empareja con una llamada a la `EndPreventAsyncAbort` método, es posible obtener acceso a un estado en que el subproceso no se puede entregar anulaciones al subproceso actual.  
  
 No se respeta el retraso de un subproceso que se anula a sí mismo.  
  
 La funcionalidad que se expone mediante esta característica se usa internamente por la máquina virtual (VM). Uso inadecuado de estos métodos puede provocar un comportamiento no especificado en la máquina virtual. Por ejemplo, al llamar a `EndPreventAsyncAbort` sin llamar primero a `BeginPreventAsyncAbort` podría establecer el contador a cero cuando la máquina virtual ha incrementado previamente. De forma similar, no se comprueba el contador interno de desbordamiento. Si supera el límite de entero dado que se incrementa en el host y la máquina virtual, el comportamiento resultante no está especificado.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [EndPreventAsyncAbort (método)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-endpreventasyncabort-method.md)
- [ICLRTask2 (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)
- [ICLRTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)
- [IHostTask (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)
- [IHostTaskManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
