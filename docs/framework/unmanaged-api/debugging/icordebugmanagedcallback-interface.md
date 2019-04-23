---
title: ICorDebugManagedCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback
helpviewer_keywords:
- ICorDebugManagedCallback interface [.NET Framework debugging]
ms.assetid: b47f1d61-c7dc-4196-b926-0b08c94f7041
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: eacd10eecf2a8a2fc1b73a7f97eef5cb5eabafd4
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59133723"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback (Interfaz)
Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Break (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al depurador cuando un <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta la instrucción en la secuencia de código.|  
|[Breakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica al depurador cuando se encuentra un punto de interrupción.|  
|[BreakpointSetError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al depurador que common language runtime (CLR) no pudo enlazar con precisión un punto de interrupción que estableció antes de una función que se compilan just-in-time (JIT).|  
|[ControlCTrap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al depurador que se captura CTRL+C en el proceso que se está depurando.|  
|[CreateAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al depurador que se ha creado un dominio de aplicación.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Notifica al depurador cuando se asocia un proceso o se inicia por primera vez.|  
|[CreateThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al depurador que inicia un subproceso ejecuta código administrado.|  
|[DebuggerError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al depurador que se ha producido un error al intentar controlar un evento de CLR.|  
|[EditAndContinueRemap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Desusado. Notifica al depurador que se ha enviado un evento de reasignación al IDE.|  
|[EvalComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al depurador que se ha completado una evaluación.|  
|[EvalException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.|  
|[Exception (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al depurador que se ha producido una excepción desde código administrado.|  
|[ExitAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al depurador que se ha cerrado un dominio de aplicación.|  
|[ExitProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al depurador que un proceso ha terminado.|  
|[ExitThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al depurador que ha salido de un subproceso que se estaba ejecutando código administrado.|  
|[LoadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al depurador que se ha cargado correctamente un ensamblado CLR.|  
|[LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al depurador que se ha cargado una clase.|  
|[LoadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al depurador que se ha cargado correctamente un módulo CLR.|  
|[LogMessage (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método el <xref:System.Diagnostics.EventLog> clase para registrar un evento.|  
|[LogSwitch (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método el <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un conmutador de depuración y seguimiento.|  
|[NameChange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al depurador que se ha cambiado el nombre de un dominio de aplicación o el subproceso.|  
|[StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al depurador que se ha completado un paso.|  
|[UnloadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al depurador que se ha descargado un ensamblado CLR.|  
|[UnloadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al depurador que se está descargando una clase.|  
|[UnloadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al depurador que se ha descargado un módulo CLR (DLL).|  
|[UpdateModuleSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al depurador que han cambiado los símbolos para un módulo CLR.|  
  
## <a name="remarks"></a>Comentarios  
 Todas las devoluciones de llamada se serializa, llamados en el mismo subproceso y se llama con el proceso en estado sincronizado.  
  
 Cada implementación de devolución de llamada debe llamar a [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución. Si `ICorDebugController::Continue` no se llama antes de la devolución de llamada, el proceso seguirá detenido y no se producirá ninguna devolución de llamada de evento más hasta `ICorDebugController::Continue` se llama.  
  
 Debe implementar un depurador [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) si depurar aplicaciones de .NET Framework versión 2.0. Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
