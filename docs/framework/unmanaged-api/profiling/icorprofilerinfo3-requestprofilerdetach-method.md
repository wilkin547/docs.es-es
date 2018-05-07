---
title: ICorProfilerInfo3::RequestProfilerDetach (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.RequestProfilerDetach Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::RequestProfilerDetach
helpviewer_keywords:
- RequestProfilerDetach method [.NET Framework profiling]
- ICorProfilerInfo3::RequestProfilerDetach method [.NET Framework profiling]
ms.assetid: ea102e62-0454-4477-bcf3-126773acd184
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: e69a15d70b8f1b9e271571be92f1f6717a9f196c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>ICorProfilerInfo3::RequestProfilerDetach (Método)
Indica al CLR que desasocie el generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwExpectedCompletionMilliseconds`  
 [in] Período de tiempo, en milisegundos, que Common Language Runtime (CLR) debe esperar antes de comprobar si es seguro descargar el generador de perfiles.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La solicitud de desasociación es válida y el procedimiento de desasociación continuará ahora en otro subproceso. Una vez completada totalmente la desasociación, se genera un evento `ProfilerDetachSucceeded`.|  
|E_ CORPROF_E_CALLBACK3_REQUIRED|Error en el generador de perfiles una [IUnknown:: QueryInterface](http://go.microsoft.com/fwlink/?LinkID=144867) intento para la [ICorProfilerCallback3](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md) interfaz, que debe implementar para admitir la operación de separación. La desasociación no se intentó.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|No se puede realizar la desasociación porque el generador de perfiles establece marcas inmutables en el inicio. No se intentó la desasociación; el generador de perfiles sigue totalmente asociado.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|Desasociación es imposible porque el generador de perfiles usó código del lenguaje intermedio (MSIL) de Microsoft o insertadas `enter` / `leave` enlaces. No se intentó la desasociación; el generador de perfiles sigue totalmente asociado.<br /><br /> **Tenga en cuenta** MSIL instrumentado es código código proporcionado por el generador de perfiles mediante el [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md) método.|  
|CORPROF_E_RUNTIME_UNINITIALIZED|El tiempo de ejecución no se ha inicializado aún en la aplicación administrada. (Es decir, el tiempo de ejecución no se ha cargado completamente). Este código de error se puede devolver cuando se solicita la desasociación dentro de devolución de llamada del generador de perfiles [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) método.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|Se llamó a `RequestProfilerDetach` en un momento no permitido. Esto ocurre si se llama al método en un subproceso administrado pero no desde un [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) método o desde una [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) método que no tolera una recolección. Para obtener más información, consulte [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Comentarios  
 Durante el procedimiento de desasociación, el subproceso de desasociación (el subproceso creado específicamente para desasociar el generador de perfiles) comprueba ocasionalmente si todos los subprocesos han salido del código del generador de perfiles. El generador de perfiles debe proporcionar una estimación de cuánto tiempo deben tardar usando para ello el parámetro `dwExpectedCompletionMilliseconds`. Un valor adecuado es la cantidad de tiempo típica que el generador de perfiles invierte dentro de un método `ICorProfilerCallback*` cualquiera; este valor no debe ser menor que la mitad de la cantidad máxima de tiempo que el generador de perfiles espera invertir.  
  
 El subproceso de desasociación usa `dwExpectedCompletionMilliseconds` para decidir cuánto tiempo debe esperar antes de comprobar si el código de devolución de llamada del generador de perfiles se ha extraído de todas las pilas. Aunque los detalles del siguiente algoritmo pueden cambiar en futuras versiones del CLR, ilustra una forma de usar `dwExpectedCompletionMilliseconds` para determinar cuándo es seguro descargar el generador de perfiles. El subproceso de desasociación espera primero `dwExpectedCompletionMilliseconds` milisegundos. Si, después de volver del estado de suspensión, el CLR descubre que el código de devolución de llamada del generador de perfiles está presente, el subproceso de desasociación pone suspensión de nuevo, esta vez para dos veces `dwExpectedCompletionMilliseconds` milisegundos. Si después de volver de este segundo estado de suspensión, el subproceso de desasociación descubre que aún hay código de devolución de llamada del generador de perfiles, entra en suspensión durante 10 minutos antes de volver a comprobar. El subproceso de desasociación sigue realizando la comprobación cada 10 minutos.  
  
 Si el generador de perfiles especifica `dwExpectedCompletionMilliseconds` como 0 (cero), el CLR usa un valor predeterminado de 5000, lo que significa que realizará una comprobación después de 5 segundos, otra vez después de 10 segundos y, a partir de entonces, cada 10 minutos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
