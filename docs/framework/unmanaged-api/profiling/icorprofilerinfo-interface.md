---
description: 'Más información acerca de: ICorProfilerInfo (interfaz)'
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
ms.openlocfilehash: d1da0f41a7c7358b7f71c8d931fff723b3144cdd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737394"
---
# <a name="icorprofilerinfo-interface"></a>ICorProfilerInfo (Interfaz)

Proporciona métodos para que los profileres de código puedan usar para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de las solicitudes.  
  
> [!NOTE]
> Cada método de la `ICorProfilerInfo` interfaz devuelve un valor HRESULT que indica si se ha realizado correctamente o no. Vea CorError. h para obtener una lista de posibles códigos de retorno.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método BeginInprocDebugging](icorprofilerinfo-begininprocdebugging-method.md)|Inicializa la compatibilidad con la depuración en proceso. Este método está obsoleto en la .NET Framework versión 2,0.|  
|[Método EndInprocDebugging](icorprofilerinfo-endinprocdebugging-method.md)|Cierra una sesión de depuración en proceso. Este método está obsoleto en la .NET Framework versión 2,0.|  
|[Método ForceGC](icorprofilerinfo-forcegc-method.md)|Fuerza la recolección de elementos no utilizados en el tiempo de ejecución.|  
|[Método GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)|Obtiene información sobre el dominio de aplicación especificado.|  
|[Método GetAssemblyInfo](icorprofilerinfo-getassemblyinfo-method.md)|Obtiene información acerca del ensamblado especificado.|  
|[Método GetClassFromObject](icorprofilerinfo-getclassfromobject-method.md)|Obtiene el `ClassID` de un<br /><br /> objeto, dado su `ObjectID` .|  
|[Método GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)|Obtiene el identificador de la clase, dado el token de metadatos. Este método está obsoleto en la .NET Framework versión 2,0. Use en su lugar el método [ICorProfilerInfo2:: GetClassFromTokenAndTypeArgs (](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md) .|  
|[Método GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)|Obtiene el módulo primario y el token de metadatos para la clase especificada.|  
|[Método GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)|Obtiene la extensión del código nativo asociado al identificador de función especificado. Este método está obsoleto. Use en su lugar el método [ICorProfilerInfo2:: GetCodeInfo2 (](icorprofilerinfo2-getcodeinfo2-method.md) .|  
|[Método GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)|Obtiene el identificador del subproceso actual, si es un subproceso administrado.|  
|[Método GetEventMask](icorprofilerinfo-geteventmask-method.md)|Obtiene las categorías de eventos actuales para las que el generador de perfiles desea recibir notificaciones de eventos de CLR.|  
|[Método GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)|Asigna un puntero de instrucción de código administrado a un `FunctionID` .|  
|[Método GetFunctionFromToken](icorprofilerinfo-getfunctionfromtoken-method.md)|Obtiene el identificador de una función. Este método está obsoleto en la .NET Framework versión 2,0. Use en su lugar el método [ICorProfilerInfo2:: GetFunctionFromTokenAndTypeArgs (](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md) .|  
|[Método GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)|Obtiene la clase primaria y el token de metadatos para la función especificada.|  
|[Método GetHandleFromThread](icorprofilerinfo-gethandlefromthread-method.md)|Asigna el identificador de un subproceso a un identificador de subproceso de Win32.|  
|[Método GetILFunctionBody](icorprofilerinfo-getilfunctionbody-method.md)|Obtiene un puntero al cuerpo de un método en el código del lenguaje intermedio de Microsoft (MSIL), comenzando en su encabezado.|  
|[Método GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)|Obtiene una interfaz que proporciona un método para asignar la memoria que se va a usar para intercambiar el cuerpo de un método en código MSIL.|  
|[Método GetILToNativeMapping](icorprofilerinfo-getiltonativemapping-method.md)|Obtiene una asignación de desplazamientos de MSIL a desplazamientos nativos para el código contenido en la función especificada.|  
|[Método GetInprocInspectionInterface](icorprofilerinfo-getinprocinspectioninterface-method.md)|Obtiene un objeto que se puede consultar para una interfaz ICorDebugProcess. Este método está obsoleto en la .NET Framework versión 2,0.|  
|[Método GetInprocInspectionIThisThread](icorprofilerinfo-getinprocinspectionithisthread-method.md)|Obtiene un objeto que se puede consultar para la interfaz ICorDebugThread. Este método está obsoleto en la .NET Framework versión 2,0.|  
|[Método GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)|A partir de un identificador de módulo, devuelve el nombre de archivo del módulo y el identificador del ensamblado primario del módulo.|  
|[Método GetModuleMetaData](icorprofilerinfo-getmodulemetadata-method.md)|Obtiene una instancia de la interfaz de metadatos que se asigna al módulo especificado.|  
|[Método GetObjectSize](icorprofilerinfo-getobjectsize-method.md)|Obtiene el tamaño de un objeto especificado.|  
|[GetThreadContext (Método)](icorprofilerinfo-getthreadcontext-method.md)|Obtiene la identidad de contexto asociada actualmente al subproceso especificado.|  
|[Método GetThreadInfo](icorprofilerinfo-getthreadinfo-method.md)|Obtiene la identidad del subproceso de Win32 actual para el subproceso especificado.|  
|[Método GetTokenAndMetadataFromFunction](icorprofilerinfo-gettokenandmetadatafromfunction-method.md)|Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.|  
|[Método IsArrayClass](icorprofilerinfo-isarrayclass-method.md)|Determina si la clase especificada es una clase de matriz.|  
|[Método SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.|  
|[Método SetEventMask](icorprofilerinfo-seteventmask-method.md)|Establece un valor que especifica los tipos de eventos para los que el generador de perfiles desea recibir notificaciones de CLR.|  
|[Método SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)|Especifica la función implementada por el generador de perfiles a la que se llamará para asignar los valores `FunctionID` a valores alternativos, que se pasan los enlaces de entrada y salida de función del generador de perfiles.|  
|[Método SetFunctionReJIT](icorprofilerinfo-setfunctionrejit-method.md)|No implementado. No debe usarse.|  
|[SetILFunctionBody (Método)](icorprofilerinfo-setilfunctionbody-method.md)|Reemplaza el cuerpo de la función especificada en el módulo especificado.|  
|[SetILInstrumentedCodeMap (Método)](icorprofilerinfo-setilinstrumentedcodemap-method.md)|Especifica cómo se asignan los desplazamientos del MSIL original de una función especificada a los nuevos desplazamientos del MSIL modificado por el generador de perfiles de la función.|  
  
## <a name="remarks"></a>Observaciones  

 Un generador de perfiles llama a un método de la `ICorProfilerInfo` interfaz para comunicarse con CLR para controlar la supervisión de eventos y solicitar información.  
  
 El CLR implementa los métodos de la `ICorProfilerInfo` interfaz mediante el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Vea CorError. h para obtener una lista de posibles códigos de retorno.  
  
 El CLR pasa, a través de la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md), una `ICorProfilerInfo` interfaz para cada generador de perfiles de código durante la inicialización. Un generador de perfiles de código puede llamar a los métodos de la `ICorProfilerInfo` interfaz para obtener información sobre el código administrado que se ejecuta bajo el control de CLR.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo2 (Interfaz)](icorprofilerinfo2-interface.md)
