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
ms.openlocfilehash: d3e21d42340378c576bfc65750fba26a257b82cb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted (Método)
Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) para volver a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función que se ha iniciado el compilador JIT para volver a compilar.  
  
 `rejitId`  
 [in] El identificador de la recompilación de la nueva versión de la función.  
  
 `fIsSafeToBlock`  
 [in] `true` para indicar que el bloqueo puede causar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución. Un valor de `true` no dañar el tiempo de ejecución, pero puede afectar a los resultados de generación de perfiles.  
  
## <a name="remarks"></a>Comentarios  
 Es posible recibir más de un par de `ReJITCompilationStarted` y [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) método llama para cada función debido al modo en el tiempo de ejecución de los constructores de clases de identificadores. Por ejemplo, el tiempo de ejecución se inicia para volver a compilar un método, pero el constructor de la clase B es necesario ejecutar. Por lo tanto, el tiempo de ejecución vuelve a compilar el constructor de clase B y lo ejecuta. Cuando se está ejecutando el constructor, se hace una llamada a método A, que hace que el método A volver a compilar de nuevo. En este escenario, se detiene la primera recompilación de un método. Sin embargo, ambas intenta volver a compilar método notificado A son eventos de recompilación JIT.  
  
 Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada de recompilación JIT en casos donde dos subprocesos están realizando simultáneamente devoluciones de llamada. Por ejemplo, un subproceso llama a `ReJITCompilationStarted`; sin embargo, antes de llamadas de subprocesos A [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el `ReJITCompilationStarted` devolución de llamada para el subproceso A. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a [ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md) tenía no se han recibido por el generador de perfiles. Sin embargo, en este caso, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)  
 [JITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)  
 [ReJITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)
