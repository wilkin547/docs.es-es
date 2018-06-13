---
title: ICorProfilerCallback::RuntimeSuspendFinished (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.RuntimeSuspendFinished
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendFinished method [.NET Framework profiling]
- RuntimeSuspendFinished method [.NET Framework profiling]
ms.assetid: b7723f58-c55c-4399-9972-1bbf3b866694
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0b243c507171a4d907ef4594ae0c715a074c965a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33452223"
---
# <a name="icorprofilercallbackruntimesuspendfinished-method"></a>ICorProfilerCallback::RuntimeSuspendFinished (Método)
Notifica al generador de perfiles que el tiempo de ejecución ha finalizado la suspensión de todos los subprocesos en tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT RuntimeSuspendFinished();  
```  
  
## <a name="remarks"></a>Comentarios  
 Todos los subprocesos en tiempo de ejecución que están en código no administrado se pueden continuar ejecutándose hasta que intentan volver a escribir el tiempo de ejecución. En ese momento también se suspenderán hasta que el tiempo de ejecución se reanuda. Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución. Todos los subprocesos en el tiempo de ejecución están suspenden inmediatamente si ya están en código interrumpible, o se les solicita que se suspendan cuando alcanzan código interrumpible.  
  
 El `RuntimeSuspendFinished` devolución de llamada se garantiza que se producen en el mismo subproceso que el [ICorProfilerCallback:: RuntimeSuspendStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendstarted-method.md) devolución de llamada.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICorProfilerCallback (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)
