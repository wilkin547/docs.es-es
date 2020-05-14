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
ms.openlocfilehash: 24c316ea6bab11fb55e8e0fc1dc9832a312dbc6a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83397192"
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
 [in] `true` , si la interacción con el estado de proceso administrado no es posible después de que se produzca un evento no administrado, hasta que el depurador llama a [ICorDebugController:: Continue](icordebugcontroller-continue-method.md); de lo contrario, `false` .  
  
## <a name="remarks"></a>Comentarios  
 Si el subproceso que se está depurando es un subproceso de Win32, no use ningún miembro de la interfaz de depuración de Win32. Solo se puede llamar a `ICorDebugController::Continue` en un subproceso de Win32 y solo al continuar después de un evento fuera de banda.  
  
 La `DebugEvent` devolución de llamada no sigue las reglas estándar para las devoluciones de llamada. Cuando llame a `DebugEvent` , el proceso estará en el estado sin procesar y depuración de sistema operativo detenido. El proceso no se sincronizará. Se especificará automáticamente el estado Synchronized cuando sea necesario para satisfacer las solicitudes de información sobre el código administrado, lo que puede dar lugar a otras `DebugEvent` devoluciones de llamada anidadas.  
  
 Llame a [ICorDebugProcess:: ClearCurrentException (](icordebugprocess-clearcurrentexception-method.md) en el proceso para omitir un evento de excepción antes de continuar con el proceso. Al llamar a este método, se envía DBG_CONTINUE en lugar de DBG_EXCEPTION_NOT_HANDLED en la solicitud continue y se borran automáticamente los puntos de interrupción fuera de banda y las excepciones de un solo paso. Los eventos fuera de banda pueden aparecer en cualquier momento, incluso cuando la aplicación que se está depurando aparece detenida y cuando ya existe un evento en banda pendiente.  
  
 En el .NET Framework versión 2,0, el depurador debe continuar inmediatamente después de un evento de punto de interrupción fuera de banda. El depurador debe utilizar los métodos [ICorDebugProcess2:: SetUnmanagedBreakpoint (](icordebugprocess2-setunmanagedbreakpoint-method.md) y [ICorDebugProcess2:: ClearUnmanagedBreakpoint (](icordebugprocess2-clearunmanagedbreakpoint-method.md) para agregar y quitar puntos de interrupción. Estos métodos omitirán automáticamente los puntos de interrupción fuera de banda. Por lo tanto, los únicos puntos de interrupción fuera de banda que se envían deben ser puntos de interrupción sin formato que ya estén en el flujo de instrucciones, como una llamada a la `DebugBreak` función de Win32. No intente usar `ICorDebugProcess::ClearCurrentException` , [ICorDebugProcess:: GetThreadContext](icordebugprocess-getthreadcontext-method.md), [ICorDebugProcess:: SetThreadContext](icordebugprocess-setthreadcontext-method.md)o cualquier otro miembro de la [API de depuración](index.md).  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorDebugUnmanagedCallback (Interfaz)](icordebugunmanagedcallback-interface.md)
