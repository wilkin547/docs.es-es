---
title: ICLRIoCompletionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRIoCompletionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRIoCompletionManager
helpviewer_keywords:
- ICLRIoCompletionManager interface [.NET Framework hosting]
ms.assetid: c6c3ace6-e5e7-4450-8cc5-a9a48208c493
topic_type:
- apiref
ms.openlocfilehash: b63d4269a8d48ee49016a4c51d63bf81bdba8da2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141022"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager (Interfaz)
Implementa un método de devolución de llamada que permite al host notificar el Common Language Runtime (CLR) del estado de las solicitudes de e/s especificadas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OnComplete (método)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Notifica a CLR el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Comentarios  
 El host implementa la abstracción de finalización de e/s mediante la interfaz [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) . El CLR realiza solicitudes de e/s a través de esta interfaz y el host notifica al tiempo de ejecución el resultado de dichas solicitudes mediante el uso de la interfaz de `ICLRIoCompletionManager`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
