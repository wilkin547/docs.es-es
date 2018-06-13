---
title: ICorDebugUnmanagedCallback::DebugEvent (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback.DebugEvent
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback::DebugEvent
helpviewer_keywords:
- DebugEvent method [.NET Framework debugging]
- ICorDebugUnmanagedCallback::DebugEvent method [.NET Framework debugging]
ms.assetid: be9cab04-65ec-44d5-a39a-f90709fdd043
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 51ccc7b1b50613f0d2b44a9e101314128782c412
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33423135"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent (Método)
Notifica al depurador que se ha desencadenado un evento nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pDebugEvent`  
 [in] Un puntero al evento nativo.  
  
 `fOutOfBand`  
 [in] `true`, si es posible la interacción con el estado del proceso administrado después de que se produce un evento no administrado, hasta que el depurador llama [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); en caso contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si el subproceso que se está depurando es un subproceso de Win32, no utilice a todos los miembros de Win32, interfaz de depuración. Puede llamar a `ICorDebugController::Continue` sólo en un subproceso de Win32 y solo cuando continuar más allá de un evento fuera de banda.  
  
 El `DebugEvent` devolución de llamada no sigue las reglas estándares para las devoluciones de llamada. Cuando se llama a `DebugEvent`, el proceso estará en el modo raw, estado de detención de depuración del sistema operativo. El proceso no se sincronizarán. Especificará automáticamente el estado sincronizado cuando sea necesario para satisfacer las solicitudes para obtener información sobre el código administrado, lo que puede producir otros anidados `DebugEvent` las devoluciones de llamada.  
  
 Llame a [ICorDebugProcess:: ClearCurrentException](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) en el proceso para omitir un evento de excepción antes de continuar el proceso. Llamar a este método envía DBG_CONTINUE en lugar de DBG_EXCEPTION_NOT_HANDLED en la solicitud y borra automáticamente los puntos de interrupción fuera de banda y las excepciones de paso a paso. Eventos fuera de banda pueden consultar en cualquier momento, incluso cuando la aplicación que se está depura aparece detenida y cuando ya existe un evento en banda pendiente.  
  
 En la versión 2.0 de .NET Framework, el depurador debe continuar inmediatamente tras un evento de punto de interrupción fuera de banda. El depurador debería estar utilizando el [ICorDebugProcess2:: SetUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) y [ICorDebugProcess2:: ClearUnmanagedBreakpoint](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) métodos para agregar y quitar puntos de interrupción. Estos métodos omitirá los puntos de interrupción fuera de banda automáticamente. Por lo tanto, los puntos de interrupción solo fuera de banda que se distribución deben ser puntos de interrupción sin formato que ya están en la secuencia de instrucciones, como una llamada a Win32 `DebugBreak` función. No intente utilizar `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md), o cualquier otro miembro de la [API de depuración](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorDebugUnmanagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
