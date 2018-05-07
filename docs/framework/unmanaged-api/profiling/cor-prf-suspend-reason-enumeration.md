---
title: COR_PRF_SUSPEND_REASON (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_SUSPEND_REASON
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_SUSPEND_REASON
helpviewer_keywords:
- COR_PRF_SUSPEND_REASON enumeration [.NET Framework profiling]
ms.assetid: 75594833-bed3-47b2-a426-b75c5fe6fbcf
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f4382c7fa85008de9e67ad21c467402bae4ac90
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="corprfsuspendreason-enumeration"></a>COR_PRF_SUSPEND_REASON (Enumeración)
Indica la razón por la que se suspende el tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
typedef enum {  
    COR_PRF_SUSPEND_OTHER                   = 0x00,  
    COR_PRF_SUSPEND_FOR_GC                  = 0x01,  
    COR_PRF_SUSPEND_FOR_APPDOMAIN_SHUTDOWN  = 0x02,  
    COR_PRF_SUSPEND_FOR_CODE_PITCHING       = 0x03,  
    COR_PRF_SUSPEND_FOR_SHUTDOWN            = 0x04,  
    COR_PRF_SUSPEND_FOR_INPROC_DEBUGGER     = 0x06,  
    COR_PRF_SUSPEND_FOR_GC_PREP             = 0x07,    COR_PRF_SUSPEND_FOR_REJIT               = 8  
} COR_PRF_SUSPEND_REASON;  
```  
  
## <a name="members"></a>Miembros  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|El tiempo de ejecución se suspende por un motivo no especificado.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|El tiempo de ejecución se suspende para atender una solicitud de recopilación de elementos no utilizados.<br /><br /> Las devoluciones de llamada relacionadas con la recopilación de elementos no utilizados se producen entre el [ICorProfilerCallback:: RuntimeSuspendFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md) y [ICorProfilerCallback:: RuntimeResumeStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimeresumestarted-method.md) las devoluciones de llamada.|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|El tiempo de ejecución se suspende para que un `AppDomain` puede cerrarse.<br /><br /> Mientras se suspende el tiempo de ejecución, el tiempo de ejecución determinará qué subprocesos están en el `AppDomain` es decir que se va a cerrar y configúrelos para que se anulen cuando se reanuden. No hay ningún `AppDomain`-devoluciones de llamada específicas durante esta suspensión.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|El tiempo de ejecución se suspende para que puedan realizarse la eliminación de código nativo.<br /><br /> Eliminación de código nativo que habrá trastornos solo cuando el compilador de just-in-time (JIT) está activo con la eliminación de código nativo habilitada. Código de eliminación de devoluciones de llamada que se producen entre el `ICorProfilerCallback::RuntimeSuspendFinished` y `ICorProfilerCallback::RuntimeResumeStarted` las devoluciones de llamada. **Nota:** CLR JIT no las funciones de eliminación en .NET Framework versión 2.0, por lo que este valor no se utiliza en 2.0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|El tiempo de ejecución se suspende para que puede apagar. Deben suspender todos los subprocesos para completar la operación.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|El tiempo de ejecución se suspende para la depuración en curso.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|El tiempo de ejecución se suspende para prepararse para una colección de elementos no utilizados.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|El tiempo de ejecución se suspende para la recompilación con JIT.|  
  
## <a name="remarks"></a>Comentarios  
 Para continuar la ejecución hasta que intentan volver a escribir el tiempo de ejecución, momento en que también se suspenderán hasta que el tiempo de ejecución se reanuda, se permiten todos los subprocesos en tiempo de ejecución que están en código no administrado. Esto también se aplica a nuevos subprocesos que entran en el tiempo de ejecución. Todos los subprocesos en tiempo de ejecución se suspende inmediatamente si están en código interrumpible o solicita su suspensión cuando alcanzan código interrumpible.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Enumeraciones para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
