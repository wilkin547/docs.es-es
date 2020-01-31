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
ms.openlocfilehash: b2429052173a187297b67c756213e5d27a79298b
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76792602"
---
# <a name="icordebugprocess-interface"></a>Interfaz ICorDebugProcess
Representa un proceso que ejecuta código administrado. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ClearCurrentException (método)](icordebugprocess-clearcurrentexception-method.md)|Borra la excepción no administrada actual en el subproceso especificado.|  
|[EnableLogMessages (método)](icordebugprocess-enablelogmessages-method.md)|Habilita y deshabilita el envío de mensajes de registro al depurador.|  
|[EnumerateAppDomains (método)](icordebugprocess-enumerateappdomains-method.md)|Enumera todos los dominios de aplicación del proceso.|  
|[EnumerateObjects (método)](icordebugprocess-enumerateobjects-method.md)|Sin implementar.|  
|[GetHandle (método)](icordebugprocess-gethandle-method.md)|Obtiene un identificador para el proceso.|  
|[GetHelperThreadID (método)](icordebugprocess-gethelperthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.|  
|[GetID (método)](icordebugprocess-getid-method.md)|Obtiene el identificador del sistema operativo (SO) del proceso.|  
|[GetObject (método)](icordebugprocess-getobject-method.md)|Sin implementar.|  
|[GetThread (método)](icordebugprocess-getthread-method.md)|Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.|  
|[GetThreadContext (método)](icordebugprocess-getthreadcontext-method.md)|Obtiene el contexto para el subproceso especificado.|  
|[IsOSSuspended (método)](icordebugprocess-isossuspended-method.md)|Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.|  
|[IsTransitionStub (método)](icordebugprocess-istransitionstub-method.md)|Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.|  
|[ModifyLogSwitch (método)](icordebugprocess-modifylogswitch-method.md)|Establece el nivel de gravedad del modificador de registro especificado.|  
|[ReadMemory (método)](icordebugprocess-readmemory-method.md)|Lee la memoria del proceso.|  
|[SetThreadContext (método)](icordebugprocess-setthreadcontext-method.md)|Establece el contexto para el subproceso especificado.|  
|[ThreadForFiberCookie (método)](icordebugprocess-threadforfibercookie-method.md)|Opción obsoleta.|  
|[WriteMemory (método)](icordebugprocess-writememory-method.md)|Escribe datos en un área de memoria del proceso.|  
  
## <a name="remarks"></a>Notas  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](icordebug-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
