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
ms.openlocfilehash: 7ce100a68a3e2b8963ed14bbf044fa9ba11d629f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725526"
---
# <a name="icorprofilercallbackjitcompilationstarted-method"></a>ICorProfilerCallback::JITCompilationStarted (Método)

Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a compilar una función.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITCompilationStarted(  
    [in] FunctionID functionId,  
    [in] BOOL       fIsSafeToBlock);  
```  
  
## <a name="parameters"></a>Parámetros  

 `functionId`  
 de IDENTIFICADOR de la función para la que se está iniciando la compilación.  
  
 `fIsSafeToBlock`  
 de Un valor que indica al generador de perfiles si el bloqueo afectará al funcionamiento del tiempo de ejecución. El valor es `true` si el bloqueo puede hacer que el tiempo de ejecución espere a que el subproceso que realiza la llamada devuelva de esta devolución de llamada; de lo contrario, `false` .  
  
 Aunque un valor de `true` no dañará el tiempo de ejecución, puede sesgar los resultados de la generación de perfiles.  
  
## <a name="remarks"></a>Comentarios  

 Es posible recibir más de un par de `JITCompilationStarted` llamadas y [ICorProfilerCallback:: JITCompilationFinished (](icorprofilercallback-jitcompilationfinished-method.md) para cada función debido al modo en que el Runtime controla los constructores de clase. Por ejemplo, el tiempo de ejecución comienza a compilar de forma JIT el método A, pero es necesario ejecutar el constructor de clase de la clase B. Por lo tanto, el Runtime compila el constructor para la clase B y lo ejecuta. Mientras se ejecuta el constructor, realiza una llamada al método a, lo que hace que el método a se vuelva a compilar JIT. En este escenario, se detiene la primera compilación JIT del método A. Sin embargo, ambos intentos de compilar de forma JIT a se registran con eventos de compilación JIT. Si el generador de perfiles va a reemplazar el código del lenguaje intermedio de Microsoft (MSIL) para el método A llamando al método [ICorProfilerInfo:: SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) , debe hacerlo para ambos `JITCompilationStarted` eventos, pero puede usar el mismo bloque MSIL para ambos.  
  
 Los perfiles de servicio deben admitir la secuencia de devoluciones de llamada JIT en los casos en que dos subprocesos realizan simultáneamente devoluciones de llamada. Por ejemplo, el subproceso A llama a `JITCompilationStarted` . Sin embargo, antes de que el subproceso A llame a `JITCompilationFinished` , el subproceso B llama a [ICorProfilerCallback:: exceptionsearchfunctionenter (](icorprofilercallback-exceptionsearchfunctionenter-method.md) con el identificador de función de la devolución de llamada del subproceso a `JITCompilationStarted` . Podría parecer que el ID. de función no debería ser válido todavía porque `JITCompilationFinished` el generador de perfiles no ha recibido todavía una llamada a. Sin embargo, en un caso como este, el identificador de función es válido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)
