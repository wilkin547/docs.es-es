---
title: ICorProfilerCallback4::ReJITCompilationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4.ReJITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4::ReJITCompilationStarted
helpviewer_keywords:
- ReJITCompilationStarted method, ICorProfilerCallback4 interface [.NET Framework profiling]
- ICorProfilerCallback4::ReJITCompilationStarted method [.NET Framework profiling]
ms.assetid: 512fdd00-262a-4456-a075-365ef4133c4d
topic_type:
- apiref
ms.openlocfilehash: be257930ca0fad658afa75d6efa4573d4f888a2b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177091"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted (Método)
Notifica al generador de perfiles que el compilador Just-In-Time (JIT) ha comenzado a volver a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReJITCompilationStarted(
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [en] El identificador de la función que el compilador JIT ha comenzado a volver a compilar.  
  
 `rejitId`  
 [en] El identificador de recompilación de la nueva versión de la función.  
  
 `fIsSafeToBlock`  
 [en] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada vuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución. Un valor `true` de no daña el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.  
  
## <a name="remarks"></a>Observaciones  
 Es posible recibir más de `ReJITCompilationStarted` un par de llamadas al método [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md) para cada función debido a la forma en que el tiempo de ejecución controla los constructores de clase. Por ejemplo, el tiempo de ejecución comienza a volver a compilar el método A, pero es necesario ejecutar el constructor de clase para la clase B. Por lo tanto, el tiempo de ejecución vuelve a compilar el constructor para la clase B y lo ejecuta. Mientras se ejecuta el constructor, realiza una llamada al método A, lo que hace que el método A se vuelva a compilar. En este escenario, se detiene la primera recompilación del método A. Sin embargo, ambos intentos de volver a compilar el método A se notifican con eventos de recompilación JIT.  
  
 Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada de recompilación JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada. Por ejemplo, el `ReJITCompilationStarted`subproceso A llama a ; sin embargo, antes de que el subproceso A llame a [ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md), el `ReJITCompilationStarted` subproceso B llama a [ICorProfilerCallback::ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la devolución de llamada para el subproceso A. Puede parecer que el identificador de función aún no debe ser válido porque el generador de perfiles aún no ha recibido una llamada a [ReJITCompilationFinished.](icorprofilercallback4-rejitcompilationfinished-method.md) Sin embargo, en este caso, el IDENTIFICADOR de función es válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)
- [JITCompilationFinished (método)](icorprofilercallback-jitcompilationfinished-method.md)
- [Método ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)
