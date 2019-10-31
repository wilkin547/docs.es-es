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
ms.openlocfilehash: 2d865f837d38894e8449af671e2d12e7676dd040
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129132"
---
# <a name="icordebugunmanagedcallbackdebugevent-method"></a>ICorDebugUnmanagedCallback::DebugEvent (Método)
Notifica al depurador que se ha desencadenado un evento nativo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT DebugEvent (  
    [in] LPDEBUG_EVENT  pDebugEvent,  
    [in] BOOL           fOutOfBand  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pDebugEvent`  
 de Puntero al evento nativo.  
  
 `fOutOfBand`  
 [in] `true`, si la interacción con el estado de proceso administrado no es posible después de que se produzca un evento no administrado, hasta que el depurador llame a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md); de lo contrario, `false`.  
  
## <a name="remarks"></a>Comentarios  
 Si el subproceso que se está depurando es un subproceso de Win32, no use ningún miembro de la interfaz de depuración de Win32. Solo se puede llamar a `ICorDebugController::Continue` en un subproceso de Win32 y solo al continuar después de un evento fuera de banda.  
  
 La devolución de llamada de `DebugEvent` no sigue las reglas estándar para las devoluciones de llamada. Cuando llame a `DebugEvent`, el proceso estará en el estado sin procesar, depuración de sistema operativo detenido. El proceso no se sincronizará. Se especificará automáticamente el estado Synchronized cuando sea necesario para satisfacer las solicitudes de información sobre el código administrado, lo que puede dar lugar a otras devoluciones de llamada de `DebugEvent` anidadas.  
  
 Llame a [ICorDebugProcess:: ClearCurrentException (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-clearcurrentexception-method.md) en el proceso para omitir un evento de excepción antes de continuar con el proceso. Al llamar a este método, se envía DBG_CONTINUE en lugar de DBG_EXCEPTION_NOT_HANDLED en la solicitud continue y se borran automáticamente los puntos de interrupción fuera de banda y las excepciones de un solo paso. Los eventos fuera de banda pueden aparecer en cualquier momento, incluso cuando la aplicación que se está depurando aparece detenida y cuando ya existe un evento en banda pendiente.  
  
 En el .NET Framework versión 2,0, el depurador debe continuar inmediatamente después de un evento de punto de interrupción fuera de banda. El depurador debe utilizar los métodos [ICorDebugProcess2:: SetUnmanagedBreakpoint (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-setunmanagedbreakpoint-method.md) y [ICorDebugProcess2:: ClearUnmanagedBreakpoint (](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess2-clearunmanagedbreakpoint-method.md) para agregar y quitar puntos de interrupción. Estos métodos omitirán automáticamente los puntos de interrupción fuera de banda. Por lo tanto, los únicos puntos de interrupción fuera de banda que se envían deben ser puntos de interrupción sin formato que ya estén en el flujo de instrucciones, como una llamada a la función `DebugBreak` de Win32. No intente usar `ICorDebugProcess::ClearCurrentException`, [ICorDebugProcess:: GetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess-setthreadcontext-method.md)o cualquier otro miembro de la [API de depuración](../../../../docs/framework/unmanaged-api/debugging/index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugUnmanagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugunmanagedcallback-interface.md)
