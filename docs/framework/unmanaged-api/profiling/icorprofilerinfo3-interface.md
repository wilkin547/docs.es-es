---
title: ICorProfilerInfo3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3
helpviewer_keywords:
- ICorProfilerInfo3 interface [.NET Framework profiling]
ms.assetid: 044a262f-0fa7-485d-b0c1-64cdc359c654
topic_type:
- apiref
ms.openlocfilehash: c42b0df90dc690997bbc5414e977d6830dc5f3b8
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449630"
---
# <a name="icorprofilerinfo3-interface"></a>ICorProfilerInfo3 (Interfaz)
Proporciona métodos que los generadores de perfiles de código usan para comunicarse con Common Language Runtime (CLR) para controlar la supervisión de eventos y para solicitar información. La interfaz de `ICorProfilerInfo3` es una extensión de la interfaz [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) . Proporciona nuevos métodos que se admiten en el .NET Framework 4 y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumJITedFunctions (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)|Devuelve un enumerador para todas las funciones previamente compiladas con JIT.|  
|[EnumModules (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)|Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.|  
|[GetAppDomainsContainingModule (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.|  
|[GetFunctionEnter3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)|Proporciona el marco de pila y la información de los argumentos de la función que se está informando al generador de perfiles mediante la función [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) ; solo se puede llamar durante la devolución de llamada de `FunctionEnter3WithInfo`.|  
|[GetFunctionLeave3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)|Proporciona el marco de pila y el valor devuelto de la función que la función [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) devuelve al generador de perfiles. solo se puede llamar durante la devolución de llamada de `FunctionLeave3WithInfo`.|  
|[GetFunctionTailcall3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)|Proporciona el marco de pila de la función que la función [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) está informando al generador de perfiles. solo se puede llamar durante la devolución de llamada de `FunctionTailcall3WithInfo`.|  
|[GetModuleInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)|Dado un identificador de módulo, devuelve el nombre de archivo del módulo, el identificador del ensamblado primario del módulo y una máscara de bits que describe las propiedades del módulo.|  
|[GetRuntimeInformation (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getruntimeinformation-method.md)|Proporciona información sobre la versión del CLR cuyo perfil se está generando.|  
|[GetStringLayout2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[GetThreadStaticAddress2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getthreadstaticaddress2-method.md)|Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.|  
|[RequestProfilerDetach (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)|Indica al CLR que desasocie el generador de perfiles.|  
|[SetEnterLeaveFunctionHooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) .|  
|[SetEnterLeaveFunctionHooks3WithInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) de las funciones administradas.|  
|[SetFunctionIDMapper2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)|Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende [ICorProfilerInfo:: setfunctionidmapper (](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro que los perfiles pueden utilizar para eliminar la ambigüedad entre los tiempos de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR implementa los métodos de la interfaz `ICorProfilerInfo3` usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 El CLR pasa una interfaz `ICorProfilerInfo3` a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles del método [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) o [ICorProfilerCallback3:: InitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) . Después, un generador de perfiles de código puede llamar a los métodos `ICorProfilerInfo3` para obtener información acerca del código administrado que se está ejecutando bajo el control del CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
