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
ms.openlocfilehash: 7f9d4ac99234545ef75d9b91e6e84f79a133ffef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95694924"
---
# <a name="icordebugprocess-interface"></a>Interfaz ICorDebugProcess

Representa un proceso que ejecuta código administrado. Esta interfaz es una subclase de ICorDebugController.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ClearCurrentException](icordebugprocess-clearcurrentexception-method.md)|Borra la excepción no administrada actual en el subproceso especificado.|  
|[Método EnableLogMessages](icordebugprocess-enablelogmessages-method.md)|Habilita y deshabilita el envío de mensajes de registro al depurador.|  
|[Método EnumerateAppDomains](icordebugprocess-enumerateappdomains-method.md)|Enumera todos los dominios de aplicación del proceso.|  
|[Método EnumerateObjects](icordebugprocess-enumerateobjects-method.md)|Sin implementar.|  
|[Método GetHandle](icordebugprocess-gethandle-method.md)|Obtiene un identificador para el proceso.|  
|[Método GetHelperThreadID](icordebugprocess-gethelperthreadid-method.md)|Obtiene el identificador del subproceso del sistema operativo (SO) del subproceso auxiliar interno del depurador.|  
|[Método GetID](icordebugprocess-getid-method.md)|Obtiene el identificador del sistema operativo (SO) del proceso.|  
|[GetObject (Método)](icordebugprocess-getobject-method.md)|Sin implementar.|  
|[Método GetThread](icordebugprocess-getthread-method.md)|Obtiene la instancia de ICorDebugThread que tiene el identificador de subproceso de sistema operativo especificado.|  
|[GetThreadContext (Método)](icordebugprocess-getthreadcontext-method.md)|Obtiene el contexto para el subproceso especificado.|  
|[Método IsOSSuspended](icordebugprocess-isossuspended-method.md)|Determina si el subproceso se ha suspendido como resultado de que el depurador detenga el proceso.|  
|[Método IsTransitionStub](icordebugprocess-istransitionstub-method.md)|Determina si una dirección está dentro de un código auxiliar que producirá una transición a código administrado.|  
|[Método ModifyLogSwitch](icordebugprocess-modifylogswitch-method.md)|Establece el nivel de gravedad del modificador de registro especificado.|  
|[Método ReadMemory](icordebugprocess-readmemory-method.md)|Lee la memoria del proceso.|  
|[Método SetThreadContext](icordebugprocess-setthreadcontext-method.md)|Establece el contexto para el subproceso especificado.|  
|[Método ThreadForFiberCookie](icordebugprocess-threadforfibercookie-method.md)|Desusado.|  
|[Método WriteMemory](icordebugprocess-writememory-method.md)|Escribe datos en un área de memoria del proceso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebug (Interfaz)](icordebug-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
