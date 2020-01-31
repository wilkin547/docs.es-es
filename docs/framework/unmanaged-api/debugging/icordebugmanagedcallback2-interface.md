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
ms.openlocfilehash: 43982ebb634843c0130c3321aa84c90b84e8c786
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76793311"
---
# <a name="icordebugmanagedcallback2-interface"></a>ICorDebugManagedCallback2 (Interfaz)
Proporciona métodos para admitir el control de excepciones del depurador y asistentes para depuración administrada (MDA). `ICorDebugManagedCallback2` es una extensión lógica de la interfaz [ICorDebugManagedCallback](icordebugmanagedcallback-interface.md) .  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ChangeConnection (método)](icordebugmanagedcallback2-changeconnection-method.md)|Notifica al depurador que ha cambiado el conjunto de tareas asociado a la conexión especificada.|  
|[CreateConnection (método)](icordebugmanagedcallback2-createconnection-method.md)|Notifica al depurador que se ha creado una nueva conexión.|  
|[DestroyConnection (método)](icordebugmanagedcallback2-destroyconnection-method.md)|Notifica al depurador que se ha terminado la conexión especificada.|  
|[Exception (método)](icordebugmanagedcallback2-exception-method.md)|Notifica al depurador que se ha iniciado una búsqueda de un controlador de excepciones.|  
|[ExceptionUnwind (método)](icordebugmanagedcallback2-exceptionunwind-method.md)|Proporciona una notificación de estado durante el proceso de desenredo de excepciones.|  
|[FunctionRemapComplete (método)](icordebugmanagedcallback2-functionremapcomplete-method.md)|Notifica al depurador que la ejecución del código ha cambiado a una nueva versión de una función editada.|  
|[FunctionRemapOpportunity (método)](icordebugmanagedcallback2-functionremapopportunity-method.md)|Notifica al depurador que la ejecución del código ha alcanzado un punto de secuencia en una versión anterior de una función editada.|  
|[MDANotification (método)](icordebugmanagedcallback2-mdanotification-method.md)|Proporciona una notificación de que la ejecución del código ha encontrado un mensaje del Asistente para la depuración administrada (MDA).|  
  
## <a name="remarks"></a>Notas  
 La interfaz de `ICorDebugManagedCallback2` amplía la interfaz `ICorDebugManagedCallback` para controlar los nuevos eventos de depuración introducidos en la .NET Framework versión 2,0.  
  
 Un depurador debe implementar `ICorDebugManagedCallback2` si está depurando .NET Framework aplicaciones 2,0. Se pasa una instancia de `ICorDebugManagedCallback` o `ICorDebugManagedCallback2` como el objeto de devolución de llamada a [ICorDebug:: SetManagedHandler (](icordebug-setmanagedhandler-method.md).  
  
> [!NOTE]
> Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Diagnóstico de errores con asistentes para la depuración administrada](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [Interfaces de depuración](debugging-interfaces.md)
- [ICorDebugManagedCallback (interfaz)](icordebugmanagedcallback-interface.md)
