---
title: ICorDebugController::SetAllThreadsDebugState (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugController.SetAllThreadsDebugState
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugController::SetAllThreadsDebugState
helpviewer_keywords:
- SetAllThreadsDebugState method [.NET Framework debugging]
- ICorDebugController::SetAllThreadsDebugState method [.NET Framework debugging]
ms.assetid: bdda4bd7-4743-4d58-a22b-8067e967db95
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ee396c512dca2bea0a7a9737d5515defce4b2b0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugcontrollersetallthreadsdebugstate-method"></a>ICorDebugController::SetAllThreadsDebugState (Método)
Establece el estado de depuración de todos los subprocesos administrados en el proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetAllThreadsDebugState (  
    [in] CorDebugThreadState  state,  
    [in] ICorDebugThread      *pExceptThisThread  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `state`  
 [in] Un valor de la enumeración "CorDebugThreadState" que especifica el estado del subproceso para la depuración.  
  
 `pExceptThisThread`  
 [in] Un puntero a un objeto de "ICorDebugThread" que representa un subproceso que deben excluirse de la configuración de estado de depuración. Si este valor es null, no se excluye ningún subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El `SetAllThreadsDebugState` método puede afectar a subprocesos que no son visibles a través de [EnumerateThreads (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), así que los subprocesos suspendidos con el `SetAllThreadsDebugState` método necesitará su reanudación con el `SetAllThreadsDebugState` método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 
