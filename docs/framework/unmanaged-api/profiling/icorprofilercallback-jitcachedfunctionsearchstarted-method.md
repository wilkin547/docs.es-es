---
title: ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.JITCachedFunctionSearchStarted
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::JITCachedFunctionSearchStarted
helpviewer_keywords:
- JITCachedFunctionSearchStarted method [.NET Framework profiling]
- ICorProfilerCallback::JITCachedFunctionSearchStarted method [.NET Framework profiling]
ms.assetid: 5cba642c-0d80-48ee-889d-198c5044d821
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6d97b40412b6999000a601b72904a03edf2acd08
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)
Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló anteriormente con el generador de imágenes nativas (NGen.exe).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para la que se realiza la búsqueda.  
  
 `pbUseCachedFunction`  
 [out] `true` si el motor de ejecución debe usar la versión en caché de una función (si está disponible); en caso contrario `false`. Si el valor es `false`, el motor de ejecución del compilador JIT compila la función en lugar de usar una versión que no está compilado JIT.  
  
## <a name="remarks"></a>Comentarios  
 En .NET Framework versión 2.0, el `JITCachedFunctionSearchStarted` y [ICorProfilerCallback:: JITCachedFunctionSearchFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) no se realizarán las devoluciones de llamada para todas las funciones en imágenes NGen normales. Sólo las imágenes NGen optimizadas para un perfil generará las devoluciones de llamada para todas las funciones en la imagen. Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas de generador de perfiles solo si tiene intención de utilizar estas devoluciones de llamada para forzar una función para ser compilado just-in-time (JIT). En caso contrario, el generador de perfiles debe utilizar una estrategia lenta para recopilar información de la función.  
  
 Los generadores de perfiles deben admitir casos en los que varios subprocesos de una aplicación de perfiles llamen al mismo método simultáneamente. Por ejemplo, un subproceso llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *pbUseCachedFunction*en FALSE para forzar una compilación JIT. Subproceso llama a un then [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Ahora subproceso B llama `JITCachedFunctionSearchStarted` para la misma función. Aunque el generador de perfiles se ha indicado su intención de la función de compilación JIT, el generador de perfiles recibe la segunda llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles ha respondido a la llamada del subproceso a `JITCachedFunctionSearchStarted`. El orden en la que los subprocesos realizan llamadas depende de cómo se programan los subprocesos.  
  
 Cuando el generador de perfiles recibe las devoluciones de llamada duplicados, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicados. Es decir, cuando `JITCachedFunctionSearchStarted` se llama varias veces con el mismo `functionId` valor, el generador de perfiles debe responder lo mismo cada vez.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
