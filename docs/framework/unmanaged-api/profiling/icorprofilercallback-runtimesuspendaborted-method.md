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
ms.openlocfilehash: a3fb5c398b8ccd7caba0b005bcf03e64ecef4ba5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503255"
---
# <a name="icorprofilercallbackruntimesuspendaborted-method"></a>ICorProfilerCallback::RuntimeSuspendAborted (Método)
Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RuntimeSuspendAborted();  
```  
  
## <a name="remarks"></a>Comentarios  
 La suspensión en tiempo de ejecución se puede anular si dos subprocesos intentan suspender el tiempo de ejecución simultáneamente.  
  
 La devolución de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) o la `RuntimeSuspendAborted` devolución de llamada se producirán en un único subproceso después de una devolución de llamada [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) .  
  
 `RuntimeSuspendAborted`Se garantiza que la devolución de llamada se produce en el mismo subproceso que la `RuntimeSuspendStarted` devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
