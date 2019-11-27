---
title: ICorProfilerCallback::RuntimeSuspendAborted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendAborted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendAborted method [.NET Framework profiling]
- RuntimeSuspendAborted method [.NET Framework profiling]
ms.assetid: 5a8a4277-345b-448b-a028-fc8cff9998aa
topic_type:
- apiref
ms.openlocfilehash: fb09a9422f2aeec239f9aef25fb61c731e0aa2e9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74430612"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a>ICorProfilerCallback::RuntimeSuspendAborted (Método)
Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a>Comentarios  
 La suspensión en tiempo de ejecución se puede anular si dos subprocesos intentan suspender el tiempo de ejecución simultáneamente.  
  
 La devolución de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) o la devolución de llamada `RuntimeSuspendAborted` se producirán en un único subproceso después de una devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) .  
  
 Se garantiza que la devolución de llamada de `RuntimeSuspendAborted` se produce en el mismo subproceso que la devolución de llamada de `RuntimeSuspendStarted`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
