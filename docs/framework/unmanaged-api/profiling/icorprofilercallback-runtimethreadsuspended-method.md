---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7673d6fac2626bc0059204ea77a23686b11638cc
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackruntimethreadsuspended-method"></a>ICorProfilerCallback::RuntimeThreadSuspended (Método)
Notifica al generador de perfiles que el subproceso especificado se ha suspendido o está a punto de suspensión.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RuntimeThreadSuspended(  
    [in] ThreadID threadId);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `threadId`  
 [in] El identificador del subproceso que se ha suspendido.  
  
## <a name="remarks"></a>Comentarios  
 El `RuntimeThreadSuspended` notificación puede producirse en cualquier momento entre el [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) y asociado [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) las devoluciones de llamada. Las notificaciones que se producen entre [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` para subprocesos que estaban en ejecución en código no administrado y se suspendieron cuando entra en el tiempo de ejecución.  
  
 Por lo general, esta devolución de llamada se produce justo después de que un subproceso está suspendido. Sin embargo, si el subproceso actualmente en ejecución (el subproceso que llamó a esta devolución de llamada) es el que se está suspendiendo, esta devolución de llamada se producirá justo antes de que el subproceso está suspendido.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeThreadResumed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
