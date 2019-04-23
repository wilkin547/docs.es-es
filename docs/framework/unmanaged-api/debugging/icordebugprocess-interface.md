---
title: Interfaz ICorDebugProcess
ms.date: 03/30/2017
api_name:
- ICorDebugProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess
helpviewer_keywords:
- ICorDebugProcess interface [.NET Framework debugging]
ms.assetid: be86f4b5-418a-4c5c-a67c-97148c65ed8c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46d96d66f16cd956d8fab1afe00486d564e37953
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59216800"
---
# <a name="icordebugprocess-interface"></a>Interfaz ICorDebugProcess
Representa un proceso que ejecuta código administrado. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearCurrentException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Borra la excepción no administrada actual del subproceso especificado.|  
|[EnableLogMessages (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Habilita y deshabilita el envío de mensajes de registro al depurador.|  
|[EnumerateAppDomains (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Enumera todos los dominios de aplicación en el proceso.|  
|[EnumerateObjects (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Sin implementar.|  
|[GetHandle (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Obtiene un identificador para el proceso.|  
|[GetHelperThreadID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Obtiene el identificador de subproceso del sistema operativo (SO) para el subproceso del depurador auxiliar interno.|  
|[GetID (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Obtiene el identificador de sistema operativo (SO) del proceso.|  
|[GetObject (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Sin implementar.|  
|[GetThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Obtiene la instancia de ICorDebugThread que tiene el subproceso del sistema operativo especificado.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Obtiene el contexto del subproceso especificado.|  
|[IsOSSuspended (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Determina si el subproceso se ha suspendido porque el depurador que detenga el proceso.|  
|[IsTransitionStub (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Determina si es una dirección dentro de un código auxiliar que provocará una transición a código administrado.|  
|[ModifyLogSwitch (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Establece el nivel de gravedad del modificador de registro especificado.|  
|[ReadMemory (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Lee la memoria del proceso.|  
|[SetThreadContext (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Establece el contexto del subproceso especificado.|  
|[ThreadForFiberCookie (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Desusado.|  
|[WriteMemory (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Escribe datos en un área de memoria en el proceso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
