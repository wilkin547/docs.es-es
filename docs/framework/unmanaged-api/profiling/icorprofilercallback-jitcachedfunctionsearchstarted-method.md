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
ms.openlocfilehash: 5d3fe6691a2d9989de002bad09c2e8f66a094f56
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448433"
---
# <a name="icorprofilercallbackjitcachedfunctionsearchstarted-method"></a>ICorProfilerCallback::JITCachedFunctionSearchStarted (Método)
Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló previamente mediante el generador de imágenes nativas (NGen. exe).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT JITCachedFunctionSearchStarted(  
    [in]  FunctionID functionId,  
    [out] BOOL *pbUseCachedFunction);  
```  
  
## <a name="parameters"></a>Parámetros  
 `functionId`  
 de IDENTIFICADOR de la función para la que se realiza la búsqueda.  
  
 `pbUseCachedFunction`  
 [out] `true` si el motor de ejecución debe utilizar la versión almacenada en caché de una función (si está disponible); de lo contrario `false`. Si el valor es `false`, el motor de ejecución compila la función JIT en lugar de usar una versión que no está compilada JIT.  
  
## <a name="remarks"></a>Comentarios  
 En la versión .NET Framework 2,0, las devoluciones de llamada del método `JITCachedFunctionSearchStarted` y [ICorProfilerCallback:: JITCachedFunctionSearchFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md) no se realizarán para todas las funciones de las imágenes Ngen normales. Solo las imágenes de NGen optimizadas para un perfil generarán devoluciones de llamada para todas las funciones de la imagen. Sin embargo, debido a la sobrecarga adicional, un generador de perfiles debe solicitar imágenes NGen optimizadas para el generador de perfiles solo si pretende utilizar estas devoluciones de llamada para forzar que una función se compile Just-in-Time (JIT). De lo contrario, el generador de perfiles debe usar una estrategia diferida para recopilar información de la función.  
  
 Los perfiles deben admitir casos en los que varios subprocesos de una aplicación de la que se ha performado estén llamando al mismo método simultáneamente. Por ejemplo, el subproceso A llama a `JITCachedFunctionSearchStarted` y el generador de perfiles responde estableciendo *pbUseCachedFunction*en false para forzar la compilación JIT. Después, el subproceso a llama a [ICorProfilerCallback:: JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md) e [ICorProfilerCallback:: JITCompilationFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md).  
  
 Ahora el subproceso B llama a `JITCachedFunctionSearchStarted` para la misma función. Aunque el generador de perfiles ha indicado su intención de compilar la función JIT, el generador de perfiles recibe la segunda devolución de llamada porque el subproceso B envía la devolución de llamada antes de que el generador de perfiles haya respondido a la llamada de subproceso a `JITCachedFunctionSearchStarted`. El orden en que los subprocesos realizan llamadas depende de cómo estén programados los subprocesos.  
  
 Cuando el generador de perfiles recibe devoluciones de llamada duplicadas, debe establecer el valor al que hace referencia `pbUseCachedFunction` en el mismo valor para todas las devoluciones de llamada duplicadas. Es decir, cuando se llama a `JITCachedFunctionSearchStarted` varias veces con el mismo valor `functionId`, el generador de perfiles debe responder cada vez.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
