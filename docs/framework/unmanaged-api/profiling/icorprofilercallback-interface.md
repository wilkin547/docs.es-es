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
ms.openlocfilehash: 891cca8ac47a3f8391bd7ab7b27b35d6318bbe0a
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76866298"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback (Interfaz)
Proporciona métodos utilizados por el Common Language Runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[AppDomainCreationFinished (método)](icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al generador de perfiles que se ha creado un dominio de aplicación.|  
|[AppDomainCreationStarted (método)](icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al generador de perfiles que se está creando un dominio de aplicación.|  
|[AppDomainShutdownFinished (método)](icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.|  
|[AppDomainShutdownStarted (método)](icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.|  
|[AssemblyLoadFinished (método)](icorprofilercallback-assemblyloadfinished-method.md)|Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.|  
|[AssemblyLoadStarted (método)](icorprofilercallback-assemblyloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un ensamblado.|  
|[AssemblyUnloadFinished (método)](icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al generador de perfiles que se ha descargado un ensamblado.|  
|[AssemblyUnloadStarted (método)](icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un ensamblado.|  
|[ClassLoadFinished (método)](icorprofilercallback-classloadfinished-method.md)|Notifica al generador de perfiles que se ha terminado de cargar una clase.|  
|[ClassLoadStarted (método)](icorprofilercallback-classloadstarted-method.md)|Notifica al generador de perfiles que se está cargando una clase.|  
|[ClassUnloadFinished (método)](icorprofilercallback-classunloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de descargarse.|  
|[ClassUnloadStarted (método)](icorprofilercallback-classunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando una clase.|  
|[COMClassicVTableCreated (método)](icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al generador de perfiles que se ha creado un contenedor RCW (Runtime Callable wrapper) para el IID y la clase especificados.|  
|[COMClassicVTableDestroyed (método)](icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al generador de perfiles que se está destruyendo un contenedor RCW.|  
|[ExceptionCatcherEnter (método)](icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al generador de perfiles que el control se pasa al bloque `catch` adecuado.|  
|[ExceptionCatcherLeave (método)](icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al generador de perfiles que el control se está pasando fuera del bloque de `catch` adecuado.|  
|[ExceptionCLRCatcherExecute (método)](icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleto en la .NET Framework versión 2,0.|  
|[ExceptionCLRCatcherFound (método)](icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleto en el .NET Framework 2,0.|  
|[ExceptionOSHandlerEnter (método)](icorprofilercallback-exceptionoshandlerenter-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionOSHandlerLeave (método)](icorprofilercallback-exceptionoshandlerleave-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[ExceptionSearchCatcherFound (método)](icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.|  
|[ExceptionSearchFilterEnter (método)](icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al generador de perfiles que se está ejecutando un filtro de usuario.|  
|[ExceptionSearchFilterLeave (método)](icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al generador de perfiles que un filtro de usuario ha terminado de ejecutarse.|  
|[ExceptionSearchFunctionEnter (método)](icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha entrado en una función.|  
|[ExceptionSearchFunctionLeave (método)](icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.|  
|[ExceptionThrown (método)](icorprofilercallback-exceptionthrown-method.md)|Notifica al generador de perfiles que se ha producido una excepción.|  
|[ExceptionUnwindFinallyEnter (método)](icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al generador de perfiles que la fase de desenredo del control de excepciones está entrando en una cláusula `finally` incluida en la función especificada.|  
|[ExceptionUnwindFinallyLeave (método)](icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha dejado una cláusula `finally`.|  
|[ExceptionUnwindFunctionEnter (método)](icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha entrado en una función.|  
|[ExceptionUnwindFunctionLeave (método)](icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha terminado de desenredar una función.|  
|[FunctionUnloadStarted (método)](icorprofilercallback-functionunloadstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.|  
|[Initialize (método)](icorprofilercallback-initialize-method.md)|Se llama para inicializar el generador de perfiles cada vez que se inicia una nueva aplicación CLR.|  
|[JITCachedFunctionSearchFinished (método)](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al generador de perfiles que ha finalizado una búsqueda para una función que se compiló previamente mediante NGen. exe.|  
|[JITCachedFunctionSearchStarted (método)](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló previamente mediante NGen. exe.|  
|[JITCompilationFinished (método)](icorprofilercallback-jitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador JIT ha terminado de compilar una función.|  
|[JITCompilationStarted (método)](icorprofilercallback-jitcompilationstarted-method.md)|Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a compilar una función.|  
|[JITFunctionPitched (método)](icorprofilercallback-jitfunctionpitched-method.md)|Notifica al generador de perfiles que se ha quitado de la memoria una función que se ha compilado con JIT.|  
|[JITInlining (método)](icorprofilercallback-jitinlining-method.md)|Notifica al generador de perfiles que el compilador JIT está a punto de insertar una función en línea con otra función.|  
|[ManagedToUnmanagedTransition (método)](icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.|  
|[ModuleAttachedToAssembly (método)](icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al generador de perfiles que se está asociando un módulo a su ensamblado primario.|  
|[ModuleLoadFinished (método)](icorprofilercallback-moduleloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de cargarse.|  
|[ModuleLoadStarted (método)](icorprofilercallback-moduleloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un módulo.|  
|[ModuleUnloadFinished (método)](icorprofilercallback-moduleunloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de descargarse.|  
|[ModuleUnloadStarted (método)](icorprofilercallback-moduleunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un módulo.|  
|[MovedReferences (método)](icorprofilercallback-movedreferences-method.md)|Notifica al generador de perfiles sobre las referencias a objetos que se movieron durante la recolección de elementos no utilizados.|  
|[ObjectAllocated (método)](icorprofilercallback-objectallocated-method.md)|Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.|  
|[ObjectReferences (método)](icorprofilercallback-objectreferences-method.md)|Notifica al generador de perfiles sobre los objetos en memoria a los que hace referencia el objeto especificado.|  
|[ObjectsAllocatedByClass (método)](icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la recolección de elementos no utilizados anterior.|  
|[RemotingClientInvocationFinished (método)](icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.|  
|[RemotingClientInvocationStarted (método)](icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una llamada de comunicación remota.|  
|[RemotingClientReceivingReply (método)](icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.|  
|[RemotingClientSendingMessage (método)](icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al generador de perfiles que el cliente envía una solicitud al servidor.|  
|[RemotingServerInvocationReturned (método)](icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al generador de perfiles que el proceso ha terminado de invocar un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerInvocationStarted (método)](icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.|  
|[RemotingServerReceivingMessage (método)](icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al generador de perfiles que el proceso está recibiendo una solicitud de activación o invocación de método remoto.|  
|[RemotingServerSendingReply (método)](icorprofilercallback-remotingserversendingreply-method.md)|Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.|  
|[RootReferences (método)](icorprofilercallback-rootreferences-method.md)|Notifica al generador de perfiles información sobre las referencias raíz después de la recolección de elementos no utilizados.|  
|[RuntimeResumeFinished (método)](icorprofilercallback-runtimeresumefinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.|  
|[RuntimeResumeStarted (método)](icorprofilercallback-runtimeresumestarted-method.md)|Notifica al generador de perfiles que el Runtime está reanudando todos los subprocesos en tiempo de ejecución.|  
|[RuntimeSuspendAborted (método)](icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.|  
|[RuntimeSuspendFinished (método)](icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al generador de perfiles que el Runtime ha completado la suspensión de todos los subprocesos en tiempo de ejecución.|  
|[RuntimeSuspendStarted (método)](icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.|  
|[RuntimeThreadResumed (método)](icorprofilercallback-runtimethreadresumed-method.md)|Notifica al generador de perfiles que se ha reanudado el subproceso especificado tras su suspensión.|  
|[RuntimeThreadSuspended (método)](icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al generador de perfiles que el subproceso especificado ha sido o está a punto de ser suspendido.|  
|[Shutdown (método)](icorprofilercallback-shutdown-method.md)|Notifica al generador de perfiles que la aplicación se está cerrando.|  
|[ThreadAssignedToOSThread (método)](icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo (SO) determinado.|  
|[ThreadCreated (método)](icorprofilercallback-threadcreated-method.md)|Notifica al generador de perfiles que se ha creado un subproceso.|  
|[ThreadDestroyed (método)](icorprofilercallback-threaddestroyed-method.md)|Notifica al generador de perfiles que se ha destruido un subproceso.|  
|[UnmanagedToManagedTransition (método)](icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código no administrado a código administrado.|  
  
## <a name="remarks"></a>Notas  
 CLR llama a un método de la interfaz `ICorProfilerCallback` (o [ICorProfilerCallback2](icorprofilercallback2-interface.md)) para notificar al generador de perfiles cuando se produce un evento, al que se ha suscrito el generador de perfiles. Esta es la interfaz de devolución de llamada principal a través de la cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la interfaz `ICorProfilerCallback`. En el .NET Framework versión 2,0 o posterior, el generador de perfiles también debe implementar los métodos de `ICorProfilerCallback2`. Cada implementación de método debe devolver un HRESULT que tenga un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, CLR omite el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 En el registro de Microsoft Windows, un generador de perfiles de código debe registrar su objeto de modelo de objetos componentes (COM) que implementa las interfaces `ICorProfilerCallback` y `ICorProfilerCallback2`. Un generador de perfiles de código se suscribe a los eventos para los que desea recibir notificaciones llamando a [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Normalmente, esto se hace en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Después, el generador de perfiles puede recibir notificaciones del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en tiempo de ejecución en ejecución.  
  
> [!NOTE]
> El generador de perfiles registra un objeto COM único. Si el generador de perfiles tiene como destino la .NET Framework versión 1,0 o 1,1, el objeto COM solo debe implementar los métodos de `ICorProfilerCallback`. Si tiene como destino .NET Framework versión 2,0 o posterior, el objeto COM también debe implementar los métodos de `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 (interfaz)](icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 (interfaz)](icorprofilercallback4-interface.md)
