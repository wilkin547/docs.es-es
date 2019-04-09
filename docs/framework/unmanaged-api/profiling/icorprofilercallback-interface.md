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
ms.openlocfilehash: e2f474317493b3aac421ca1270ff461b97cfe027
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59125949"
---
# <a name="icorprofilercallback-interface"></a>ICorProfilerCallback (Interfaz)
Proporciona métodos que se usan por common language runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos al que se ha suscrito el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método AppDomainCreationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationfinished-method.md)|Notifica al generador de perfiles que se ha creado un dominio de aplicación.|  
|[Método AppDomainCreationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomaincreationstarted-method.md)|Notifica al generador de perfiles que se está creando un dominio de aplicación.|  
|[Método AppDomainShutdownFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownfinished-method.md)|Notifica al generador de perfiles que se ha descargado de un proceso de un dominio de aplicación.|  
|[Método AppDomainShutdownStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-appdomainshutdownstarted-method.md)|Notifica al generador de perfiles que se está descargando un dominio de aplicación de un proceso.|  
|[Método AssemblyLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadfinished-method.md)|Notifica al generador de perfiles que un ensamblado ha terminado de cargarse.|  
|[Método AssemblyLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un ensamblado.|  
|[Método AssemblyUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadfinished-method.md)|Notifica al generador de perfiles que se ha descargado un ensamblado.|  
|[Método AssemblyUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-assemblyunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un ensamblado.|  
|[Método ClassLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de cargarse.|  
|[Método ClassLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classloadstarted-method.md)|Notifica al generador de perfiles que se está cargando una clase.|  
|[Método ClassUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadfinished-method.md)|Notifica al generador de perfiles que una clase ha terminado de descargarse.|  
|[Método ClassUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-classunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando una clase.|  
|[Método COMClassicVTableCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtablecreated-method.md)|Notifica al generador de perfiles que se ha creado un contenedor invocable en tiempo de ejecución (RCW) para el IID y la clase especificada.|  
|[Método COMClassicVTableDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-comclassicvtabledestroyed-method.md)|Notifica al generador de perfiles que se está destruyendo un RCW.|  
|[Método ExceptionCatcherEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherenter-method.md)|Notifica al generador de perfiles que se está pasando el control correspondiente `catch` bloque.|  
|[Método ExceptionCatcherLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptioncatcherleave-method.md)|Notifica al generador de perfiles que se pasa el control fuera adecuado `catch` bloque.|  
|[Método ExceptionCLRCatcherExecute](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherexecute-method.md)|Ha quedado obsoleto en .NET Framework versión 2.0.|  
|[Método ExceptionCLRCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionclrcatcherfound-method.md)|Ha quedado obsoleto en .NET Framework 2.0.|  
|[Método ExceptionOSHandlerEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerenter-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[Método ExceptionOSHandlerLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionoshandlerleave-method.md)|Sin implementar. Un generador de perfiles que necesita información de excepción no administrada debe obtener esta información a través de otros medios.|  
|[Método ExceptionSearchCatcherFound](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchcatcherfound-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones encuentra un controlador para la excepción que se produjo.|  
|[Método ExceptionSearchFilterEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterenter-method.md)|Notifica al generador de perfiles que se está ejecutando un filtro de usuario.|  
|[Método ExceptionSearchFilterLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfilterleave-method.md)|Notifica al generador de perfiles que un filtro de usuario acaba de ejecutar.|  
|[Método ExceptionSearchFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionenter-method.md)|Notifica al generador de perfiles que ha entrado en una función de la fase de búsqueda del control de excepciones.|  
|[Método ExceptionSearchFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionsearchfunctionleave-method.md)|Notifica al generador de perfiles que la fase de búsqueda del control de excepciones ha terminado de buscar una función.|  
|[Método ExceptionThrown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionthrown-method.md)|Notifica al generador de perfiles que se ha producido una excepción.|  
|[Método ExceptionUnwindFinallyEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyenter-method.md)|Notifica al generador de perfiles que la fase de desenredo de excepciones está entrando en control de un `finally` cláusula contenida en la función especificada.|  
|[Método ExceptionUnwindFinallyLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfinallyleave-method.md)|Notifica al generador de perfiles que la fase de desenredo de excepción control ha dejado un `finally` cláusula.|  
|[Método ExceptionUnwindFunctionEnter](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionenter-method.md)|Notifica al generador de perfiles que ha entrado en una función de la fase de desenredo de excepciones.|  
|[Método ExceptionUnwindFunctionLeave](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-exceptionunwindfunctionleave-method.md)|Notifica al generador de perfiles que ha terminado la fase de desenredo de excepciones de desenredado de una función.|  
|[Método FunctionUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-functionunloadstarted-method.md)|Notifica al generador de perfiles que se ha iniciado el tiempo de ejecución a una función de punto de descargarse.|  
|[Método Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md)|Se llama para inicializar el generador de perfiles cuando se inicia una nueva aplicación de CLR.|  
|[Método JITCachedFunctionSearchFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchfinished-method.md)|Notifica al generador de perfiles que ha finalizado la búsqueda para una función que se ha compilado previamente con NGen.exe.|  
|[Método JITCachedFunctionSearchStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcachedfunctionsearchstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una búsqueda para una función que se ha compilado previamente con NGen.exe.|  
|[Método JITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador JIT ha terminado de compilar una función.|  
|[Método JITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) compilar una función.|  
|[Método JITFunctionPitched](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitfunctionpitched-method.md)|Notifica al generador de perfiles que se ha quitado una función que se ha compilado con JIT de la memoria.|  
|[Método JITInlining](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-jitinlining-method.md)|Notifica al generador de perfiles que el compilador JIT está a punto de insertar una función en consonancia con otra función.|  
|[Método ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición desde código administrado a código no administrado.|  
|[Método ModuleAttachedToAssembly](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleattachedtoassembly-method.md)|Notifica al generador de perfiles que se va a adjuntar un módulo a su ensamblado principal.|  
|[Método ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de cargarse.|  
|[Método ModuleLoadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadstarted-method.md)|Notifica al generador de perfiles que se está cargando un módulo.|  
|[Método ModuleUnloadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadfinished-method.md)|Notifica al generador de perfiles que un módulo ha terminado de descargarse.|  
|[Método ModuleUnloadStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleunloadstarted-method.md)|Notifica al generador de perfiles que se está descargando un módulo.|  
|[Método MovedReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-movedreferences-method.md)|Notifica al generador de perfiles de las referencias de objeto que se movieron durante la recolección de elementos no utilizados.|  
|[Método ObjectAllocated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectallocated-method.md)|Notifica al generador de perfiles que se ha asignado la memoria del montón de un objeto.|  
|[Método ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md)|Notifica al generador de perfiles de objetos en memoria al que hace referencia el objeto especificado.|  
|[Método ObjectsAllocatedByClass](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectsallocatedbyclass-method.md)|Notifica al generador de perfiles sobre el número de instancias de cada clase especificada que se han creado desde la recolección de elementos anteriores.|  
|[Método RemotingClientInvocationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationfinished-method.md)|Notifica al generador de perfiles que una llamada remota ha ejecutado hasta su finalización en el cliente.|  
|[Método RemotingClientInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientinvocationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado una llamada remota.|  
|[Método RemotingClientReceivingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientreceivingreply-method.md)|Notifica al generador de perfiles que se ha completado la parte del servidor de una llamada remota y el cliente ahora recibe y a procesar la respuesta.|  
|[Método RemotingClientSendingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingclientsendingmessage-method.md)|Notifica al generador de perfiles que el cliente envía una solicitud al servidor.|  
|[Método RemotingServerInvocationReturned](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationreturned-method.md)|Notifica al generador de perfiles que ha finalizado el proceso para invocar un método en respuesta a una solicitud de invocación de método remoto.|  
|[Método RemotingServerInvocationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverinvocationstarted-method.md)|Notifica al generador de perfiles que el proceso está invocando un método en respuesta a una solicitud de invocación de método remoto.|  
|[Método RemotingServerReceivingMessage](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserverreceivingmessage-method.md)|Notifica al generador de perfiles que el proceso recibe una solicitud de activación o la invocación de método remoto.|  
|[Método RemotingServerSendingReply](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-remotingserversendingreply-method.md)|Notifica al generador de perfiles que el proceso ha terminado de procesar una solicitud de invocación de método remota y está a punto de transmitir la respuesta a través de un canal.|  
|[Método RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md)|Notifica al generador de perfiles con información acerca de las referencias de raíz después de la recolección de elementos.|  
|[Método RuntimeResumeFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumefinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha reanudado todos los subprocesos en tiempo de ejecución y se ha vuelto a su funcionamiento normal.|  
|[Método RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está reanudando todos los subprocesos de tiempo de ejecución.|  
|[Método RuntimeSuspendAborted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)|Notifica al generador de perfiles que ha anulado el tiempo de ejecución de la suspensión de tiempo de ejecución que se está produciendo.|  
|[Método RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)|Notifica al generador de perfiles que el tiempo de ejecución ha finalizado la suspensión de todos los subprocesos de tiempo de ejecución.|  
|[Método RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md)|Notifica al generador de perfiles que el tiempo de ejecución está a punto de suspender todos los subprocesos de tiempo de ejecución.|  
|[Método RuntimeThreadResumed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)|Notifica al generador de perfiles que se ha reanudado el subproceso especificado después de haberse suspendido.|  
|[Método RuntimeThreadSuspended](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadsuspended-method.md)|Notifica al generador de perfiles que el subproceso especificado ha sido o está a punto, suspenderse.|  
|[Método Shutdown](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-shutdown-method.md)|Notifica al generador de perfiles que se va a cerrar la aplicación.|  
|[Método ThreadAssignedToOSThread](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadassignedtoosthread-method.md)|Notifica al generador de perfiles que se está implementando un subproceso administrado mediante un subproceso de sistema operativo determinado (SO).|  
|[Método ThreadCreated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threadcreated-method.md)|Notifica al generador de perfiles que se ha creado un subproceso.|  
|[Método ThreadDestroyed](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-threaddestroyed-method.md)|Notifica al generador de perfiles que se ha destruido un subproceso.|  
|[Método UnmanagedToManagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-unmanagedtomanagedtransition-method.md)|Notifica al generador de perfiles que se ha producido una transición desde código no administrado a código administrado.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a un método el `ICorProfilerCallback` (o [ICorProfilerCallback2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)) interfaz para notificar al generador de perfiles cuando un evento, al que se haya suscrito el generador de perfiles, se produce. Esta es la interfaz de devolución de llamada principal a través del cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la `ICorProfilerCallback` interfaz. .NET Framework versión 2.0 o posterior, el generador de perfiles también debe implementar la `ICorProfilerCallback2` métodos. Cada implementación de método debe devolver un valor HRESULT que tiene un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, el CLR pasa por alto el HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 En el registro de Microsoft Windows, un generador de perfiles de código debe registrar su objeto de modelo de objetos componentes (COM) que implementa el `ICorProfilerCallback` y `ICorProfilerCallback2` interfaces. Un generador de perfiles de código se suscribe a los eventos para el que desea recibir una notificación mediante una llamada a [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Esto se hace normalmente en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). El generador de perfiles, a continuación, es capaz de recibir una notificación del tiempo de ejecución cuando un evento tiene lugar o se produce en un proceso que se ejecuta en tiempo de ejecución.  
  
> [!NOTE]
>  El generador de perfiles registra un único objeto COM. Si el generador de perfiles está destinado a .NET Framework versión 1.0 o 1.1, que debe implementar solo los métodos del objeto COM `ICorProfilerCallback`. Si tiene como destino .NET Framework versión 2.0 o posterior, el objeto COM debe implementar también los métodos de `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerCallback2 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback3 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
