---
title: Interfaz ICorDebugController
ms.date: 03/30/2017
api_name:
- ICorDebugController
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController
helpviewer_keywords:
- ICorDebugController interface [.NET Framework debugging]
ms.assetid: dbb1c4dc-269a-459b-ab1d-6c70788782ce
topic_type:
- apiref
ms.openlocfilehash: 1ca9e55a2183ca4293d30607496b588cbf21d6dd
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679954"
---
# <a name="icordebugcontroller-interface"></a>Interfaz ICorDebugController

Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Este método está obsoleto.|  
|`ICorDebugController::CommitChanges`|Este método está obsoleto.|  
|[Método Continue](icordebugcontroller-continue-method.md)|Reanuda la ejecución de subprocesos administrados después de una llamada a [ICorDebugController:: Stop](icordebugcontroller-stop-method.md).|  
|[Método Detach](icordebugcontroller-detach-method.md)|Desasocia el depurador del dominio del proceso o de la aplicación.|  
|[Método EnumerateThreads](icordebugcontroller-enumeratethreads-method.md)|Obtiene un enumerador para los subprocesos administrados activos en el proceso.|  
|[Método HasQueuedCallbacks](icordebugcontroller-hasqueuedcallbacks-method.md)|Obtiene un valor que indica si las devoluciones de llamada administradas están actualmente en la cola del subproceso especificado.|  
|[Método IsRunning](icordebugcontroller-isrunning-method.md)|Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.|  
|[Método SetAllThreadsDebugState](icordebugcontroller-setallthreadsdebugstate-method.md)|Establece el estado de depuración de todos los subprocesos administrados en el proceso.|  
|[Método Stop](icordebugcontroller-stop-method.md)|Realiza una detención cooperativa en todos los subprocesos que ejecutan código administrado en el proceso.|  
|[Terminate (Método)](icordebugcontroller-terminate-method.md)|Finaliza el proceso con el código de salida especificado.|  
  
## <a name="remarks"></a>Comentarios  

 Si `ICorDebugController` controla un proceso, el ámbito incluye todos los subprocesos del proceso. Si `ICorDebugController` está controlando un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación concreto.  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaces para depuración](debugging-interfaces.md)
