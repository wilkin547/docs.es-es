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
ms.openlocfilehash: 6c879af682e2d54ed3ae1e9821c0bd85b5cac27d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback (Interfaz)
Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Break (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al depurador cuando un <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta la instrucción en la secuencia de código.|  
|[Breakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica al depurador cuando se encuentra un punto de interrupción.|  
|[BreakpointSetError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al depurador que common language runtime (CLR) no pudo enlazar con precisión un punto de interrupción que estableció antes de que una función se compila con el compilador just-in-time (JIT).|  
|[ControlCTrap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al depurador que se captura CTRL+C en el proceso que se está depurando.|  
|[CreateAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al depurador que se ha creado un dominio de aplicación.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Notifica al depurador cuando un proceso se adjunta o se inicia por primera vez.|  
|[CreateThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al depurador que un subproceso ha iniciado la ejecución de código administrado.|  
|[DebuggerError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al depurador que se ha producido un error al intentar controlar un evento de CLR.|  
|[EditAndContinueRemap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Desusado. Notifica al depurador que se ha enviado un evento de reasignación al IDE.|  
|[EvalComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al depurador que se ha completado una evaluación.|  
|[EvalException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al depurador que una evaluación ha finalizado con una excepción no controlada.|  
|[Exception (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al depurador que se ha producido una excepción desde código administrado.|  
|[ExitAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al depurador que un dominio de aplicación ha salido.|  
|[ExitProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al depurador que un proceso ha terminado.|  
|[ExitThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al depurador que un subproceso que se estaba ejecutando código administrado ha terminado.|  
|[LoadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al depurador que un ensamblado CLR se ha cargado correctamente.|  
|[LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al depurador que se ha cargado una clase.|  
|[LoadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al depurador que se ha cargado correctamente un módulo CLR.|  
|[LogMessage (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método el <xref:System.Diagnostics.EventLog> clase para registrar un evento.|  
|[LogSwitch (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método el <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un modificador de depuración o traza.|  
|[NameChange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al depurador que se ha cambiado el nombre de un dominio de aplicación o el subproceso.|  
|[StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al depurador que se ha completado un paso.|  
|[UnloadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al depurador que se ha descargado un ensamblado CLR.|  
|[UnloadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al depurador que se está descargando una clase.|  
|[UnloadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al depurador que se ha descargado un módulo CLR (DLL).|  
|[UpdateModuleSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al depurador que han cambiado los símbolos para un módulo CLR.|  
  
## <a name="remarks"></a>Comentarios  
 Todas las devoluciones de llamada se serializa, denominados en el mismo subproceso y llama con el proceso en estado sincronizado.  
  
 Cada implementación de devolución de llamada debe llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución. Si `ICorDebugController::Continue` no se llama antes de que devuelve la devolución de llamada, el proceso seguirá detenido y no más devoluciones de llamada de evento se producirán hasta que `ICorDebugController::Continue` se llama.  
  
 Debe implementar un depurador [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) si se está depurando aplicaciones de la versión 2.0 de .NET Framework. Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
>  Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)  
 [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
