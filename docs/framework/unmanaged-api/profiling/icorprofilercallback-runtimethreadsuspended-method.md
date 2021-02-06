---
description: 'Más información sobre: ICorProfilerCallback:: RuntimeThreadSuspended ((método)'
title: ICorProfilerCallback::RuntimeThreadSuspended (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeThreadSuspended
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeThreadSuspended
helpviewer_keywords:
- RuntimeThreadSuspended method [.NET Framework profiling]
- ICorProfilerCallback::RuntimeThreadSuspended method [.NET Framework profiling]
ms.assetid: de830a8b-6ee1-4900-ace3-4237108f6b12
topic_type:
- apiref
ms.openlocfilehash: f7c2f5baf5a320375d9a2606ca05b13d522336be
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657339"
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended (Método)

Notifica al generador de perfiles que el subproceso especificado se ha suspendido o está a punto de ser suspendido.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
## <a name="parameters"></a>Parámetros  

 `threadId`  
 de IDENTIFICADOR del subproceso que se ha suspendido.  
  
## <a name="remarks"></a>Observaciones  

 La `RuntimeThreadSuspended` notificación puede producirse en cualquier momento entre el [ICorProfilerCallback:: runtimesuspendstarted (](icorprofilercallback-runtimesuspendstarted-method.md) y las devoluciones de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) asociadas. Las notificaciones que se producen entre [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` son para los subprocesos que se ejecutaron en código no administrado y se suspendieron en la entrada al tiempo de ejecución.  
  
 Normalmente, esta devolución de llamada se produce justo después de suspender un subproceso. Sin embargo, si el subproceso que se está ejecutando actualmente (el subproceso que llamó a esta devolución de llamada) es el que se está suspendiendo, esta devolución de llamada se producirá justo antes de que se suspenda el subproceso.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (Interfaz)](icorprofilercallback-interface.md)
- [Método RuntimeThreadResumed](icorprofilercallback-runtimethreadresumed-method.md)
