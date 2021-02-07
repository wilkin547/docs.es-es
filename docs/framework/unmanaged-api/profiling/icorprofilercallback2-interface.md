---
description: 'Más información sobre: ICorProfilerCallback2 (interfaz)'
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
ms.openlocfilehash: b6a6fa62d8d1b119ce1a52b06cb562c6da32b1a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99705530"
---
# <a name="icorprofilercallback2-interface"></a>ICorProfilerCallback2 (Interfaz)

Proporciona métodos utilizados por el Common Language Runtime (CLR) para notificar a un generador de perfiles de código cuando se producen los eventos a los que se ha suscrito el generador de perfiles. La `ICorProfilerCallback2` interfaz es una extensión de la interfaz [ICorProfilerCallback](icorprofilercallback-interface.md) . Es decir, proporciona nuevas devoluciones de llamada introducidas en la .NET Framework versión 2,0.  
  
> [!NOTE]
> Cada implementación de método debe devolver un valor HRESULT que tenga un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, CLR omite el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método FinalizeableObjectQueued](icorprofilercallback2-finalizeableobjectqueued-method.md)|Notifica al generador de perfiles de código que un objeto con un finalizador se ha puesto en cola en el subproceso finalizador para la ejecución de su `Finalize` método.|  
|[Método GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)|Notifica al generador de perfiles que se ha completado una recolección de elementos no utilizados y que se han emitido todas las devoluciones de llamada de recolección de elementos no utilizados.|  
|[Método GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md)|Notifica al generador de perfiles de código que se ha iniciado una recolección de elementos no utilizados.|  
|[Método HandleCreated](icorprofilercallback2-handlecreated-method.md)|Notifica al generador de perfiles de código que se ha creado un identificador de recolección de elementos no utilizados.|  
|[Método HandleDestroyed](icorprofilercallback2-handledestroyed-method.md)|Notifica al generador de perfiles de código que se ha destruido un identificador de recolección de elementos no utilizados.|  
|[Método RootReferences2](icorprofilercallback2-rootreferences2-method.md)|Notifica al generador de perfiles las referencias raíz después de que se haya producido la recolección de elementos no utilizados. Este método es una extensión del método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) .|  
|[Método SurvivingReferences](icorprofilercallback2-survivingreferences-method.md)|Notifica al generador de perfiles sobre las referencias a objetos que han sobrevivido a una recolección de elementos no utilizados.|  
|[Método ThreadNameChanged](icorprofilercallback2-threadnamechanged-method.md)|Notifica al generador de perfiles de código que el nombre de un subproceso ha cambiado.|  
  
## <a name="remarks"></a>Observaciones  

 CLR llama a un método en la `ICorProfilerCallback` interfaz (o `ICorProfilerCallback2` ) para notificar al generador de perfiles cuando se produce un evento, al que se ha suscrito el generador de perfiles. Esta es la interfaz de devolución de llamada principal a través de la cual el CLR se comunica con el generador de perfiles de código.  
  
 Un generador de perfiles de código debe implementar los métodos de la `ICorProfilerCallback` interfaz. En el caso del .NET Framework 2,0 y versiones posteriores, el generador de perfiles también debe implementar los `ICorProfilerCallback2` métodos. Cada implementación de método debe devolver un valor HRESULT que tenga un valor de S_OK si se ejecuta correctamente o E_FAIL en caso de error. Actualmente, CLR omite el valor HRESULT devuelto por cada devolución de llamada excepto [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md).  
  
 Un generador de perfiles de código debe registrarse en el registro de Microsoft Windows, su objeto COM que implementa las `ICorProfilerCallback` `ICorProfilerCallback2` interfaces y. Un generador de perfiles de código se suscribe a los eventos para los que desea recibir notificaciones llamando a [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md). Normalmente, esto se hace en la implementación del generador de perfiles de [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md). Después, el generador de perfiles puede recibir notificaciones del tiempo de ejecución cuando un evento está a punto de producirse o simplemente se ha producido en un proceso en tiempo de ejecución en ejecución.  
  
> [!NOTE]
> El generador de perfiles registra un objeto COM único. Si el generador de perfiles tiene como destino .NET Framework versión 1,0 o 1,1, ese objeto COM solo necesita implementar los métodos de `ICorProfilerCallback` . Si tiene como destino .NET Framework versión 2,0 y versiones posteriores, el objeto COM también debe implementar los métodos de `ICorProfilerCallback2` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [ICorProfilerCallback3 (Interfaz)](icorprofilercallback3-interface.md)
- [ICorProfilerCallback4 (Interfaz)](icorprofilercallback4-interface.md)
