---
title: ICorProfilerInfo2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2
helpviewer_keywords:
- ICorProfilerInfo2 interface [.NET Framework profiling]
ms.assetid: 91bd49b6-4d12-494f-a8f1-2f251e8c65e3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8cec2a622a1a30881949ad5a9f2050077e195015
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33461404"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2 (Interfaz)
Proporciona métodos que los generadores de perfiles de código usan para comunicarse con el common language runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud. El `ICorProfilerInfo2` interfaz es una extensión de la [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) interfaz. Es decir, proporciona nuevos métodos admitidos en la versión de .NET Framework 2.0 y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DoStackSnapshot (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)|Recorre la pila del subproceso especificado para informar de marcos de llamadas administradas en el generador de perfiles.|  
|[EnumModuleFrozenObjects (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-enummodulefrozenobjects-method.md)|Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado.|  
|[GetAppDomainStaticAddress (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getappdomainstaticaddress-method.md)|Obtiene la dirección del campo estático del dominio de aplicación especificada que se encuentra en el ámbito del dominio de aplicación especificado.|  
|[GetArrayObjectInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getarrayobjectinfo-method.md)|Obtiene información detallada sobre un objeto de matriz.|  
|[GetBoxClassLayout (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getboxclasslayout-method.md)|Obtiene información sobre el diseño de clase para un tipo de valor especificado es una conversión boxing.|  
|[GetClassFromTokenAndTypeArgs (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y la `ClassID` valores de cualquier tipo de argumentos.|  
|[GetClassIDInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)|Obtiene el módulo primario de la clase genérica especificada, el token de metadatos para la clase, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.|  
|[GetClassLayout (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclasslayout-method.md)|Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada. Es decir, este método obtiene los desplazamientos de los campos de la clase.|  
|[GetCodeInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)|Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.|  
|[GetContextStaticAddress (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcontextstaticaddress-method.md)|Obtiene la dirección del campo estático de contexto especificado que se encuentra en el ámbito del contexto especificado.|  
|[GetFunctionFromTokenAndTypeArgs (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, que contiene la clase, y `ClassID` valores de cualquier tipo de argumentos.|  
|[GetFunctionInfo2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)|Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.|  
|[GetGenerationBounds (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getgenerationbounds-method.md)|Obtiene las regiones de memoria (los segmentos del montón) que constituyen las generaciones del montón de recolección.|  
|[GetNotifiedExceptionClauseInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Obtiene la información de dirección y el marco nativo para la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse o recientemente ejecutado.|  
|[GetObjectGeneration (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getobjectgeneration-method.md)|Obtiene el segmento del montón que contiene el objeto especificado.|  
|[GetRVAStaticAddress (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getrvastaticaddress-method.md)|Obtiene la dirección de la dirección virtual relativa (RVA) especificada-campo estático.|  
|[GetStaticFieldInfo (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstaticfieldinfo-method.md)|Obtiene el ámbito en el que el campo especificado es estático.|  
|[GetStringLayout (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getstringlayout-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[GetThreadAppDomain (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)|Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando el código.|  
|[GetThreadStaticAddress (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadstaticaddress-method.md)|Obtiene la dirección del campo estático de subproceso especificado que se encuentra en el ámbito del subproceso especificado.|  
|[SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Especifica las funciones implementadas por el generador de perfiles que se llame en "escriba", "leave" y "tailcall" enlaces de funciones administradas.|  
  
## <a name="remarks"></a>Comentarios  
 Un generador de perfiles llama a un método el `ICorProfilerInfo2` interfaz para comunicarse con CLR para controlar la supervisión de eventos y solicitar información.  
  
 Los métodos de la `ICorProfilerInfo2` interfaz está implementada por el CLR usando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 CLR pasa una `ICorProfilerInfo2` interfaz a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Un generador de perfiles de código, a continuación, puede llamar a métodos de la `ICorProfilerInfo2` interfaz para obtener información sobre el código administrado que se está ejecutando bajo el control de CLR.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
