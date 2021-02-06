---
description: 'Más información acerca de: ICorProfilerInfo2 (interfaz)'
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
ms.openlocfilehash: 07828c6f55b72068e9021991600ed17eb6ffe6ad
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647016"
---
# <a name="icorprofilerinfo2-interface"></a>ICorProfilerInfo2 (Interfaz)

Proporciona métodos que los perfiles de código usan para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos y la información de la solicitud. La `ICorProfilerInfo2` interfaz es una extensión de la interfaz [ICorProfilerInfo](icorprofilerinfo-interface.md) . Es decir, proporciona nuevos métodos que se admiten en la .NET Framework versión 2,0 y versiones posteriores.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)|Recorre la pila del subproceso especificado para informar de los marcos de llamadas administrados al generador de perfiles.|  
|[Método EnumModuleFrozenObjects](icorprofilerinfo2-enummodulefrozenobjects-method.md)|Obtiene un enumerador que permite la iteración sobre los objetos inmovilizados en el módulo especificado.|  
|[Método GetAppDomainStaticAddress](icorprofilerinfo2-getappdomainstaticaddress-method.md)|Obtiene la dirección del campo estático del dominio de aplicación especificado que está en el ámbito del dominio de aplicación especificado.|  
|[Método GetArrayObjectInfo](icorprofilerinfo2-getarrayobjectinfo-method.md)|Obtiene información detallada sobre un objeto de matriz.|  
|[Método GetBoxClassLayout](icorprofilerinfo2-getboxclasslayout-method.md)|Obtiene información sobre el diseño de clase para un tipo de valor especificado al que se aplica la conversión boxing.|  
|[Método GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)|Obtiene el `ClassID` de un tipo mediante el token de metadatos especificado y los `ClassID` valores de cualquier argumento de tipo.|  
|[Método GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)|Obtiene el módulo primario de la clase genérica especificada, el token de metadatos para la clase, el `ClassID` de su clase primaria y el `ClassID` para cada argumento de tipo, si está presente, de la clase.|  
|[GetClassLayout (Método)](icorprofilerinfo2-getclasslayout-method.md)|Obtiene información sobre la distribución, en memoria, de los campos definidos por la clase especificada. Es decir, este método obtiene los desplazamientos de los campos de la clase.|  
|[Método GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)|Obtiene las extensiones del código nativo asociado al `FunctionID` especificado.|  
|[Método GetContextStaticAddress](icorprofilerinfo2-getcontextstaticaddress-method.md)|Obtiene la dirección del campo estático de contexto especificado que está en el ámbito del contexto especificado.|  
|[Método GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)|Obtiene el `FunctionID` de una función mediante el token de metadatos especificado, la clase contenedora y `ClassID` los valores de cualquier argumento de tipo.|  
|[Método GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)|Obtiene la clase primaria, el token de metadatos y el `ClassID` de cada argumento de tipo, si está presente, de una función.|  
|[Método GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md)|Obtiene las regiones de memoria (los segmentos del montón) que componen las generaciones del montón de recolección de elementos no utilizados.|  
|[Método GetNotifiedExceptionClauseInfo](icorprofilerinfo2-getnotifiedexceptionclauseinfo-method.md)|Obtiene la información de la dirección nativa y el marco de la cláusula de excepción ( `catch` / `finally` / `filter` ) que está a punto de ejecutarse o que se acaba de ejecutar.|  
|[Método GetObjectGeneration](icorprofilerinfo2-getobjectgeneration-method.md)|Obtiene el segmento del montón que contiene el objeto especificado.|  
|[Método GetRVAStaticAddress](icorprofilerinfo2-getrvastaticaddress-method.md)|Obtiene la dirección del campo estático de la dirección virtual relativa (RVA).|  
|[Método GetStaticFieldInfo](icorprofilerinfo2-getstaticfieldinfo-method.md)|Obtiene el ámbito en el que el campo especificado es estático.|  
|[Método GetStringLayout](icorprofilerinfo2-getstringlayout-method.md)|Obtiene información sobre la distribución de un objeto de cadena.|  
|[Método GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)|Obtiene el identificador del dominio de aplicación en el que el subproceso especificado está ejecutando código actualmente.|  
|[Método GetThreadStaticAddress](icorprofilerinfo2-getthreadstaticaddress-method.md)|Obtiene la dirección del campo estático de subproceso especificado que está en el ámbito del subproceso especificado.|  
|[Método SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md)|Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces "Enter", "Leave" y "llamada" de las funciones administradas.|  
  
## <a name="remarks"></a>Observaciones  

 Un generador de perfiles llama a un método de la `ICorProfilerInfo2` interfaz para comunicarse con CLR para controlar la supervisión de eventos y solicitar información.  
  
 El CLR implementa los métodos de la `ICorProfilerInfo2` interfaz mediante el modelo de subprocesamiento libre. Cada método devuelve un valor HRESULT para indicar un resultado correcto o erróneo. Para obtener una lista de los posibles códigos devueltos, consulte el archivo CorError.h.  
  
 El CLR pasa una `ICorProfilerInfo2` interfaz a cada generador de perfiles de código durante la inicialización, mediante la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Un generador de perfiles de código puede llamar a los métodos de la `ICorProfilerInfo2` interfaz para obtener información sobre el código administrado que se ejecuta bajo el control de CLR.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
