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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b71c177c7c0cb029fb7cfa734f54c87abf20b348
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557843"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager (Interfaz)
Implementa un método de devolución de llamada que permite al host informar a common language runtime (CLR) del estado de E/S especificado solicitudes.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[OnComplete (método)](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Notifica a CLR del estado de una solicitud de E/S que se hace mediante una llamada a la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-bind-method.md) método.|  
  
## <a name="remarks"></a>Comentarios  
 El host implementa la abstracción de finalización de E/S mediante el uso de la [IHostIoCompletionManager](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md) interfaz. El CLR realiza las solicitudes de E/S a través de esta interfaz, y el host informa el tiempo de ejecución del resultado de dichas solicitudes mediante el uso de la `ICLRIoCompletionManager` interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MSCorEE.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IHostIoCompletionManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager (interfaz)](../../../../docs/framework/unmanaged-api/hosting/ihostthreadpoolmanager-interface.md)
- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
