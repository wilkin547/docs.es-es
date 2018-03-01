---
title: ICorProfilerInfo3 (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3c0251e4e4934ac632eb977f2f1505fe6610b31b
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo3-interface"></a>ICorProfilerInfo3 (Interfaz)
Proporciona métodos que los generadores de perfiles de código usan para comunicarse con Common Language Runtime (CLR) para controlar la supervisión de eventos y para solicitar información. El `ICorProfilerInfo3` interfaz es una extensión de la [ICorProfilerInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md) interfaz. Proporciona nuevos métodos admitidos en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[EnumJITedFunctions (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enumjitedfunctions-method.md)|Devuelve un enumerador para todas las funciones previamente compiladas con JIT.|  
|[EnumModules (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)|Devuelve un enumerador que proporciona métodos para iterar secuencialmente por una colección de módulos administrados cargados en la aplicación.|  
|[GetAppDomainsContainingModule (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|Obtiene los identificadores de los dominios de aplicación en los que se cargó el módulo especificado.|  
|[GetFunctionEnter3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionenter3info-method.md)|Proporciona la información de pila de marco y los argumentos de la función que se va a notificar al generador de perfiles la [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md) función; se puede llamar solo durante la `FunctionEnter3WithInfo` devolución de llamada.|  
|[GetFunctionLeave3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctionleave3info-method.md)|Proporciona el marco de pila y el valor devuelto de la función que se va a notificar al generador de perfiles la [función FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) función; se puede llamar solo durante la `FunctionLeave3WithInfo` devolución de llamada.|  
|[GetFunctionTailcall3Info (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getfunctiontailcall3info-method.md)|Proporciona el marco de pila de la función que se va a notificar al generador de perfiles la [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) función; se puede llamar solo durante la `FunctionTailcall3WithInfo` devolución de llamada.|  
|[GetModuleInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getmoduleinfo2-method.md)|Dado un identificador de módulo, devuelve el nombre de archivo del módulo, el identificador del ensamblado primario del módulo y una máscara de bits que describe las propiedades del módulo.|  
|[GetRuntimeInformation (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getruntimeinformation-method.md)|Proporciona información sobre la versión del CLR cuyo perfil se está generando.|  
|[GetStringLayout2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getstringlayout2-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[GetThreadStaticAddress2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getthreadstaticaddress2-method.md)|Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso y del dominio de aplicación especificados.|  
|[RequestProfilerDetach (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)|Indica al CLR que desasocie el generador de perfiles.|  
|[SetEnterLeaveFunctionHooks3 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)|Especifica las funciones implementadas por el generador de perfiles que se llamará en el [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) funciones.|  
|[SetEnterLeaveFunctionHooks3WithInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)|Especifica las funciones implementadas por el generador de perfiles que se llamará en el [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) enlaces de funciones administradas.|  
|[SetFunctionIDMapper2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setfunctionidmapper2-method.md)|Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles. Este método extiende [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) con un parámetro que los generadores de perfiles pueden usar para eliminar la ambigüedad entre los Runtime.|  
  
## <a name="remarks"></a>Comentarios  
 El CLR implementa los métodos de la interfaz `ICorProfilerInfo3` usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 CLR pasa una `ICorProfilerInfo3` interfaz a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles de la [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) o [ICorProfilerCallback3::I nitializeForAttach](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md) método. Después, un generador de perfiles de código puede llamar a los métodos `ICorProfilerInfo3` para obtener información acerca del código administrado que se está ejecutando bajo el control del CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
