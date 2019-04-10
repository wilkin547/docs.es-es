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
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59216800"
---
# <a name="icordebugprocess-interface"></a>Interfaz ICorDebugProcess
Representa un proceso que ejecuta código administrado. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md)|Borra la excepción no administrada actual del subproceso especificado.|  
|[Método EnableLogMessages](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enablelogmessages-method.md)|Habilita y deshabilita el envío de mensajes de registro al depurador.|  
|[Método EnumerateAppDomains](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateappdomains-method.md)|Enumera todos los dominios de aplicación en el proceso.|  
|[Método EnumerateObjects](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-enumerateobjects-method.md)|Sin implementar.|  
|[Método GetHandle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethandle-method.md)|Obtiene un identificador para el proceso.|  
|[Método GetHelperThreadID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-gethelperthreadid-method.md)|Obtiene el identificador de subproceso del sistema operativo (SO) para el subproceso del depurador auxiliar interno.|  
|[Método GetID](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getid-method.md)|Obtiene el identificador de sistema operativo (SO) del proceso.|  
|[GetObject (Método)](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getobject-method.md)|Sin implementar.|  
|[Método GetThread](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthread-method.md)|Obtiene la instancia de ICorDebugThread que tiene el subproceso del sistema operativo especificado.|  
|[Método GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md)|Obtiene el contexto del subproceso especificado.|  
|[Método IsOSSuspended](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-isossuspended-method.md)|Determina si el subproceso se ha suspendido porque el depurador que detenga el proceso.|  
|[Método IsTransitionStub](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-istransitionstub-method.md)|Determina si es una dirección dentro de un código auxiliar que provocará una transición a código administrado.|  
|[Método ModifyLogSwitch](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-modifylogswitch-method.md)|Establece el nivel de gravedad del modificador de registro especificado.|  
|[Método ReadMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-readmemory-method.md)|Lee la memoria del proceso.|  
|[Método SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)|Establece el contexto del subproceso especificado.|  
|[Método ThreadForFiberCookie](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-threadforfibercookie-method.md)|Desusado.|  
|[Método WriteMemory](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-writememory-method.md)|Escribe datos en un área de memoria en el proceso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [Interfaces para depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
