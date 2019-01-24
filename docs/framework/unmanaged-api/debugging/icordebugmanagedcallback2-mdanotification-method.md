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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 90c805a5f1f1da990564034fc292562d5f933d71
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54608094"
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification (Método)
Proporciona notificación de que la ejecución de código ha encontrado a un Asistente para depuración administrada (MDA) de la aplicación que se está depurando.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT MDANotification(  
    [in] ICorDebugController  *pController,  
    [in] ICorDebugThread      *pThread,  
    [in] ICorDebugMDA         *pMDA  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pController`  
 [in] Un puntero a un ICorDebugController (interfaz) que expone el proceso o un dominio de aplicación en el que se ha producido el MDA.  
  
 Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para tomar una decisión.  
  
 `pThread`  
 [in] Un puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se ha producido el evento de depuración.  
  
 Si el MDA se produjo en una no administrado de subprocesos, el valor de `pThread` será null.  
  
 Debe obtener el identificador de subproceso del sistema operativo (SO) desde el propio objeto MDA.  
  
 `pMDA`  
 [in] Un puntero a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaz que expone la información de MDA.  
  
## <a name="remarks"></a>Comentarios  
 Un MDA es una advertencia heurística y no requiere ninguna acción explícita del depurador, excepto que realiza la llamada [ICorDebugController](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.  
  
 Common language runtime (CLR) puede determinar qué MDA se desencadenan y qué datos están en cualquier MDA en cualquier momento determinado. Por lo tanto, los depuradores no deben compilar cualquier funcionalidad que requiera modelos de MDA concretos.  
  
 MDA se pueden poner en cola y poco después de que se encuentra el MDA se desencadena. Esto podría suceder si el tiempo de ejecución debe esperar hasta que alcanza un punto seguro para activar el MDA, en lugar de activar el MDA cuando lo encuentra. También significa que el tiempo de ejecución puede desencadenar un número de MDA en un único conjunto de devoluciones de llamada en cola (similares a una operación de evento "adjuntar").  
  
 Un depurador debe liberar la referencia a un `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que el CLR se recicle la memoria utilizada por un MDA. Liberar la instancia puede mejorar el rendimiento si se desencadenan muchos MDA.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)
- [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)
- [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
