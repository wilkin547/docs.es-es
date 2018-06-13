---
title: ICorProfilerCallback::JITCompilationStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCompilationStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCompilationStarted
helpviewer_keywords:
- JITCompilationStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCompilationStarted method [.NET Framework profiling]
ms.assetid: 31782b36-d311-4518-8f45-25f65385af5b
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fa1081afc77c8116d8858c187401555409b4dcd
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453986"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted (Método)
Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para la que se está iniciando la compilación.  
  
 `fIsSafeToBlock`  
 [in] Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución. El valor es `true` Si bloqueo puede hacer que el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; de lo contrario, `false`.  
  
 Aunque un valor de `true` no dañarán el tiempo de ejecución, se pueden falsear los resultados de la generación de perfiles.  
  
## <a name="remarks"></a>Comentarios  
 Es posible recibir más de un par de `JITCompilationStarted` y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) llama para cada función debido al modo en el tiempo de ejecución de los constructores de clases de identificadores. Por ejemplo, el tiempo de ejecución inicia la compilación JIT del método A, pero el constructor de la clase B es necesario ejecutar. Por lo tanto, el tiempo de ejecución de la compilación JIT del constructor de clase B y lo ejecuta. Cuando se está ejecutando el constructor, se hace una llamada a método A, que hace que el método A para volver a estar compilado JIT. En este escenario, se detiene la primera compilación JIT de un método. Sin embargo, los intentos de compilación JIT del método A se notifican con los eventos de compilación JIT. Si el generador de perfiles se va a reemplazar el código de lenguaje intermedio (MSIL) de Microsoft para un método mediante una llamada a la [ICorProfilerInfo:: SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, debe hacerlo para ambos `JITCompilationStarted` eventos, pero se puede utilizar el mismo bloque MSIL para ambos.  
  
 Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada JIT en casos donde dos subprocesos están realizando simultáneamente devoluciones de llamada. Por ejemplo, un subproceso llama a `JITCompilationStarted`. Sin embargo, antes de llamadas de subprocesos A `JITCompilationFinished`, el subproceso B llama [ICorProfilerCallback:: ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de subproceso del `JITCompilationStarted` devolución de llamada. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a `JITCompilationFinished` tenía no se han recibido por el generador de perfiles. Sin embargo, en un caso como este, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [JITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
