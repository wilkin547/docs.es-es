---
title: ICorDebugManagedCallback2::MDANotification (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2.MDANotification
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type:
- apiref
ms.openlocfilehash: ab3819d5c33f090fda1ca9c3dccb5d08ab8f84cc
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131458"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification (Método)
Proporciona una notificación de que la ejecución del código ha encontrado un asistente para la depuración administrada (MDA) en la aplicación que se está depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pController`  
 de Puntero a una interfaz ICorDebugController que expone el proceso o dominio de aplicación en el que se produjo el MDA.  
  
 Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para realizar una determinación.  
  
 `pThread`  
 de Puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se produjo el evento de depuración.  
  
 Si el MDA se produjo en un subproceso no administrado, el valor de `pThread` será null.  
  
 Debe obtener el identificador del subproceso del sistema operativo (SO) del propio objeto MDA.  
  
 `pMDA`  
 de Puntero a una interfaz [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) que expone la información de MDA.  
  
## <a name="remarks"></a>Comentarios  
 Un MDA es una advertencia heurística y no requiere ninguna acción explícita del depurador, salvo llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.  
  
 El Common Language Runtime (CLR) puede determinar qué MDA se activan y qué datos se encuentran en cualquier MDA determinado en cualquier momento. Por lo tanto, los depuradores no deben compilar ninguna funcionalidad que requiera patrones específicos de MDA.  
  
 Los MDA se pueden poner en cola y se activan poco después de encontrar el MDA. Esto puede ocurrir si el tiempo de ejecución necesita esperar hasta que alcanza un punto seguro para activar el MDA, en lugar de activar el MDA cuando lo encuentra. También significa que el tiempo de ejecución puede activar varios MDA en un único conjunto de devoluciones de llamada en cola (similar a una operación de evento "Attach").  
  
 Un depurador debe liberar la referencia a una instancia de `ICorDebugMDA` inmediatamente después de volver de la devolución de llamada `MDANotification`, para permitir que CLR recicle la memoria consumida por un MDA. Liberar la instancia puede mejorar el rendimiento si se activan muchos MDA.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
