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
ms.openlocfilehash: 4b75eebd8d9bf439a0317521a61c06ece3745be0
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075326"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted (Método)
Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para el que se está iniciando la compilación.  
  
 `fIsSafeToBlock`  
 [in] Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución. El valor es `true` Si bloqueo puede provocar el tiempo de ejecución esperar el subproceso de llamada devolver desde esta devolución de llamada; de lo contrario, `false`.  
  
 Aunque un valor de `true` no dañarán el tiempo de ejecución, pueden sesgar los resultados de la generación de perfiles.  
  
## <a name="remarks"></a>Comentarios  
 Es posible recibir más de un par de `JITCompilationStarted` y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md) llama para cada función debido al modo en el tiempo de ejecución controla los constructores de clase. Por ejemplo, el tiempo de ejecución se inicia la compilación JIT del método A, pero el constructor de la clase B debe ejecutarse. Por lo tanto, el tiempo de ejecución JIT compila el constructor de clase B y lo ejecuta. Mientras se ejecuta el constructor, realiza una llamada al método A, que hace que el método A volver a estar compilado JIT. En este escenario, se detiene la primera compilación JIT del método. Sin embargo, se notifica tanto a la compilación JIT del método A los intentos con eventos de compilación JIT. Si el generador de perfiles se va a reemplazar el código de lenguaje intermedio (MSIL) de Microsoft para un método mediante una llamada a la [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método, debe hacerlo para ambos `JITCompilationStarted` eventos, pero se puede usar el mismo bloque MSIL para ambos.  
  
 Los generadores de perfiles deben admitir la secuencia de devoluciones de llamada JIT en casos donde dos subprocesos están realizando simultáneamente las devoluciones de llamada. Por ejemplo, un subproceso a llama a `JITCompilationStarted`. Sin embargo, antes de un subproceso llama a `JITCompilationFinished`, el subproceso B llama a [ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función desde el subproceso del `JITCompilationStarted` devolución de llamada. Podría parecer que el identificador de función no debe encontrarse aún válido porque una llamada a `JITCompilationFinished` tenía no se han recibido por el generador de perfiles. Sin embargo, en un caso como éste, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [Método JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)
