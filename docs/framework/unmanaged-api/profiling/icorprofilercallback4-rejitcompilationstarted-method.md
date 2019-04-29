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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b8f2ada73686dfbe5629e21cfc6468becbd4ccc5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61597367"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted (Método)
Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función que se ha iniciado el compilador JIT para volver a compilar.  
  
 `rejitId`  
 [in] El identificador de la recompilación de la nueva versión de la función.  
  
 `fIsSafeToBlock`  
 [in] `true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que la de bloqueo no afectará al funcionamiento del tiempo de ejecución. Un valor de `true` no daña el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.  
  
## <a name="remarks"></a>Comentarios  
 Es posible recibir más de un par de `ReJITCompilationStarted` y [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) método llama para cada función debido al modo en el tiempo de ejecución controla los constructores de clase. Por ejemplo, el tiempo de ejecución empieza a compilar un método, pero el constructor de la clase B debe ejecutarse. Por lo tanto, el tiempo de ejecución vuelve a compilar el constructor de clase B y lo ejecuta. Mientras se ejecuta el constructor, realiza una llamada al método A, lo que hace que el método a compilarse de nuevo. En este escenario, se detiene la primera recompilación de un método. Sin embargo, ambos intenta volver a compilar una son se notifica con eventos de recompilación JIT del método.  
  
 Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada de recompilación JIT en casos donde dos subprocesos están realizando simultáneamente las devoluciones de llamada. Por ejemplo, un subproceso a llama a `ReJITCompilationStarted`; sin embargo, antes de un subproceso llama a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama a [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el `ReJITCompilationStarted` devolución de llamada para el subproceso A. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) tenía no se han recibido por el generador de perfiles. Sin embargo, en este caso, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
- [JITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
