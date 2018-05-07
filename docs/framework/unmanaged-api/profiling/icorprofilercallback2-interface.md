---
title: ICorProfilerCallback2 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback2
helpviewer_keywords:
- ICorProfilerCallback2 interface [.NET Framework profiling]
ms.assetid: 4a261dba-450d-4f1f-8d98-865b58bfc992
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6a218b58ed2ab40505204768f7d6071dea6db5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 (Interfaz)
Proporciona métodos que se utilizan por common language runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles. El `ICorProfilerCallback2` interfaz es una extensión de la [ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md) interfaz. Es decir, proporciona nuevas devoluciones de llamada que introdujo en la versión 2.0 de .NET Framework.  
  
> [!NOTE]
>  Cada implementación de método debe devolver un valor HRESULT que tiene un valor de S_OK resultado correcto o E_FAIL en caso de error. Actualmente, el CLR pasa por alto el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[FinalizeableObjectQueued (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-finalizeableobjectqueued-method.md)|Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su `Finalize` método.|  
|[GarbageCollectionFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)|Notifica al generador de perfiles que ha completado una recolección y se han emitido para él todas las devoluciones de llamada de recopilación de elementos no utilizados.|  
|[GarbageCollectionStarted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md)|Notifica al generador de perfiles de código que se ha iniciado una recolección de elementos.|  
|[HandleCreated (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handlecreated-method.md)|Notifica al generador de perfiles de código que se ha creado un identificador de la colección de elementos no utilizados.|  
|[HandleDestroyed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-handledestroyed-method.md)|Notifica al generador de perfiles de código que se ha destruido un identificador de la colección de elementos no utilizados.|  
|[RootReferences2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)|Notifica al generador de perfiles acerca de las referencias de raíz después de que se ha producido una colección de elementos no utilizados. Este método es una extensión de la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) método.|  
|[SurvivingReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-survivingreferences-method.md)|Notifica al generador de perfiles acerca de las referencias de objeto que han sobrevivido a una recolección de elementos.|  
|[ThreadNameChanged (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-threadnamechanged-method.md)|Notifica al analizador de código que ha cambiado el nombre de un subproceso.|  
  
## <a name="remarks"></a>Comentarios  
 CLR llama a un método el `ICorProfilerCallback` (o `ICorProfilerCallback2`) interfaz para notificar al generador de perfiles cuando un evento, al que está suscrito el generador de perfiles, se produce. Se trata de la interfaz de devolución de llamada principal a través del cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la `ICorProfilerCallback` interfaz. Para el .NET Framework 2.0 y versiones posteriores, el generador de perfiles debe implementar también el `ICorProfilerCallback2` métodos. Cada implementación de método debe devolver un valor HRESULT que tiene un valor de S_OK resultado correcto o E_FAIL en caso de error. Actualmente, el CLR pasa por alto el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md).  
  
 Un generador de perfiles de código debe registrar en el registro de Microsoft Windows, el objeto COM que implementa el `ICorProfilerCallback` y `ICorProfilerCallback2` interfaces. Un generador de perfiles de código se suscribe a los eventos para el que desea recibir una notificación mediante una llamada a [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md). Esto se hace normalmente en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md). El generador de perfiles es capaz de recibir una notificación del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en ejecución en tiempo de ejecución.  
  
> [!NOTE]
>  El generador de perfiles registra un único objeto COM. Si el generador de perfiles tiene como destino .NET Framework versión 1.0 o 1.1, ese objeto COM sólo necesita implementar los métodos de `ICorProfilerCallback`. Si tiene como destino .NET Framework versión 2.0 y versiones posteriores, el objeto COM debe implementar también los métodos de `ICorProfilerCallback2`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [ICorProfilerCallback3 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-interface.md)  
 [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
