---
title: CORPROF_E_UNSUPPORTED_CALL_SEQUENCE (HRESULT)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE
helpviewer_keywords:
- CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT [.NET Framework profiling]
ms.assetid: f2fc441f-d62e-4f72-a011-354ea13c8c59
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3694e08555df3ad91fbfcc35b6eb385bd24ce3c0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corprofeunsupportedcallsequence-hresult"></a>CORPROF_E_UNSUPPORTED_CALL_SEQUENCE (HRESULT)
El valor de HRESULT CORPROF_E_UNSUPPORTED_CALL_SEQUENCE se introdujo en la versión 2.0 de .NET Framework. El [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)] devuelve este HRESULT en dos escenarios:  
  
-   Cuando un generador de perfiles de secuestro restablece de forma forzada de un subproceso registrar contexto en un momento arbitrario para que el subproceso intenta obtener acceso a estructuras que están en un estado incoherente.  
  
-   Cuando un generador de perfiles intenta llamar a un método informativo que desencadena la recolección de elementos de un método de devolución de llamada que prohíbe la recolección.  
  
 Estos dos escenarios se tratan en las secciones siguientes.  
  
## <a name="hijacking-profilers"></a>Cambiando la configuración de los generadores de perfiles  
 (Este escenario es principalmente un problema con los generadores de perfiles de apropiación aunque hay casos donde los generadores de perfiles no secuestro pueden ver este HRESULT).  
  
 En este escenario, un generador de perfiles de secuestro restablece de forma forzada contexto del registro de un subproceso en un momento arbitrario para que el subproceso puede escribir código de generador de perfiles o volver a escribir el common language runtime (CLR) a través de un [ICorProfilerInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md) método.  
  
 Muchos de los identificadores que la API de generación de perfiles proporciona punto a estructuras de datos en el CLR. Muchos `ICorProfilerInfo` llamadas simplemente leer información de estas estructuras de datos y pasarlos de nuevo. Sin embargo, el CLR puede cambiar cosas en esas estructuras tal y como se ejecuta y pueden usar bloqueos para hacerlo. Supongamos que el CLR era ya que contiene (o intentar adquirir) un bloqueo en el momento en el generador de perfiles secuestradas el subproceso. Si el subproceso vuelve a introduce el CLR y se intenta tomar más bloqueos o inspeccionar las estructuras que estaban en el proceso que se está modificando, estas estructuras estén en un estado incoherente. Interbloqueos e infracciones de acceso pueden producir con facilidad en estas situaciones.  
  
 En general, cuando un generador de perfiles no secuestro ejecuta código dentro de un [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) método y llama a un `ICorProfilerInfo` método con parámetros válidos, no debe generar un interbloqueo o recibir una infracción de acceso. Por ejemplo, el código de generador de perfiles que se ejecuta dentro de la [ICorProfilerCallback:: ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md) método puede solicitar información acerca de la clase mediante una llamada a la [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md) método. El código podría recibir un HRESULT CORPROF_E_DATAINCOMPLETE para indicar que la información está disponible; Sin embargo, no un interbloqueo ni recibir una infracción de acceso. Esta clase de llamadas en `ICorProfilerInfo` se denominan sincrónicas, porque se realizan desde un `ICorProfilerCallback` método.  
  
 Sin embargo, un subproceso administrado que ejecuta código que no está comprendido en un `ICorProfilerCallback` método se considera que está realizando una llamada asincrónica. En la versión 1 de .NET Framework, resultaba difícil determinar qué puede ocurrir en una llamada asincrónica. La llamada podría causar interbloqueos, bloqueará o proporcione una respuesta no válida. La versión 2.0 de .NET Framework introdujo algunas comprobaciones simples para ayudarle a evitar este problema. En .NET Framework 2.0, si se llama a un método unsafe `ICorProfilerInfo` funcionar de forma asincrónica, se produce un error con un HRESULT de CORPROF_E_UNSUPPORTED_CALL_SEQUENCE.  
  
 En general, las llamadas asincrónicas no son seguros. Sin embargo, los siguientes métodos son seguros y específicamente admiten llamadas asincrónicas:  
  
