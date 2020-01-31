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
ms.openlocfilehash: 81d11c87c9bc970dd5b5c9010023610cea7c0e72
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865199"
---
# <a name="icorprofilercallback4rejitcompilationstarted-method"></a>ICorProfilerCallback4::ReJITCompilationStarted (Método)
Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ReJITCompilationStarted(   
    [in] FunctionID functionId,  
    [in] ReJITID    rejitId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parameters  
 `functionId`  
 de IDENTIFICADOR de la función que el compilador JIT ha empezado a volver a compilar.  
  
 `rejitId`  
 de IDENTIFICADOR de recompilación de la nueva versión de la función.  
  
 `fIsSafeToBlock`  
 [in] `true` para indicar que el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; `false` para indicar que el bloqueo no afectará al funcionamiento del tiempo de ejecución. Un valor de `true` no perjudica al tiempo de ejecución, pero puede afectar a los resultados de la generación de perfiles.  
  
## <a name="remarks"></a>Notas  
 Es posible recibir más de un par de llamadas a métodos `ReJITCompilationStarted` y [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) para cada función debido a la manera en que el tiempo de ejecución controla los constructores de clase. Por ejemplo, el tiempo de ejecución comienza a volver a compilar el método A, pero es necesario ejecutar el constructor de clase de la clase B. Por consiguiente, el tiempo de ejecución vuelve a compilar el constructor de la clase B y lo ejecuta. Mientras se ejecuta el constructor, realiza una llamada al método a, que hace que se vuelva a compilar el método a. En este escenario, se detiene la primera recompilación del método A. Sin embargo, ambos intentos de volver a compilar el método A se registran con eventos de recompilación JIT.  
  
 Los profileres deben admitir la secuencia de devoluciones de llamada de recompilación JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada. Por ejemplo, el subproceso A llama a `ReJITCompilationStarted`; sin embargo, antes de que el subproceso A llame a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md), el subproceso B llama a [ICorProfilerCallback:: EXCEPTIONSEARCHFUNCTIONENTER (](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la devolución de llamada `ReJITCompilationStarted` para el subproceso A. Podría parecer que el identificador de función no debería ser válido todavía porque el generador de perfiles no ha recibido todavía una llamada a [rejitcompilationfinished (](icorprofilercallback4-rejitcompilationfinished-method.md) . Sin embargo, en este caso, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback4 (interfaz)](icorprofilercallback4-interface.md)
- [JITCompilationFinished (método)](icorprofilercallback-jitcompilationfinished-method.md)
- [ReJITCompilationFinished (método)](icorprofilercallback4-rejitcompilationfinished-method.md)
