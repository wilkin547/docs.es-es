---
title: ICorProfilerInfo (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo
helpviewer_keywords:
- ICorProfilerInfo interface [.NET Framework profiling]
ms.assetid: eb4e4ce0-06e7-4469-bbc4-edc2eb5da4b1
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 936bcd59cd21a4fb4c101febcefd26f3b1fdafa1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54665583"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo (Interfaz)
Proporciona métodos para su uso por los generadores de perfiles de código para comunicarse con common language runtime (CLR) para controlar la supervisión de eventos y solicitar información.  
  
> [!NOTE]
>  Cada método en el `ICorProfilerInfo` interfaz devuelve un valor HRESULT para indicar éxito o error. Para obtener una lista de posibles códigos de retorno, vea CorError.h.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[BeginInprocDebugging (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-begininprocdebugging-method.md)|Inicializa la compatibilidad con la depuración en proceso. Este método está obsoleto en .NET Framework versión 2.0.|  
|[EndInprocDebugging (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-endinprocdebugging-method.md)|Se cierra una sesión de depuración en proceso. Este método está obsoleto en .NET Framework versión 2.0.|  
|[ForceGC (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)|Fuerza la recolección que se produzca en el tiempo de ejecución.|  
|[GetAppDomainInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)|Obtiene información sobre el dominio de aplicación especificado.|  
|[GetAssemblyInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getassemblyinfo-method.md)|Obtiene información sobre el ensamblado especificado.|  
|[GetClassFromObject (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromobject-method.md)|Obtiene el `ClassID` de un<br /><br /> objeto, dada su `ObjectID`.|  
|[GetClassFromToken (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)|Obtiene el identificador de la clase, dado el token de metadatos. Este método está obsoleto en .NET Framework versión 2.0. Use la [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) método en su lugar.|  
|[GetClassIDInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)|Obtiene el módulo primario y el token de metadatos para la clase especificada.|  
|[GetCodeInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)|Obtiene la extensión del código nativo asociado al identificador de función especificado. Este método está obsoleto. Use la [ICorProfilerInfo2:: Getcodeinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md) método en su lugar.|  
|[GetCurrentThreadID (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)|Obtiene el identificador del subproceso actual, si es un subproceso administrado.|  
|[GetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)|Obtiene las categorías de eventos actual para el que el generador de perfiles quiere recibir notificaciones de eventos de CLR.|  
|[GetFunctionFromIP (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)|Asigna un puntero de instrucción de código administrado a un `FunctionID`.|  
|[GetFunctionFromToken (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromtoken-method.md)|Obtiene el identificador de una función. Este método está obsoleto en .NET Framework versión 2.0. Use la [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) método en su lugar.|  
|[GetFunctionInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)|Obtiene la clase primaria y los metadatos de token para la función especificada.|  
|[GetHandleFromThread (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gethandlefromthread-method.md)|El identificador de un subproceso se asigna a un identificador de subproceso de Win32.|  
|[GetILFunctionBody (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbody-method.md)|Obtiene un puntero al cuerpo de un método en el código de lenguaje intermedio (MSIL) de Microsoft, comenzando por su encabezado.|  
|[GetILFunctionBodyAllocator (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)|Obtiene una interfaz que proporciona un método para asignar memoria que se usará para intercambiar el cuerpo de un método en código MSIL.|  
|[GetILToNativeMapping (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getiltonativemapping-method.md)|Obtiene una asignación de desplazamientos de MSIL a desplazamientos nativos para el código incluido en la función especificada.|  
|[GetInprocInspectionInterface (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectioninterface-method.md)|Obtiene un objeto que se puede consultar para una ICorDebugProcess (interfaz). Este método está obsoleto en .NET Framework versión 2.0.|  
|[GetInprocInspectionIThisThread (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getinprocinspectionithisthread-method.md)|Obtiene un objeto que se puede consultar para ICorDebugThread (interfaz). Este método está obsoleto en .NET Framework versión 2.0.|  
|[GetModuleInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)|A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.|  
|[GetModuleMetaData (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md)|Obtiene una instancia de la interfaz de metadatos que se asigna para el módulo especificado.|  
|[GetObjectSize (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md)|Obtiene el tamaño de un objeto especificado.|  
|[GetThreadContext (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)|Obtiene la identidad de contexto actualmente asociada con el subproceso especificado.|  
|[GetThreadInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadinfo-method.md)|Obtiene la identidad del subproceso Win32 actual para el subproceso especificado.|  
|[GetTokenAndMetadataFromFunction (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Obtiene el token de metadatos y una instancia de la interfaz de metadatos que puede utilizarse con el token para la función especificada.|  
|[IsArrayClass (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)|Determina si la clase especificada es una clase de matriz.|  
|[SetEnterLeaveFunctionHooks (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md)|Especifica las funciones implementadas por el generador de perfiles que se llamará en "enter", "salir" y "llamada de cola" enlaces de funciones administradas.|  
|[SetEventMask (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)|Establece un valor que especifica los tipos de eventos para el que el generador de perfiles quiere recibir una notificación de CLR.|  
|[SetFunctionIDMapper (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)|Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.|  
|[SetFunctionReJIT (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionrejit-method.md)|Sin implementar. No utilizar.|  
|[SetILFunctionBody (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)|Reemplaza el cuerpo de la función especificada en el módulo especificado.|  
|[SetILInstrumentedCodeMap (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)|Especifica cómo se asignan los desplazamientos de MSIL original de la función especificada a los desplazamientos de MSIL de modificación del generador de perfiles de la función nueva.|  
  
## <a name="remarks"></a>Comentarios  
 Un generador de perfiles llama a un método el `ICorProfilerInfo` interfaz para comunicarse con CLR para controlar la supervisión de eventos y solicitar información.  
  
 Los métodos de la `ICorProfilerInfo` interfaz se implementa mediante el CLR utilizando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de posibles códigos de retorno, vea CorError.h.  
  
 El CLR pasa, a través de la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md), un `ICorProfilerInfo` interfaz cada generador de perfiles de código durante la inicialización. Un generador de perfiles de código, a continuación, puede llamar a métodos de la `ICorProfilerInfo` interfaz para obtener información sobre el código administrado que se está ejecutando bajo el control de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
