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
ms.openlocfilehash: c3642154ba5f9798f59ca8fc49cb848d7e2f73c7
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862235"
---
# <a name="icorprofilerinfo3-interface"></a>ICorProfilerInfo3 (Interfaz)
Proporciona métodos que los generadores de perfiles de código usan para comunicarse con Common Language Runtime (CLR) para controlar la supervisión de eventos y para solicitar información. La interfaz de `ICorProfilerInfo3` es una extensión de la interfaz [ICorProfilerInfo2](icorprofilerinfo2-interface.md) . Proporciona nuevos métodos que se admiten en el .NET Framework 4 y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumJITedFunctions (método)](icorprofilerinfo3-enumjitedfunctions-method.md)|Devuelve un enumerador para todas las funciones previamente compiladas con JIT.|  
|[EnumModules (método)](icorprofilerinfo3-enummodules-method.md)|Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.|  
|[GetAppDomainsContainingModule (método)](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Obtiene los identificadores de los dominios de la aplicación en la que se cargó el módulo especificado.|  
|[GetFunctionEnter3Info (método)](icorprofilerinfo3-getfunctionenter3info-method.md)|Proporciona el marco de pila y la información de los argumentos de la función que se está informando al generador de perfiles mediante la función [FunctionEnter3WithInfo](functionenter3withinfo-function.md) ; solo se puede llamar durante la devolución de llamada de `FunctionEnter3WithInfo`.|  
|[GetFunctionLeave3Info (método)](icorprofilerinfo3-getfunctionleave3info-method.md)|Proporciona el marco de pila y el valor devuelto de la función que la función [FunctionLeave3WithInfo](functionleave3withinfo-function.md) devuelve al generador de perfiles. solo se puede llamar durante la devolución de llamada de `FunctionLeave3WithInfo`.|  
|[GetFunctionTailcall3Info (método)](icorprofilerinfo3-getfunctiontailcall3info-method.md)|Proporciona el marco de pila de la función que la función [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) está informando al generador de perfiles. solo se puede llamar durante la devolución de llamada de `FunctionTailcall3WithInfo`.|  
|[GetModuleInfo2 (método)](icorprofilerinfo3-getmoduleinfo2-method.md)|Dado un identificador de módulo, devuelve el nombre de archivo del módulo, el identificador del ensamblado primario del módulo y una máscara de bits que describe las propiedades del módulo.|  
|[GetRuntimeInformation (método)](icorprofilerinfo3-getruntimeinformation-method.md)|Proporciona información sobre la versión del CLR cuyo perfil se está generando.|  
|[GetStringLayout2 (método)](icorprofilerinfo3-getstringlayout2-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[GetThreadStaticAddress2 (método)](icorprofilerinfo3-getthreadstaticaddress2-method.md)|Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.|  
|[RequestProfilerDetach (método)](icorprofilerinfo3-requestprofilerdetach-method.md)|Indica al CLR que desasocie el generador de perfiles.|  
|[SetEnterLeaveFunctionHooks3 (método)](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) .|  
|[SetEnterLeaveFunctionHooks3WithInfo (método)](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de las funciones administradas.|  
|[SetFunctionIDMapper2 (método)](icorprofilerinfo3-setfunctionidmapper2-method.md)|Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro que los perfiles pueden utilizar para eliminar la ambigüedad entre los tiempos de ejecución.|  
  
## <a name="remarks"></a>Notas  
 El CLR implementa los métodos de la interfaz `ICorProfilerInfo3` usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 El CLR pasa una interfaz `ICorProfilerInfo3` a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles del método [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) o [ICorProfilerCallback3:: InitializeForAttach](icorprofilercallback3-initializeforattach-method.md) . Después, un generador de perfiles de código puede llamar a los métodos `ICorProfilerInfo3` para obtener información acerca del código administrado que se está ejecutando bajo el control del CLR.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
