---
description: 'Más información sobre: interfaz ICorDebugManagedCallback'
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
ms.openlocfilehash: 0dd33e4295caa8f5ae41c65d9bd10152737156ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722820"
---
# <a name="icordebugmanagedcallback-interface"></a>ICorDebugManagedCallback (Interfaz)

Proporciona métodos que permiten procesar las devoluciones de llamada del depurador.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método Break](icordebugmanagedcallback-break-method.md)|Notifica al depurador cuando <xref:System.Reflection.Emit.OpCodes.Break> se ejecuta una instrucción en la secuencia de código.|  
|[Método Breakpoint](icordebugmanagedcallback-breakpoint-method.md)|Notifica al depurador cuando se encuentra un punto de interrupción.|  
|[Método BreakpointSetError](icordebugmanagedcallback-breakpointseterror-method.md)|Notifica al depurador que el Common Language Runtime (CLR) no pudo enlazar con precisión un punto de interrupción establecido antes de que una función se compilara Just-in-Time (JIT).|  
|[Método ControlCTrap](icordebugmanagedcallback-controlctrap-method.md)|Notifica al depurador que se ha capturado CTRL + C en el proceso que se está depurando.|  
|[Método CreateAppDomain](icordebugmanagedcallback-createappdomain-method.md)|Notifica al depurador que se ha creado un dominio de aplicación.|  
|[Método CreateProcess](icordebugmanagedcallback-createprocess-method.md)|Notifica al depurador cuando un proceso se ha adjuntado o Iniciado por primera vez.|  
|[Método CreateThread](icordebugmanagedcallback-createthread-method.md)|Notifica al depurador que un subproceso ha empezado a ejecutar código administrado.|  
|[Método DebuggerError](icordebugmanagedcallback-debuggererror-method.md)|Notifica al depurador que se ha producido un error al intentar controlar un evento desde CLR.|  
|[Método EditAndContinueRemap](icordebugmanagedcallback-editandcontinueremap-method.md)|En desuso. Notifica al depurador que se ha enviado un evento de reasignación al IDE.|  
|[Método EvalComplete](icordebugmanagedcallback-evalcomplete-method.md)|Notifica al depurador que se ha completado una evaluación.|  
|[Método EvalException](icordebugmanagedcallback-evalexception-method.md)|Notifica al depurador que se ha finalizado una evaluación con una excepción no controlada.|  
|[Método Exception](icordebugmanagedcallback-exception-method.md)|Notifica al depurador que se ha producido una excepción del código administrado.|  
|[Método ExitAppDomain](icordebugmanagedcallback-exitappdomain-method.md)|Notifica al depurador que se ha salido de un dominio de aplicación.|  
|[ExitProcess (Método)](icordebugmanagedcallback-exitprocess-method.md)|Notifica al depurador que se ha salido de un proceso.|  
|[Método ExitThread](icordebugmanagedcallback-exitthread-method.md)|Notifica al depurador que un subproceso que estaba ejecutando código administrado ha salido.|  
|[Método LoadAssembly](icordebugmanagedcallback-loadassembly-method.md)|Notifica al depurador que se ha cargado correctamente un ensamblado CLR.|  
|[Método LoadClass](icordebugmanagedcallback-loadclass-method.md)|Notifica al depurador que se ha cargado una clase.|  
|[Método LoadModule](icordebugmanagedcallback-loadmodule-method.md)|Notifica al depurador que un módulo CLR se ha cargado correctamente.|  
|[Método LogMessage](icordebugmanagedcallback-logmessage-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método en la <xref:System.Diagnostics.EventLog> clase para registrar un evento.|  
|[Método LogSwitch](icordebugmanagedcallback-logswitch-method.md)|Notifica al depurador que un subproceso administrado de CLR ha llamado a un método en la <xref:System.Diagnostics.Switch> clase para crear, modificar o eliminar un modificador de depuración o traza.|  
|[Método NameChange](icordebugmanagedcallback-namechange-method.md)|Notifica al depurador que el nombre de un dominio de aplicación o un subproceso ha cambiado.|  
|[Método StepComplete](icordebugmanagedcallback-stepcomplete-method.md)|Notifica al depurador que se ha completado un paso.|  
|[Método UnloadAssembly](icordebugmanagedcallback-unloadassembly-method.md)|Notifica al depurador que se ha descargado un ensamblado CLR.|  
|[Método UnloadClass](icordebugmanagedcallback-unloadclass-method.md)|Notifica al depurador que se está descargando una clase.|  
|[Método UnloadModule](icordebugmanagedcallback-unloadmodule-method.md)|Notifica al depurador que se ha descargado un módulo CLR (DLL).|  
|[Método UpdateModuleSymbols](icordebugmanagedcallback-updatemodulesymbols-method.md)|Notifica al depurador que los símbolos para un módulo CLR han cambiado.|  
  
## <a name="remarks"></a>Observaciones  

 Todas las devoluciones de llamada se serializan, se llaman en el mismo subproceso y se llama con el proceso en el estado Synchronized.  
  
 Cada implementación de devolución de llamada debe llamar a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md) para reanudar la ejecución. Si `ICorDebugController::Continue` no se llama a antes de que se devuelva la devolución de llamada, el proceso seguirá detenido y no se producirán más devoluciones de llamada de eventos hasta que `ICorDebugController::Continue` se llame a.  
  
 Un depurador debe implementar [ICorDebugManagedCallback2](icordebugmanagedcallback2-interface.md) si está depurando .NET Framework aplicaciones de la versión 2,0. Una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` se pasa como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebug (Interfaz)](icordebug-interface.md)
- [ICorDebugManagedCallback2 (Interfaz)](icordebugmanagedcallback2-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
