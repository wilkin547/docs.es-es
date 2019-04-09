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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7628aa0ad10398f92d475c4c776810e13fac22b7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59107554"
---
# <a name="icordebugcontroller-interface"></a>Interfaz ICorDebugController

Representa un ámbito, <xref:System.Diagnostics.Process> o <xref:System.AppDomain>, en el que se puede controlar el contexto de ejecución de código.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|`ICorDebugController::CanCommitChanges`|Este método está obsoleto.|  
|`ICorDebugController::CommitChanges`|Este método está obsoleto.|  
|[Método Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md)|Reanuda la ejecución de subprocesos administrados después de llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md).|  
|[Método Detach](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-detach-method.md)|Desasocia al depurador desde el dominio de aplicación o proceso.|  
|[Método EnumerateThreads](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md)|Obtiene un enumerador para los subprocesos administrados activos en el proceso.|  
|[Método HasQueuedCallbacks](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-hasqueuedcallbacks-method.md)|Obtiene un valor que indica si las devoluciones de llamada administradas actualmente están en cola para el subproceso especificado.|  
|[Método IsRunning](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-isrunning-method.md)|Obtiene un valor que indica si los subprocesos del proceso se están ejecutando libremente.|  
|[Método SetAllThreadsDebugState](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-setallthreadsdebugstate-method.md)|Establece el estado de depuración de todos los subprocesos administrados en el proceso.|  
|[Método Stop](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-stop-method.md)|Realiza una detención cooperativa de todos los subprocesos que ejecutan código administrado en el proceso.|  
|[Método Terminate](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-terminate-method.md)|Finaliza el proceso con el código de salida especificado.|  
  
## <a name="remarks"></a>Comentarios  
 Si `ICorDebugController` es controlar un proceso, el ámbito incluye todos los subprocesos del proceso. Si `ICorDebugController` es controlar un dominio de aplicación, el ámbito incluye solo los subprocesos de ese dominio de aplicación determinado.  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
