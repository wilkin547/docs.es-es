---
title: IDebuggerThreadControl (Interfaz)
ms.date: 03/30/2017
api_name:
- IDebuggerThreadControl
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IDebuggerThreadControl
helpviewer_keywords:
- IDebuggerThreadControl interface [.NET Framework hosting]
ms.assetid: 0a270c42-a7d1-45f1-a64d-fa3e84d14532
topic_type:
- apiref
ms.openlocfilehash: a65f9f0f29a43cf3d26b4b2bc5f6f594f0557009
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73133160"
---
# <a name="idebuggerthreadcontrol-interface"></a>IDebuggerThreadControl (Interfaz)
Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ThreadIsBlockingForDebugger (método)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.|  
|[ReleaseAllRuntimeThreads (método)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.|  
|[StartBlockingForDebugger (método)](../../../../docs/framework/unmanaged-api/hosting/idebuggerthreadcontrol-startblockingfordebugger-method.md)|Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces de hospedaje](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
