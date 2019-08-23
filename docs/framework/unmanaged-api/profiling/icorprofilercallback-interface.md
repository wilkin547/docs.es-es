---
title: ICorProfilerCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback
helpviewer_keywords:
- ICorProfilerCallback interface [.NET Framework profiling]
ms.assetid: 4bae06f7-94d7-4ba8-b250-648b2da78674
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3119818934df765a8bbd9c05caaee04f9476069f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69963521"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback (Interfaz)
Proporciona métodos utilizados por el Common Language Runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|DESCRIPCIÓN|  
|------------|-----------------|  
|[AppDomainCreationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al generador de perfiles que se ha creado un dominio de aplicación.|  
|[AppDomainCreationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al generador de perfiles que se está creando un dominio de aplicación.|  
|[AppDomainShutdownFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.|  
|[AppDomainShutdownStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.|  
|[AssemblyLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.|  
|[AssemblyLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un ensamblado.|  
|[AssemblyUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al generador de perfiles que se ha descargado un ensamblado.|  
|[AssemblyUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un ensamblado.|  
|[ClassLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al generador de perfiles que se ha terminado de cargar una clase.|  
|[ClassLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica al generador de perfiles que se está cargando una clase.|  
|[ClassUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de descargarse.|  
|[ClassUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando una clase.|  
|[COMClassicVTableCreated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al generador de perfiles que se ha creado un contenedor RCW (Runtime Callable wrapper) para el IID y la clase especificados.|  
|[COMClassicVTableDestroyed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al generador de perfiles que se está destruyendo un contenedor RCW.|  
|[ExceptionCatcherEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al generador de perfiles que el control se está pasando al `catch` bloque adecuado.|  
|[ExceptionCatcherLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al generador de perfiles que el control se está pasando fuera del `catch` bloque adecuado.|  
|[ExceptionCLRCatcherExecute (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleto en la .NET Framework versión 2,0.|  
|[ExceptionCLRCatcherFound (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleto en el .NET Framework 2,0.|  
|[ExceptionOSHandlerEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionOSHandlerLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionSearchCatcherFound (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.|  
|[ExceptionSearchFilterEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al generador de perfiles que se está ejecutando un filtro de usuario.|  
|[ExceptionSearchFilterLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al generador de perfiles que un filtro de usuario ha terminado de ejecutarse.|  
|[ExceptionSearchFunctionEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha entrado en una función.|  
|[ExceptionSearchFunctionLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.|  
|[ExceptionThrown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al generador de perfiles que se ha producido una excepción.|  
|[ExceptionUnwindFinallyEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de `finally` excepciones está entrando en una cláusula incluida en la función especificada.|  
|[ExceptionUnwindFinallyLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de `finally` excepciones ha dejado una cláusula.|  
|[ExceptionUnwindFunctionEnter (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha entrado en una función.|  
|[ExceptionUnwindFunctionLeave (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha terminado de desenredar una función.|  
|[FunctionUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.|  
|[Initialize (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Se llama para inicializar el generador de perfiles cada vez que se inicia una nueva aplicación CLR.|  
|[JITCachedFunctionSearchFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al generador de perfiles que ha finalizado una búsqueda para una función que se compiló previamente mediante NGen. exe.|  
|[JITCachedFunctionSearchStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló previamente mediante NGen. exe.|  
|[JITCompilationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador JIT ha terminado de compilar una función.|  
|[JITCompilationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a compilar una función.|  
|[JITFunctionPitched (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al generador de perfiles que se ha quitado de la memoria una función que se ha compilado con JIT.|  
|[JITInlining (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al generador de perfiles que el compilador JIT está a punto de insertar una función en línea con otra función.|  
|[ManagedToUnmanagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.|  
|[ModuleAttachedToAssembly (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al generador de perfiles que se está asociando un módulo a su ensamblado primario.|  
|[ModuleLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de cargarse.|  
|[ModuleLoadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un módulo.|  
|[ModuleUnloadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de descargarse.|  
|[ModuleUnloadStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un módulo.|  
|[MovedReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al generador de perfiles sobre las referencias a objetos que se movieron durante la recolección de elementos no utilizados.|  
|[ObjectAllocated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.|  
|[ObjectReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al generador de perfiles sobre los objetos en memoria a los que hace referencia el objeto especificado.|  
|[ObjectsAllocatedByClass (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la recolección de elementos no utilizados anterior.|  
|[RemotingClientInvocationFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.|  
|[RemotingClientInvocationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una llamada de comunicación remota.|  
|[RemotingClientReceivingReply (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.|  
|[RemotingClientSendingMessage (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al generador de perfiles que el cliente envía una solicitud al servidor.|  
|[RemotingServerInvocationReturned (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al generador de perfiles que el proceso ha terminado de invocar un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerInvocationStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerReceivingMessage (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al generador de perfiles que el proceso está recibiendo una solicitud de activación o invocación de método remoto.|  
|[RemotingServerSendingReply (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.|  
|[RootReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al generador de perfiles información sobre las referencias raíz después de la recolección de elementos no utilizados.|  
|[RuntimeResumeFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.|  
|[RuntimeResumeStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al generador de perfiles que el Runtime está reanudando todos los subprocesos en tiempo de ejecución.|  
|[RuntimeSuspendAborted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.|  
|[RuntimeSuspendFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al generador de perfiles que el Runtime ha completado la suspensión de todos los subprocesos en tiempo de ejecución.|  
|[RuntimeSuspendStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.|  
|[RuntimeThreadResumed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al generador de perfiles que se ha reanudado el subproceso especificado tras su suspensión.|  
|[RuntimeThreadSuspended (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al generador de perfiles que el subproceso especificado ha sido o está a punto de ser suspendido.|  
|[Shutdown (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al generador de perfiles que la aplicación se está cerrando.|  
|[ThreadAssignedToOSThread (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo (SO) determinado.|  
|[ThreadCreated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al generador de perfiles que se ha creado un subproceso.|  
|[ThreadDestroyed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al generador de perfiles que se ha destruido un subproceso.|  
|[UnmanagedToManagedTransition (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código no administrado a código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a un método de la `ICorProfilerCallback` interfaz (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) para notificar al generador de perfiles cuando se produce un evento, al que se ha suscrito el generador de perfiles. Esta es la interfaz de devolución de llamada principal a través de la cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los `ICorProfilerCallback` métodos de la interfaz. En el .NET Framework versión 2,0 o posterior, el generador de perfiles también debe `ICorProfilerCallback2` implementar los métodos. Cada implementación de método debe devolver un HRESULT que tenga un valor de S_OK si se realiza correctamente o E_FAIL en caso de error. Actualmente, CLR omite el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 En el registro de Microsoft Windows, un generador de perfiles de código debe registrar su objeto de modelo de objetos componentes ( `ICorProfilerCallback` com `ICorProfilerCallback2` ) que implementa las interfaces y. Un generador de perfiles de código se suscribe a los eventos para los que desea recibir notificaciones llamando a [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Normalmente, esto se hace en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). Después, el generador de perfiles puede recibir notificaciones del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en tiempo de ejecución en ejecución.  
  
> [!NOTE]
> El generador de perfiles registra un objeto COM único. Si el generador de perfiles tiene como destino la .NET Framework versión 1,0 o 1,1, el objeto COM solo debe implementar los métodos `ICorProfilerCallback`de. Si tiene como destino .NET Framework versión 2,0 o posterior, el objeto COM también debe implementar los métodos de `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Corprof. idl, Corprof. h  
  
 **Biblioteca** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
