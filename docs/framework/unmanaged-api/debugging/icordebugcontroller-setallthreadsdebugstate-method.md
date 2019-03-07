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
ms.openlocfilehash: 0dffe95df75fafe293c225c513db7ff7896765fa
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501778"
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
  
## <a name="parameters"></a>Parámetros  
 `state`  
 [in] Un valor de la enumeración "CorDebugThreadState" que especifica el estado del subproceso para la depuración.  
  
 `pExceptThisThread`  
 [in] Un puntero a un objeto "ICorDebugThread" que representa un subproceso que se va a excluir de la configuración de estado de depuración. Si este valor es null, no se excluye ningún subproceso.  
  
## <a name="remarks"></a>Comentarios  
 El `SetAllThreadsDebugState` método puede afectar a los subprocesos que no son visibles a través de [EnumerateThreads (método)](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-enumeratethreads-method.md), así que los subprocesos suspendidos con el `SetAllThreadsDebugState` necesitará el método con el `SetAllThreadsDebugState` método.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

