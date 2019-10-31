---
title: ICorDebugManagedCallback2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback2
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback2
helpviewer_keywords:
- ICorDebugManagedCallback2 interface [.NET Framework debugging]
ms.assetid: cf7b7cfa-1c4b-4d8c-be70-4f9ed15a788b
topic_type:
- apiref
ms.openlocfilehash: 97f103844c38ebd3dbff058bfe96ab953cdba960
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131469"
---
# <a name="icordebugmanagedcallback2-interface"></a>ICorDebugManagedCallback2 (Interfaz)
Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de la interfaz [ICorDebugManagedCallback](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ChangeConnection (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-changeconnection-method.md)|Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.|  
|[CreateConnection (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-createconnection-method.md)|Notifica al depurador que se ha creado una nueva conexión.|  
|[DestroyConnection (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-destroyconnection-method.md)|Notifica al depurador que se ha terminado la conexión especificada.|  
|[Exception (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exception-method.md)|Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.|  
|[ExceptionUnwind (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-exceptionunwind-method.md)|Proporciona una notificación de estado durante el proceso de desenredo de excepciones.|  
|[FunctionRemapComplete (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapcomplete-method.md)|Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.|  
|[FunctionRemapOpportunity (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-functionremapopportunity-method.md)|Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.|  
|[MDANotification (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-mdanotification-method.md)|Proporciona una notificación de que la ejecución del código ha encontrado un mensaje del Asistente para la depuración administrada (MDA).|  
  
## <a name="remarks"></a>Comentarios  
 La interfaz de `ICorDebugManagedCallback2` amplía la interfaz `ICorDebugManagedCallback` para controlar los nuevos eventos de depuración introducidos en la .NET Framework versión 2,0.  
  
 Un depurador debe implementar `ICorDebugManagedCallback2` si está depurando .NET Framework aplicaciones 2,0. Se pasa una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](../../../../docs/framework/unmanaged-api/debugging/icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
