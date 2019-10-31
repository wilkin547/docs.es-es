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
ms.openlocfilehash: 96dedcd27e87c5afc504e7840100eb121410675e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73130757"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback (Interfaz)
Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Break (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-break-method.md)|Notifica al depurador cuando se ejecuta una instrucción <xref:System.Reflection.Emit.OpCodes.Break> en la secuencia de código.|  
|[Breakpoint (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpoint-method.md)|Notifica al depurador cuando se encuentra un punto de interrupción.|  
|[BreakpointSetError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al depurador que el Common Language Runtime (CLR) no pudo enlazar con precisión un punto de interrupción establecido antes de que una función se compilara Just-in-Time (JIT).|  
|[ControlCTrap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-controlctrap-method.md)|Notifica al depurador que se ha capturado CTRL + C en el proceso que se está depurando.|  
|[CreateAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createappdomain-method.md)|Notifica al depurador que se ha creado un dominio de aplicación.|  
|[CreateProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createprocess-method.md)|Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.|  
|[CreateThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-createthread-method.md)|Notifica al depurador que un subproceso ha empezado a ejecutar código administrado.|  
|[DebuggerError (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-debuggererror-method.md)|Notifica al depurador que se ha producido un error al intentar controlar un evento desde CLR.|  
|[EditAndContinueRemap (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-editandcontinueremap-method.md)|Desusado. Notifica al depurador que se ha enviado un evento de reasignación al IDE.|  
|[EvalComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalcomplete-method.md)|Notifica al depurador que se ha completado una evaluación.|  
|[EvalException (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-evalexception-method.md)|Notifica al depurador que se ha finalizado una evaluación con una excepción no controlada.|  
|[Exception (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exception-method.md)|Notifica al depurador que se ha producido una excepción del código administrado.|  
|[ExitAppDomain (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md)|Notifica al depurador que se ha salido de un dominio de aplicación.|  
|[ExitProcess (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md)|Notifica al depurador que se ha salido de un proceso.|  
|[ExitThread (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitthread-method.md)|Notifica al depurador que un subproceso que estaba ejecutando código administrado ha salido.|  
|[LoadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadassembly-method.md)|Notifica al depurador que se ha cargado correctamente un ensamblado CLR.|  
|[LoadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadclass-method.md)|Notifica al depurador que se ha cargado una clase.|  
|[LoadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-loadmodule-method.md)|Notifica al depurador que un módulo CLR se ha cargado correctamente.|  
|[LogMessage (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logmessage-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método en la clase <xref:System.Diagnostics.EventLog> para registrar un evento.|  
|[LogSwitch (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-logswitch-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método en la clase <xref:System.Diagnostics.Switch> para crear, modificar o eliminar un modificador de depuración o traza.|  
|[NameChange (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-namechange-method.md)|Notifica al depurador que el nombre de un dominio de aplicación o un subproceso ha cambiado.|  
|[StepComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-stepcomplete-method.md)|Notifica al depurador que se ha completado un paso.|  
|[UnloadAssembly (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadassembly-method.md)|Notifica al depurador que se ha descargado un ensamblado CLR.|  
|[UnloadClass (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadclass-method.md)|Notifica al depurador que se está descargando una clase.|  
|[UnloadModule (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-unloadmodule-method.md)|Notifica al depurador que se ha descargado un módulo CLR (DLL).|  
|[UpdateModuleSymbols (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al depurador que los símbolos para un módulo CLR han cambiado.|  
  
## <a name="remarks"></a>Comentarios  
 Todas las devoluciones de llamada se serializan, se llaman en el mismo subproceso y se llama con el proceso en el estado Synchronized.  
  
 Cada implementación de devolución de llamada debe llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución. Si no se llama a `ICorDebugController::Continue` antes de que se devuelva la devolución de llamada, el proceso seguirá detenido y no se producirán más devoluciones de llamada de eventos hasta que se llame a `ICorDebugController::Continue`.  
  
 Un depurador debe implementar [ICorDebugManagedCallback2](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md) si está depurando .NET Framework aplicaciones de la versión 2,0. Se pasa una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebug-interface.md)
- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
