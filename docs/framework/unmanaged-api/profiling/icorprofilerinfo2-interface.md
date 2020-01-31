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
ms.openlocfilehash: 23fd44a6865b0487296f3ade37c1219e8feba288
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862586"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2 (Interfaz)
Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud. La interfaz de `ICorProfilerInfo2` es una extensión de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) . Es decir, proporciona nuevos métodos que se admiten en la .NET Framework versión 2,0 y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DoStackSnapshot (método)](icorprofilerinfo2-dostacksnapshot-method.md)|Recorre la pila del subproceso especificado para informar de los marcos de llamadas administrados al generador de perfiles.|  
|[EnumModuleFrozenObjects (método)](icorprofilerinfo2-enummodulefrozenobjects-method.md)|Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado.|  
|[GetAppDomainStaticAddress (método)](icorprofilerinfo2-getappdomainstaticaddress-method.md)|Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.|  
|[GetArrayObjectInfo (método)](icorprofilerinfo2-getarrayobjectinfo-method.md)|Obtiene información detallada sobre un objeto de matriz.|  
|[GetBoxClassLayout (método)](icorprofilerinfo2-getboxclasslayout-method.md)|Obtiene información sobre el diseño de clase para un tipo de valor especificado al que se aplica la conversión boxing.|  
|[GetClassFromTokenAndTypeArgs (método)](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los valores `ClassID` de cualquier argumento de tipo.|  
|[GetClassIDInfo2 (método)](icorprofilerinfo2-getclassidinfo2-method.md)|Obtiene el módulo primario de la clase genérica especificada, el símbolo (token) de metadatos para la clase, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.|  
|[GetClassLayout (método)](icorprofilerinfo2-getclasslayout-method.md)|Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada. Es decir, este método obtiene los desplazamientos de los campos de la clase.|  
|[GetCodeInfo2 (método)](icorprofilerinfo2-getcodeinfo2-method.md)|Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.|  
|[GetContextStaticAddress (método)](icorprofilerinfo2-getcontextstaticaddress-method.md)|Obtiene la dirección del campo estático de contexto especificado que está en el ámbito del contexto especificado.|  
|[GetFunctionFromTokenAndTypeArgs (método)](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y los valores de `ClassID` de cualquier argumento de tipo.|  
|[GetFunctionInfo2 (método)](icorprofilerinfo2-getfunctioninfo2-method.md)|Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.|  
|[GetGenerationBounds (método)](icorprofilerinfo2-getgenerationbounds-method.md)|Obtiene las regiones de memoria (los segmentos del montón) que componen las generaciones del montón de recolección de elementos no utilizados.|  
|[GetNotifiedExceptionClauseInfo (método)](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Obtiene la información de la dirección nativa y el marco de la cláusula de excepción (`catch`/`finally`/`filter`) que está a punto de ejecutarse o acaba de ejecutarse.|  
|[GetObjectGeneration (método)](icorprofilerinfo2-getobjectgeneration-method.md)|Obtiene el segmento del montón que contiene el objeto especificado.|  
|[GetRVAStaticAddress (método)](icorprofilerinfo2-getrvastaticaddress-method.md)|Obtiene la dirección del campo estático de la dirección virtual relativa (RVA).|  
|[GetStaticFieldInfo (método)](icorprofilerinfo2-getstaticfieldinfo-method.md)|Obtiene el ámbito en el que el campo especificado es estático.|  
|[GetStringLayout (método)](icorprofilerinfo2-getstringlayout-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[GetThreadAppDomain (método)](icorprofilerinfo2-getthreadappdomain-method.md)|Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando código actualmente.|  
|[GetThreadStaticAddress (método)](icorprofilerinfo2-getthreadstaticaddress-method.md)|Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso especificado.|  
|[SetEnterLeaveFunctionHooks2 (método)](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.|  
  
## <a name="remarks"></a>Notas  
 Un generador de perfiles llama a un método de la interfaz `ICorProfilerInfo2` para comunicarse con CLR para controlar la supervisión de eventos y solicitar información.  
  
 CLR implementa los métodos de la interfaz `ICorProfilerInfo2` utilizando el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 El CLR pasa una interfaz `ICorProfilerInfo2` a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Un generador de perfiles de código puede llamar a los métodos de la interfaz `ICorProfilerInfo2` para obtener información sobre el código administrado que se ejecuta bajo el control de CLR.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
