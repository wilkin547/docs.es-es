---
title: ICorProfilerCallback (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback
helpviewer_keywords: ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type: apiref
caps.latest.revision: "29"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 3370dade937d67aa40be263faf3a433d142d932c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback (Interfaz)
Proporciona métodos que se utilizan por common language runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AppDomainCreationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al generador de perfiles que se ha creado un dominio de aplicación.|  
|[AppDomainCreationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al generador de perfiles que se está creando un dominio de aplicación.|  
|[AppDomainShutdownFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al generador de perfiles que un dominio de aplicación se ha descargado desde un proceso.|  
|[AppDomainShutdownStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.|  
|[AssemblyLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.|  
|[AssemblyLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica el generador de perfiles que se va a cargar un ensamblado.|  
|[AssemblyUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al generador de perfiles que se ha descargado un ensamblado.|  
|[AssemblyUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un ensamblado.|  
|[ClassLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de cargarse.|  
|[ClassLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica el generador de perfiles que se va a cargar una clase.|  
|[ClassUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de descargarse.|  
|[ClassUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando una clase.|  
|[COMClassicVTableCreated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al generador de perfiles que se ha creado un contenedor invocable en tiempo de ejecución (RCW) para el IID y la clase especificada.|  
|[COMClassicVTableDestroyed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al generador de perfiles que se está destruyendo un RCW.|  
|[ExceptionCatcherEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al generador de perfiles que se está pasando el control a la correspondiente `catch` bloque.|  
|[ExceptionCatcherLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al generador de perfiles que se pasan control de la correspondiente `catch` bloque.|  
|[ExceptionCLRCatcherExecute (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Ha quedado obsoleto en la versión 2.0 de .NET Framework.|  
|[ExceptionCLRCatcherFound (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Ha quedado obsoleto en .NET Framework 2.0.|  
|[ExceptionOSHandlerEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionOSHandlerLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionSearchCatcherFound (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones encuentra un controlador para la excepción que se produjo.|  
|[ExceptionSearchFilterEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al generador de perfiles que se está ejecutando un filtro de usuario.|  
|[ExceptionSearchFilterLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al generador de perfiles que un filtro de usuario solo ha terminado de ejecutar.|  
|[ExceptionSearchFunctionEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha entrado en una función.|  
|[ExceptionSearchFunctionLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.|  
|[ExceptionThrown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al generador de perfiles que se ha producido una excepción.|  
|[ExceptionUnwindFinallyEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al generador de perfiles que la fase de desenredo de la excepción está accediendo al control un `finally` cláusula incluida en la función especificada.|  
|[ExceptionUnwindFinallyLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al generador de perfiles que la fase de desenredo de la excepción que ha dejado control un `finally` cláusula.|  
|[ExceptionUnwindFunctionEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al generador de perfiles que la fase de desenredo del control de excepciones ha entrado en una función.|  
|[ExceptionUnwindFunctionLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al generador de perfiles que la fase de desenredo del control de excepciones ha terminado de desenredar una función.|  
|[FunctionUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al generador de perfiles que se ha iniciado el tiempo de ejecución a una función de punto de descargarse.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Se llama para inicializar el generador de perfiles cuando se inicia una nueva aplicación de CLR.|  
|[JITCachedFunctionSearchFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al generador de perfiles que ha finalizado la búsqueda para una función que previamente compilada mediante NGen.exe.|  
|[JITCachedFunctionSearchStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que previamente compilada mediante NGen.exe.|  
|[JITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador JIT ha terminado de compilar una función.|  
|[JITCompilationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.|  
|[JITFunctionPitched (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al generador de perfiles que se ha quitado una función que se ha compilado con JIT de la memoria.|  
|[JITInlining (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al generador de perfiles que el compilador JIT está a punto de insertar una función en línea con otra función.|  
|[ManagedToUnmanagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.|  
|[ModuleAttachedToAssembly (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al generador de perfiles que se va a adjuntar un módulo a su ensamblado primario.|  
|[ModuleLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de cargarse.|  
|[ModuleLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un módulo.|  
|[ModuleUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de descargarse.|  
|[ModuleUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al generador de perfiles que un módulo se está descargando.|  
|[MovedReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al generador de perfiles acerca de las referencias de objeto que se movieron durante la recolección de elementos no utilizados.|  
|[ObjectAllocated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al generador de perfiles que se ha asignado la memoria en el montón de un objeto.|  
|[ObjectReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al generador de perfiles acerca de los objetos en memoria al que hace referencia el objeto especificado.|  
|[ObjectsAllocatedByClass (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al generador de perfiles sobre el número de instancias de cada clase especificada que se han creado desde la recolección de elementos anteriores.|  
|[RemotingClientInvocationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al generador de perfiles que una llamada de comunicación remota se ejecute hasta completarse en el cliente.|  
|[RemotingClientInvocationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una llamada remota.|  
|[RemotingClientReceivingReply (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al generador de perfiles que se ha completado la parte de servidor de una llamada de comunicación remota y el cliente ahora está recibiendo y va a procesar la respuesta.|  
|[RemotingClientSendingMessage (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al generador de perfiles que el cliente envía una solicitud al servidor.|  
|[RemotingServerInvocationReturned (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al generador de perfiles que el proceso ha terminado de invocar un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerInvocationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerReceivingMessage (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al generador de perfiles que el proceso recibe una solicitud de activación o la invocación de método remoto.|  
|[RemotingServerSendingReply (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.|  
|[RootReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al generador de perfiles con información sobre las referencias raíz después de recolección de elementos no utilizados.|  
|[RuntimeResumeFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a su funcionamiento normal.|  
|[RuntimeResumeStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al generador de perfiles que el runtime está reanudando todos los subprocesos de tiempo de ejecución.|  
|[RuntimeSuspendAborted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha anulado la suspensión de tiempo de ejecución que se estaba produciendo.|  
|[RuntimeSuspendFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha finalizado la suspensión de todos los subprocesos de tiempo de ejecución.|  
|[RuntimeSuspendStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos de tiempo de ejecución.|  
|[RuntimeThreadResumed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al generador de perfiles que el subproceso especificado ha reanudado después de haberse suspendido.|  
|[RuntimeThreadSuspended (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al generador de perfiles que el subproceso especificado ha sido o va a ser, suspendido.|  
|[Shutdown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al generador de perfiles que se está cerrando la aplicación.|  
|[ThreadAssignedToOSThread (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al generador de perfiles que se está implementando un subproceso administrado mediante un subproceso de sistema operativo particular (SO).|  
|[ThreadCreated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al generador de perfiles que se ha creado un subproceso.|  
|[ThreadDestroyed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al generador de perfiles que se ha destruido un subproceso.|  
|[UnmanagedToManagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición desde código no administrado a código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a un método el `ICorProfilerCallback` (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) interfaz para notificar al generador de perfiles cuando un evento, al que se ha suscrito el generador de perfiles, se produce. Se trata de la interfaz de devolución de llamada principal a través del cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la `ICorProfilerCallback` interfaz. La versión 2.0 o posterior de .NET Framework, el generador de perfiles también debe implementar la `ICorProfilerCallback2` métodos. Cada implementación de método debe devolver un valor HRESULT que tiene un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, el CLR pasa por alto el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 En el registro de Microsoft Windows, un generador de perfiles de código debe registrar su objeto de modelo de objetos componentes (COM) que implementa el `ICorProfilerCallback` y `ICorProfilerCallback2` interfaces. Un generador de perfiles de código se suscribe a los eventos para el que desea recibir una notificación mediante una llamada a [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Esto se hace normalmente en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). El generador de perfiles es capaz de recibir una notificación del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en ejecución en tiempo de ejecución.  
  
> [!NOTE]
>  El generador de perfiles registra un único objeto COM. Si el generador de perfiles tiene como destino .NET Framework versión 1.0 o 1.1, que debe implementar únicamente los métodos del objeto COM `ICorProfilerCallback`. Si tiene como destino .NET Framework versión 2.0 o posterior, el objeto COM debe implementar también los métodos de `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)  
 [ICorProfilerCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
