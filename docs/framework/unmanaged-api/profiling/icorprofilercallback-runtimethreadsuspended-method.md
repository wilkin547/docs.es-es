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
ms.openlocfilehash: 509d6cd2e65c2eb8c92f6d79deae9e01e75298f6
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74433445"
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
  
## <a name="remarks"></a>Comentarios  
 La notificación de `RuntimeThreadSuspended` puede producirse en cualquier momento entre el [ICorProfilerCallback:: runtimesuspendstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) y las devoluciones de llamada [ICorProfilerCallback:: RuntimeResumeStarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) asociadas. Las notificaciones que se producen entre [ICorProfilerCallback:: RuntimeSuspendFinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y `RuntimeResumeStarted` son para los subprocesos que se ejecutaron en código no administrado y se suspendieron en la entrada al tiempo de ejecución.  
  
 Normalmente, esta devolución de llamada se produce justo después de suspender un subproceso. Sin embargo, si el subproceso que se está ejecutando actualmente (el subproceso que llamó a esta devolución de llamada) es el que se está suspendiendo, esta devolución de llamada se producirá justo antes de que se suspenda el subproceso.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)
- [RuntimeThreadResumed (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimethreadresumed-method.md)
