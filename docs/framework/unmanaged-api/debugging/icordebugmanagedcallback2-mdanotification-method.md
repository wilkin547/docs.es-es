---
title: "ICorDebugManagedCallback2::MDANotification (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugManagedCallback2.MDANotification
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugManagedCallback2::MDANotification
helpviewer_keywords:
- MDANotification method [.NET Framework debugging]
- ICorDebugManagedCallback2::MDANotification method [.NET Framework debugging]
ms.assetid: 93f79627-bd31-4f4f-b95d-46a032a52fe4
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: aeddab575f6667dbd27ab3474ae9c6e00dd05750
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugmanagedcallback2mdanotification-method"></a>ICorDebugManagedCallback2::MDANotification (Método)
Proporciona notificación de que la ejecución de código ha encontrado a un Asistente para depuración administrada (MDA) en la aplicación que se está depurando.  
  
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
 [in] Un puntero a un ICorDebugController (interfaz) que expone el proceso o dominio de aplicación en la que ocurrió el MDA.  
  
 Un depurador no debe hacer ninguna suposición sobre si el controlador es un proceso o un dominio de aplicación, aunque siempre puede consultar la interfaz para determinarlo.  
  
 `pThread`  
 [in] Un puntero a una interfaz ICorDebugThread que expone el subproceso administrado en el que se ha producido el evento de depuración.  
  
 Si el MDA se produjo en una no administrada de subprocesos, el valor de `pThread` será null.  
  
 Debe obtener el identificador de subproceso del sistema operativo (SO) desde el propio objeto MDA.  
  
 `pMDA`  
 [in] Un puntero a un [ICorDebugMDA](../../../../docs/framework/unmanaged-api/debugging/icordebugmda-interface.md) interfaz que expone la información de MDA.  
  
## <a name="remarks"></a>Comentarios  
 Un MDA es un aviso heurístico y no requiere ninguna acción del depurador explícita salvo llamar a [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) para reanudar la ejecución de la aplicación que se está depurando.  
  
 Common language runtime (CLR) puede determinar qué MDA se desencadenan y qué datos están en cualquier MDA determinado en cualquier momento. Por lo tanto, los depuradores no deberían compilar funcionalidad que requiera modelos de MDA concretos.  
  
 MDA pueden ser en cola y activar poco después de que se encuentra el MDA. Esto podría suceder si el tiempo de ejecución debe esperar hasta que alcanza un punto seguro para desencadenar el MDA, en lugar de activar el MDA cuando lo encuentra. También significa que el tiempo de ejecución puede activar un número de MDA en un conjunto único de devoluciones de llamada en cola (similares a una operación de eventos "adjuntar").  
  
 Un depurador debería liberar la referencia a un `ICorDebugMDA` instancia inmediatamente después de volver de la `MDANotification` devolución de llamada, para permitir que el CLR recicle la memoria utilizada por un MDA. Al lanzar la instancia puede mejorar el rendimiento si se desencadenan muchos MDA.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Diagnosing Errors with Managed Debugging Assistants (Diagnóstico de errores con asistentes para la depuración administrada)](../../../../docs/framework/debug-trace-profile/diagnosing-errors-with-managed-debugging-assistants.md)  
 [ICorDebugManagedCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback2-interface.md)  
 [ICorDebugManagedCallback (interfaz)](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
