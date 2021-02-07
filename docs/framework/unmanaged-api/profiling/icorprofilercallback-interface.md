---
description: 'Más información sobre: ICorProfilerCallback (interfaz)'
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
ms.openlocfilehash: 5bc59839bfe352fb7d67688dcd7c8fe0d6c97eaf
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705920"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback (Interfaz)

Proporciona métodos utilizados por el Common Language Runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AppDomainCreationFinished](icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al generador de perfiles que se ha creado un dominio de aplicación.|  
|[Método AppDomainCreationStarted](icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al generador de perfiles que se está creando un dominio de aplicación.|  
|[Método AppDomainShutdownFinished](icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al generador de perfiles que se ha descargado un dominio de aplicación de un proceso.|  
|[Método AppDomainShutdownStarted](icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.|  
|[Método AssemblyLoadFinished](icorprofilercallback-assemblyloadfinished-method.md)|Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.|  
|[Método AssemblyLoadStarted](icorprofilercallback-assemblyloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un ensamblado.|  
|[Método AssemblyUnloadFinished](icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al generador de perfiles que se ha descargado un ensamblado.|  
|[Método AssemblyUnloadStarted](icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un ensamblado.|  
|[Método ClassLoadFinished](icorprofilercallback-classloadfinished-method.md)|Notifica al generador de perfiles que se ha terminado de cargar una clase.|  
|[Método ClassLoadStarted](icorprofilercallback-classloadstarted-method.md)|Notifica al generador de perfiles que se está cargando una clase.|  
|[Método ClassUnloadFinished](icorprofilercallback-classunloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de descargarse.|  
|[Método ClassUnloadStarted](icorprofilercallback-classunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando una clase.|  
|[Método COMClassicVTableCreated](icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al generador de perfiles que se ha creado un contenedor RCW (Runtime Callable wrapper) para el IID y la clase especificados.|  
|[Método COMClassicVTableDestroyed](icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al generador de perfiles que se está destruyendo un contenedor RCW.|  
|[Método ExceptionCatcherEnter](icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al generador de perfiles que el control se está pasando al `catch` bloque adecuado.|  
|[Método ExceptionCatcherLeave](icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al generador de perfiles que el control se está pasando fuera del `catch` bloque adecuado.|  
|[Método ExceptionCLRCatcherExecute](icorprofilercallback-exceptionclrcatcherexecute-method.md)|Obsoleto en la .NET Framework versión 2,0.|  
|[Método ExceptionCLRCatcherFound](icorprofilercallback-exceptionclrcatcherfound-method.md)|Obsoleto en el .NET Framework 2,0.|  
|[Método ExceptionOSHandlerEnter](icorprofilercallback-exceptionoshandlerenter-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[Método ExceptionOSHandlerLeave](icorprofilercallback-exceptionoshandlerleave-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[Método ExceptionSearchCatcherFound](icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha encontrado un controlador para la excepción que se produjo.|  
|[Método ExceptionSearchFilterEnter](icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al generador de perfiles que se está ejecutando un filtro de usuario.|  
|[Método ExceptionSearchFilterLeave](icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al generador de perfiles que un filtro de usuario ha terminado de ejecutarse.|  
|[Método ExceptionSearchFunctionEnter](icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha entrado en una función.|  
|[Método ExceptionSearchFunctionLeave](icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.|  
|[Método ExceptionThrown](icorprofilercallback-exceptionthrown-method.md)|Notifica al generador de perfiles que se ha producido una excepción.|  
|[Método ExceptionUnwindFinallyEnter](icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones está entrando `finally` en una cláusula incluida en la función especificada.|  
|[Método ExceptionUnwindFinallyLeave](icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha dejado una `finally` cláusula.|  
|[Método ExceptionUnwindFunctionEnter](icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha entrado en una función.|  
|[Método ExceptionUnwindFunctionLeave](icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al generador de perfiles que la fase de desenredado del control de excepciones ha terminado de desenredar una función.|  
|[Método FunctionUnloadStarted](icorprofilercallback-functionunloadstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha empezado a descargar una función.|  
|[Método Initialize](icorprofilercallback-initialize-method.md)|Se llama para inicializar el generador de perfiles cada vez que se inicia una nueva aplicación CLR.|  
|[Método JITCachedFunctionSearchFinished](icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al generador de perfiles que ha finalizado una búsqueda para una función que se compiló anteriormente mediante NGen.exe.|  
|[Método JITCachedFunctionSearchStarted](icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se compiló anteriormente mediante NGen.exe.|  
|[Método JITCompilationFinished](icorprofilercallback-jitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador JIT ha terminado de compilar una función.|  
|[Método JITCompilationStarted](icorprofilercallback-jitcompilationstarted-method.md)|Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a compilar una función.|  
|[Método JITFunctionPitched](icorprofilercallback-jitfunctionpitched-method.md)|Notifica al generador de perfiles que se ha quitado de la memoria una función que se ha compilado con JIT.|  
|[Método JITInlining](icorprofilercallback-jitinlining-method.md)|Notifica al generador de perfiles que el compilador JIT está a punto de insertar una función en línea con otra función.|  
|[Método ManagedToUnmanagedTransition](icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código administrado a código no administrado.|  
|[Método ModuleAttachedToAssembly](icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al generador de perfiles que se está asociando un módulo a su ensamblado primario.|  
|[Método ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de cargarse.|  
|[Método ModuleLoadStarted](icorprofilercallback-moduleloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un módulo.|  
|[Método ModuleUnloadFinished](icorprofilercallback-moduleunloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de descargarse.|  
|[Método ModuleUnloadStarted](icorprofilercallback-moduleunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un módulo.|  
|[Método MovedReferences](icorprofilercallback-movedreferences-method.md)|Notifica al generador de perfiles sobre las referencias a objetos que se movieron durante la recolección de elementos no utilizados.|  
|[Método ObjectAllocated](icorprofilercallback-objectallocated-method.md)|Notifica al generador de perfiles que se ha asignado memoria en el montón para un objeto.|  
|[Método ObjectReferences](icorprofilercallback-objectreferences-method.md)|Notifica al generador de perfiles sobre los objetos en memoria a los que hace referencia el objeto especificado.|  
|[Método ObjectsAllocatedByClass](icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al generador de perfiles el número de instancias de cada clase especificada que se han creado desde la recolección de elementos no utilizados anterior.|  
|[Método RemotingClientInvocationFinished](icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al generador de perfiles que se ha ejecutado una llamada de comunicación remota para completarse en el cliente.|  
|[Método RemotingClientInvocationStarted](icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una llamada de comunicación remota.|  
|[Método RemotingClientReceivingReply](icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada de comunicación remota y que el cliente está recibiendo y procesando la respuesta.|  
|[Método RemotingClientSendingMessage](icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al generador de perfiles que el cliente envía una solicitud al servidor.|  
|[Método RemotingServerInvocationReturned](icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al generador de perfiles que el proceso ha terminado de invocar un método en respuesta a una solicitud de invocación de método remoto.|  
|[Método RemotingServerInvocationStarted](icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.|  
|[Método RemotingServerReceivingMessage](icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al generador de perfiles que el proceso está recibiendo una solicitud de activación o invocación de método remoto.|  
|[Método RemotingServerSendingReply](icorprofilercallback-remotingserversendingreply-method.md)|Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remoto y está a punto de transmitir la respuesta a través de un canal.|  
|[Método RootReferences](icorprofilercallback-rootreferences-method.md)|Notifica al generador de perfiles información sobre las referencias raíz después de la recolección de elementos no utilizados.|  
|[Método RuntimeResumeFinished](icorprofilercallback-runtimeresumefinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y ha vuelto a la operación normal.|  
|[Método RuntimeResumeStarted](icorprofilercallback-runtimeresumestarted-method.md)|Notifica al generador de perfiles que el Runtime está reanudando todos los subprocesos en tiempo de ejecución.|  
|[Método RuntimeSuspendAborted](icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al generador de perfiles que el Runtime ha anulado la suspensión en tiempo de ejecución que se estaba produciendo.|  
|[Método RuntimeSuspendFinished](icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al generador de perfiles que el Runtime ha completado la suspensión de todos los subprocesos en tiempo de ejecución.|  
|[Método RuntimeSuspendStarted](icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos en tiempo de ejecución.|  
|[Método RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)|Notifica al generador de perfiles que se ha reanudado el subproceso especificado tras su suspensión.|  
|[Método RuntimeThreadSuspended](icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al generador de perfiles que el subproceso especificado ha sido o está a punto de ser suspendido.|  
|[Método Shutdown](icorprofilercallback-shutdown-method.md)|Notifica al generador de perfiles que la aplicación se está cerrando.|  
|[Método ThreadAssignedToOSThread](icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al generador de perfiles que un subproceso administrado se está implementando utilizando un subproceso del sistema operativo (SO) determinado.|  
|[Método ThreadCreated](icorprofilercallback-threadcreated-method.md)|Notifica al generador de perfiles que se ha creado un subproceso.|  
|[Método ThreadDestroyed](icorprofilercallback-threaddestroyed-method.md)|Notifica al generador de perfiles que se ha destruido un subproceso.|  
|[Método UnmanagedToManagedTransition](icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición de código no administrado a código administrado.|  
  
## <a name="remarks"></a>Observaciones  

 CLR llama a un método de la `ICorProfilerCallback` interfaz (o [ICorProfilerCallback2](icorprofilercallback2-interface.md)) para notificar al generador de perfiles cuando se produce un evento, al que se ha suscrito el generador de perfiles. Esta es la interfaz de devolución de llamada principal a través de la cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la `ICorProfilerCallback` interfaz. En el .NET Framework versión 2,0 o posterior, el generador de perfiles también debe implementar los `ICorProfilerCallback2` métodos. Cada implementación de método debe devolver un HRESULT que tenga un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, CLR omite el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 En el registro de Microsoft Windows, un generador de perfiles de código debe registrar su objeto de modelo de objetos componentes (COM) que implementa las `ICorProfilerCallback` `ICorProfilerCallback2` interfaces y. Un generador de perfiles de código se suscribe a los eventos para los que desea recibir notificaciones llamando a [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Normalmente, esto se hace en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Después, el generador de perfiles puede recibir notificaciones del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en tiempo de ejecución en ejecución.  
  
> [!NOTE]
> El generador de perfiles registra un objeto COM único. Si el generador de perfiles tiene como destino la .NET Framework versión 1,0 o 1,1, el objeto COM solo debe implementar los métodos de `ICorProfilerCallback` . Si tiene como destino .NET Framework versión 2,0 o posterior, el objeto COM también debe implementar los métodos de `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 (Interfaz)](icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)
