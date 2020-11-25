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
ms.openlocfilehash: 2ea39c94a5a0f3d24d4123d6405115ac75105e26
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721587"
---
# <a name="icorprofilerinfo3requestprofilerdetach-method"></a>ICorProfilerInfo3::RequestProfilerDetach (Método)

Indica al CLR que desasocie el generador de perfiles.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RequestProfilerDetach(  
   [in] DWORD    dwExpectedCompletionMilliseconds);  
```  
  
## <a name="parameters"></a>Parámetros  

 `dwExpectedCompletionMilliseconds`  
 [in] Período de tiempo, en milisegundos, que Common Language Runtime (CLR) debe esperar antes de comprobar si es seguro descargar el generador de perfiles.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|La solicitud de desasociación es válida y el procedimiento de desasociación continuará ahora en otro subproceso. Una vez completada totalmente la desasociación, se genera un evento `ProfilerDetachSucceeded`.|  
|E_CORPROF_E_CALLBACK3_REQUIRED|Error del generador de perfiles en un intento [IUnknown:: QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)) de la interfaz [ICorProfilerCallback3](icorprofilercallback3-interface.md) , que debe implementar para admitir la operación de desasociación. La desasociación no se intentó.|  
|CORPROF_E_IMMUTABLE_FLAGS_SET|No se puede realizar la desasociación porque el generador de perfiles establece marcas inmutables en el inicio. No se intentó la desasociación; el generador de perfiles sigue totalmente asociado.|  
|CORPROF_E_IRREVERSIBLE_INSTRUMENTATION_PRESENT|No es posible la desasociación porque el generador de perfiles usó código del lenguaje intermedio de Microsoft (MSIL) o enlaces insertados `enter` / `leave` . No se intentó la desasociación; el generador de perfiles sigue totalmente asociado.<br /><br /> **Nota:** MSIL instrumentado es el código que proporciona el generador de perfiles mediante el método [SetILFunctionBody (](icorprofilerinfo-setilfunctionbody-method.md) .|  
|CORPROF_E_RUNTIME_UNINITIALIZED|El tiempo de ejecución no se ha inicializado aún en la aplicación administrada. (Es decir, el tiempo de ejecución no se ha cargado completamente). Este código de error se puede devolver cuando se solicita la desasociación dentro del método [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) de la devolución de llamada del generador de perfiles.|  
|CORPROF_E_UNSUPPORTED_CALL_SEQUENCE|Se llamó a `RequestProfilerDetach` en un momento no permitido. Esto sucede si se llama al método en un subproceso administrado pero no desde dentro de un método [ICorProfilerCallback](icorprofilercallback-interface.md) o desde un método [ICorProfilerCallback](icorprofilercallback-interface.md) que no puede tolerar una recolección de elementos no utilizados. Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).|  
  
## <a name="remarks"></a>Comentarios  

 Durante el procedimiento de desasociación, el subproceso de desasociación (el subproceso creado específicamente para desasociar el generador de perfiles) comprueba ocasionalmente si todos los subprocesos han salido del código del generador de perfiles. El generador de perfiles debe proporcionar una estimación de cuánto tiempo deben tardar usando para ello el parámetro `dwExpectedCompletionMilliseconds`. Un valor adecuado es la cantidad de tiempo típica que el generador de perfiles invierte dentro de un método `ICorProfilerCallback*` cualquiera; este valor no debe ser menor que la mitad de la cantidad máxima de tiempo que el generador de perfiles espera invertir.  
  
 El subproceso de desasociación usa `dwExpectedCompletionMilliseconds` para decidir cuánto tiempo debe esperar antes de comprobar si el código de devolución de llamada del generador de perfiles se ha extraído de todas las pilas. Aunque los detalles del siguiente algoritmo pueden cambiar en futuras versiones del CLR, ilustra una forma de usar `dwExpectedCompletionMilliseconds` para determinar cuándo es seguro descargar el generador de perfiles. El subproceso de desasociación espera primero `dwExpectedCompletionMilliseconds` milisegundos. Si, después de volver de la suspensión, el CLR encuentra que el código de devolución de llamada del generador de perfiles todavía está presente, el subproceso de desasociación se vuelve a suspender, esta vez para dos veces `dwExpectedCompletionMilliseconds` milisegundos. Si después de volver de este segundo estado de suspensión, el subproceso de desasociación descubre que aún hay código de devolución de llamada del generador de perfiles, entra en suspensión durante 10 minutos antes de volver a comprobar. El subproceso de desasociación sigue realizando la comprobación cada 10 minutos.  
  
 Si el generador de perfiles especifica `dwExpectedCompletionMilliseconds` como 0 (cero), el CLR usa un valor predeterminado de 5000, lo que significa que realizará una comprobación después de 5 segundos, otra vez después de 10 segundos y, a partir de entonces, cada 10 minutos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorProfilerInfo3 (Interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
