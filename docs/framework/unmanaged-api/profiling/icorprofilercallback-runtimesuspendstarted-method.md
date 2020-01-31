---
title: ICorProfilerCallback::RuntimeSuspendStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type:
- apiref
ms.openlocfilehash: e88f6356c2e29a1d8a9e49527c5921e8155c3ce4
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865888"
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted (Método)
Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
## <a name="parameters"></a>Parameters  
 `suspendReason`  
 de Un valor de la enumeración [COR_PRF_SUSPEND_REASON](cor-prf-suspend-reason-enumeration.md) que indica el motivo de la suspensión.  
  
## <a name="remarks"></a>Notas  
 Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución. En ese momento, también se suspenderán hasta que se reanude el tiempo de ejecución. Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución. Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si ya están en código interrumpido, o se les pide que se suspendan cuando llegan a código interrumpido.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [RuntimeSuspendAborted (método)](icorprofilercallback-runtimesuspendaborted-method.md)
- [RuntimeSuspendFinished (método)](icorprofilercallback-runtimesuspendfinished-method.md)
