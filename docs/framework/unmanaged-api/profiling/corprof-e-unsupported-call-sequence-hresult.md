---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE (HRESULT)
ms.date: 03/30/2017
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
ms.openlocfilehash: b4ab5c8f7cdca1303cb4fbbc4fa39db3c5977c15
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867014"
---
# <a name="corprof_e_unsupported_call_sequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE (HRESULT)

El CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT se presentó en .NET Framework versión 2,0. .NET Framework 4 devuelve este valor HRESULT en dos escenarios:  
  
- Cuando un generador de perfiles de secuestro restablece de forma forzada el contexto de registro de un subproceso en un momento arbitrario para que el subproceso intente obtener acceso a las estructuras que se encuentran en un estado incoherente.  
  
- Cuando un generador de perfiles intenta llamar a un método informativo que desencadena la recolección de elementos no utilizados desde un método de devolución de llamada que prohíbe la recolección de elementos no utilizados.  
  
Estos dos escenarios se describen en las secciones siguientes.  
  
## <a name="hijacking-profilers"></a>Secuestradores de secuestros  

  (Este escenario es principalmente un problema con los perfiles de secuestro, aunque hay casos en los que los profileres sin secuestro pueden ver este HRESULT).  
  
 En este escenario, un generador de perfiles de secuestro restablece de forma forzada el contexto de registro de un subproceso en un momento arbitrario para que el subproceso pueda escribir código del generador de perfiles o volver a escribir el Common Language Runtime (CLR) a través de un método [ICorProfilerInfo](icorprofilerinfo-interface.md) .  
  
 Muchos de los identificadores que proporciona la API de generación de perfiles apuntan a las estructuras de datos de CLR. Muchas llamadas `ICorProfilerInfo` simplemente leen información de estas estructuras de datos y las pasan de nuevo. Sin embargo, CLR podría cambiar cosas en esas estructuras mientras se ejecuta y podría usar bloqueos para hacerlo. Supongamos que CLR ya contenía (o ha intentado adquirir) un bloqueo en el momento en que el generador de perfiles ha secuestrado el subproceso. Si el subproceso vuelve a escribir el CLR e intenta tomar más bloqueos o inspeccionar las estructuras que estaban en proceso de modificación, estas estructuras podrían tener un estado incoherente. En estas situaciones, se pueden producir fácilmente interbloqueos e infracciones de acceso.  
  
 En general, cuando un generador de perfiles que no es de secuestro ejecuta código dentro de un método [ICorProfilerCallback](icorprofilercallback-interface.md) y llama a un método de `ICorProfilerInfo` con parámetros válidos, no debe interbloquearse ni recibir una infracción de acceso. Por ejemplo, el código del generador de perfiles que se ejecuta dentro del método [ICorProfilerCallback:: classloadfinished (](icorprofilercallback-classloadfinished-method.md) puede solicitar información sobre la clase llamando al método [ICorProfilerInfo2:: GetClassIDInfo2 (](icorprofilerinfo2-getclassidinfo2-method.md) . El código podría recibir un CORPROF_E_DATAINCOMPLETE HRESULT para indicar que la información no está disponible. Sin embargo, no interbloqueará ni recibirá una infracción de acceso. Estas llamadas en `ICorProfilerInfo` se consideran sincrónicas, porque se realizan desde un método `ICorProfilerCallback`.  
  
 Sin embargo, se considera que un subproceso administrado que ejecuta código que no está dentro de un método `ICorProfilerCallback` está realizando una llamada asincrónica. En .NET Framework versión 1, era difícil determinar lo que puede ocurrir en una llamada asincrónica. La llamada podría interbloquearse, bloquearse o dar una respuesta no válida. .NET Framework versión 2,0 presentó algunas comprobaciones sencillas que le ayudarán a evitar este problema. En .NET Framework 2,0, si llama a una función `ICorProfilerInfo` no segura de forma asincrónica, se produce un error con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 En general, las llamadas asincrónicas no son seguras. Sin embargo, los métodos siguientes son seguros y admiten específicamente llamadas asincrónicas:  
  
- [GetEventMask](icorprofilerinfo-geteventmask-method.md)  
  
- [SetEventMask](icorprofilerinfo-seteventmask-method.md)  
  
- [GetCurrentThreadID](icorprofilerinfo-getcurrentthreadid-method.md)  
  
- [GetThreadContext](icorprofilerinfo-getthreadcontext-method.md)  
  
- [GetThreadAppDomain](icorprofilerinfo2-getthreadappdomain-method.md)  
  
- [GetFunctionFromIP](icorprofilerinfo-getfunctionfromip-method.md)  
  
- [GetFunctionInfo](icorprofilerinfo-getfunctioninfo-method.md)  
  
- [GetFunctionInfo2](icorprofilerinfo2-getfunctioninfo2-method.md)  
  
- [GetCodeInfo](icorprofilerinfo-getcodeinfo-method.md)  
  
- [GetCodeInfo2](icorprofilerinfo2-getcodeinfo2-method.md)  
  
- [GetModuleInfo](icorprofilerinfo-getmoduleinfo-method.md)  
  
- [GetClassIDInfo](icorprofilerinfo-getclassidinfo-method.md)  
  
- [GetClassIDInfo2](icorprofilerinfo2-getclassidinfo2-method.md)  
  
- [IsArrayClass](icorprofilerinfo-isarrayclass-method.md)  
  
- [SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md)  
  
- [DoStackSnapshot](icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Para obtener más información, vea la entrada [por la que hemos CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](https://docs.microsoft.com/archive/blogs/davbr/why-we-have-corprof_e_unsupported_call_sequence) en el blog de la API de generación de perfiles de CLR.  
  
## <a name="triggering-garbage-collections"></a>Desencadenar recolecciones de elementos no utilizados  
 Este escenario implica un generador de perfiles que se ejecuta dentro de un método de devolución de llamada (por ejemplo, uno de los métodos `ICorProfilerCallback`) que prohíbe la recolección de elementos no utilizados. Si el generador de perfiles intenta llamar a un método informativo (por ejemplo, un método en la interfaz `ICorProfilerInfo`) que podría desencadenar una recolección de elementos no utilizados, el método informativo produce un error con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
 En la tabla siguiente se muestran los métodos de devolución de llamada que prohíben las recolecciones de elementos no utilizados y los métodos informativos que pueden desencadenar las recolecciones Si el generador de perfiles se ejecuta dentro de uno de los métodos de devolución de llamada enumerados y llama a uno de los métodos informativos enumerados, se produce un error en el método informativo con un CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT.  
  
|Métodos de devolución de llamada que prohíben colecciones de elementos no utilizados|Métodos informativos que desencadenan las recolecciones de elementos no utilizados|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 (interfaz)](icorprofilercallback3-interface.md)
- [ICorProfilerInfo (interfaz)](icorprofilerinfo-interface.md)
- [ICorProfilerInfo2 (interfaz)](icorprofilerinfo2-interface.md)
- [ICorProfilerInfo3 (interfaz)](icorprofilerinfo3-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Generación de perfiles](index.md)
