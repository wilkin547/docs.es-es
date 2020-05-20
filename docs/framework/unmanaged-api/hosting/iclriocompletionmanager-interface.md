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
ms.openlocfilehash: 822b51531b7afc1c824c74b9580d9208e347e13b
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703551"
---
# <a name="iclriocompletionmanager-interface"></a>ICLRIoCompletionManager (Interfaz)
Implementa un método de devolución de llamada que permite al host notificar el Common Language Runtime (CLR) del estado de las solicitudes de e/s especificadas.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método OnComplete](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-oncomplete-method.md)|Notifica a CLR el estado de una solicitud de e/s realizada mediante una llamada al método [IHostIoCompletionManager:: Bind](ihostiocompletionmanager-bind-method.md) .|  
  
## <a name="remarks"></a>Observaciones  
 El host implementa la abstracción de finalización de e/s mediante la interfaz [IHostIoCompletionManager](ihostiocompletionmanager-interface.md) . CLR realiza solicitudes de e/s a través de esta interfaz y el host notifica al tiempo de ejecución el resultado de dichas solicitudes mediante la `ICLRIoCompletionManager` interfaz.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [IHostIoCompletionManager (Interfaz)](ihostiocompletionmanager-interface.md)
- [IHostThreadPoolManager (Interfaz)](ihostthreadpoolmanager-interface.md)
- [Interfaces de hospedaje](hosting-interfaces.md)
