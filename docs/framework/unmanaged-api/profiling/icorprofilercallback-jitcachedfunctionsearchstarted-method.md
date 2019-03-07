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
ms.openlocfilehash: 526059e0895604d18025e8ad2fd037690243ff59
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57503078"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)
Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se ha compilado previamente con el generador de imágenes nativas (NGen.exe).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 [in] El identificador de la función para el que se realiza la búsqueda.  
  
 `pbUseCachedFunction`  
 [out] `true` si el motor de ejecución debe usar la versión en caché de una función (si está disponible); de lo contrario `false`. Si el valor es `false`, el motor de ejecución del compilador JIT compila la función en lugar de usar una versión que no está compilado JIT.  
  
## <a name="remarks"></a>Comentarios  
 En .NET Framework versión 2.0, el `JITCachedFunctionSearchStarted` y [JITCachedFunctionSearchFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) no se realizarán las devoluciones de llamada para todas las funciones en imágenes NGen normales. Solo las imágenes de NGen optimizadas para un perfil generará las devoluciones de llamada para todas las funciones en la imagen. Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas por el generador de perfiles sólo si pretende usar estas devoluciones de llamada para forzar una función a ser compilado just-in-time (JIT). En caso contrario, el generador de perfiles debe usar una estrategia lenta para recopilar información de la función.  
  
 Los generadores de perfiles deben admitir casos donde varios subprocesos de una aplicación para llamar al mismo método simultáneamente. Por ejemplo, un subproceso a llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *pbUseCachedFunction*en FALSE para forzar una compilación JIT. Subproceso que llama una, a continuación, [JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) y [ICorProfilerCallback:: JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Ahora subproceso B llama `JITCachedFunctionSearchStarted` para la misma función. Aunque el generador de perfiles se ha indicado su intención a la compilación JIT la función, el generador de perfiles recibe la segunda devolución de llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles ha respondido a la llamada del subproceso a `JITCachedFunctionSearchStarted`. El orden en que los subprocesos realicen llamadas depende de cómo se programan los subprocesos.  
  
 Cuando el generador de perfiles recibe las devoluciones de llamada duplicados, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicados. Es decir, cuando `JITCachedFunctionSearchStarted` se llama varias veces con el mismo `functionId` valor, el generador de perfiles debe responder el mismo cada vez.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