-   [GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md)  
  
-   [SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md)  
  
-   [GetCurrentThreadID](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcurrentthreadid-method.md)  
  
-   [GetThreadContext](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getthreadcontext-method.md)  
  
-   [GetThreadAppDomain](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getthreadappdomain-method.md)  
  
-   [GetFunctionFromIP](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctionfromip-method.md)  
  
-   [GetFunctionInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getfunctioninfo-method.md)  
  
-   [GetFunctionInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctioninfo2-method.md)  
  
-   [GetCodeInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getcodeinfo-method.md)  
  
-   [GetCodeInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getcodeinfo2-method.md)  
  
-   [GetModuleInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmoduleinfo-method.md)  
  
-   [GetClassIDInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassidinfo-method.md)  
  
-   [GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md)  
  
-   [IsArrayClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-isarrayclass-method.md)  
  
-   [SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
  
-   [DoStackSnapshot](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-dostacksnapshot-method.md)  
  
 Para obtener más información, vea la entrada [por qué tenemos CORPROF_E_UNSUPPORTED_CALL_SEQUENCE](http://go.microsoft.com/fwlink/?LinkId=169156) en el blog de API de generación de perfiles de CLR.  
  
## <a name="triggering-garbage-collections"></a>Activación de las colecciones de elementos no utilizados  
 Este escenario implica un generador de perfiles que se ejecuta dentro de un método de devolución de llamada (por ejemplo, uno de los `ICorProfilerCallback` métodos) que prohíbe la recolección. Si el generador de perfiles intenta llamar a un método informativo (por ejemplo, un método en el `ICorProfilerInfo` interfaz) que puede desencadenar una recolección, se produce un error en el método informativo con un HRESULT de CORPROF_E_UNSUPPORTED_CALL_SEQUENCE.  
  
 En la tabla siguiente muestra los métodos de devolución de llamada que prohíben las recolecciones de elementos no utilizados y métodos informativos que pueden desencadenar las colecciones de elementos no utilizados. Si el generador de perfiles se ejecuta dentro de uno de los métodos de devolución de llamada enumerados y llama a uno de los métodos informativos enumerados, ese método informativo produce un error con un HRESULT de CORPROF_E_UNSUPPORTED_CALL_SEQUENCE.  
  
|Métodos de devolución de llamada que prohíben las recolecciones de elementos no utilizados|Métodos informativos que activan las colecciones de elementos no utilizados|  
|------------------------------------------------------|------------------------------------------------------------|  
|[ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)<br /><br /> [ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)<br /><br /> [ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)<br /><br /> [ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)<br /><br /> [ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)<br /><br /> [ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)<br /><br /> [RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)<br /><br /> [RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)<br /><br /> [RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)<br /><br /> [RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)<br /><br /> [RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)<br /><br /> [MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)<br /><br /> [ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)<br /><br /> [ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)<br /><br /> [RootReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)<br /><br /> [HandleCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)<br /><br /> [HandleDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)<br /><br /> [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)<br /><br /> [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|[GetILFunctionBodyAllocator](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getilfunctionbodyallocator-method.md)<br /><br /> [SetILFunctionBody](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilfunctionbody-method.md)<br /><br /> [SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)<br /><br /> [ForceGC](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-forcegc-method.md)<br /><br /> [GetClassFromToken](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getclassfromtoken-method.md)<br /><br /> [GetClassFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassfromtokenandtypeargs-method.md)<br /><br /> [GetFunctionFromTokenAndTypeArgs](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getfunctionfromtokenandtypeargs-method.md)<br /><br /> [GetAppDomainInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getappdomaininfo-method.md)<br /><br /> [EnumModules](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-enummodules-method.md)<br /><br /> [RequestProfilerDetach](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-requestprofilerdetach-method.md)<br /><br /> [GetAppDomainsContainingModule](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-getappdomainscontainingmodule-method.md)|  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [ICorProfilerInfo3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/index.md)
