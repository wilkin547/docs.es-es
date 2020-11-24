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
ms.openlocfilehash: 2268fce5d3ca732d852edfdb6f0edf63117df363
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684218"
---
# <a name="idebuggerthreadcontrol-interface"></a>IDebuggerThreadControl (Interfaz)

Proporciona métodos para notificar al host el bloqueo y desbloqueo de subprocesos por parte de los servicios de depuración.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ThreadIsBlockingForDebugger](idebuggerthreadcontrol-threadisblockingfordebugger-method.md)|Notifica al host que el subproceso que está enviando esta devolución de llamada está a punto de bloquearse dentro de los servicios de depuración.|  
|[Método ReleaseAllRuntimeThreads](idebuggerthreadcontrol-releaseallruntimethreads-method.md)|Notifica al host que los servicios de depuración están a punto de liberar todos los subprocesos que están bloqueados.|  
|[Método StartBlockingForDebugger](idebuggerthreadcontrol-startblockingfordebugger-method.md)|Notifica al host que los servicios de depuración están a punto de iniciar el bloqueo de todos los subprocesos.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces de hospedaje](hosting-interfaces.md)
