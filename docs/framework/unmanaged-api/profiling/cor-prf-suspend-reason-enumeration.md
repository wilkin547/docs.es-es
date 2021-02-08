---
description: 'Más información acerca de: enumeración COR_PRF_SUSPEND_REASON'
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
ms.openlocfilehash: 9e8b3dc98aa6b1a989088f5f4d0efb74d488d927
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789013"
---
# <a name="cor_prf_suspend_reason-enumeration"></a>COR_PRF_SUSPEND_REASON (Enumeración)

Indica la razón por la que se suspende el tiempo de ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
  
## <a name="members"></a>Members  
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_FIELD_SUSPEND_OTHER`|El tiempo de ejecución se suspende por una razón no especificada.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC`|El tiempo de ejecución se suspende para atender una solicitud de recolección de elementos no utilizados.<br /><br /> Las devoluciones de llamada relacionadas con la recolección de elementos no utilizados se producen entre las devoluciones de llamada [ICorProfilerCallback:: RuntimeSuspendFinished (](icorprofilercallback-runtimesuspendfinished-method.md) y [ICorProfilerCallback:: RuntimeResumeStarted (](icorprofilercallback-runtimeresumestarted-method.md) .|  
|`COR_PRF_FIELD_SUSPEND_FOR_APPDOMAIN_SHUTDOWN`|El tiempo de ejecución se suspende para que `AppDomain` se pueda cerrar.<br /><br /> Mientras se suspende el tiempo de ejecución, el tiempo de ejecución determinará qué subprocesos se encuentran en el `AppDomain` que se está cerrando y los definirá para que se anulen cuando se reanuden. No hay `AppDomain` devoluciones de llamada específicas de esta suspensión.|  
|`COR_PRF_FIELD_SUSPEND_FOR_CODE_PITCHING`|El tiempo de ejecución se suspende para que pueda producirse el paso del código.<br /><br /> El paso de código solo se retiene cuando el compilador Just-in-Time (JIT) está activo con la eliminación de código habilitada. Las devoluciones de llamada de paso de código se producen entre las `ICorProfilerCallback::RuntimeSuspendFinished` `ICorProfilerCallback::RuntimeResumeStarted` devoluciones de llamada y. **Nota:**  CLR JIT no realiza el paso de las funciones de la versión 2,0 de .NET Framework, por lo que este valor no se utiliza en 2,0.|  
|`COR_PRF_FIELD_SUSPEND_FOR_SHUTDOWN`|El tiempo de ejecución se suspende para que pueda cerrarse. Debe suspender todos los subprocesos para completar la operación.|  
|`COR_PRF_FIELD_SUSPEND_FOR_INPROC_DEBUGGER`|El tiempo de ejecución se suspende para la depuración en proceso.|  
|`COR_PRF_FIELD_SUSPEND_FOR_GC_PREP`|El tiempo de ejecución se suspende para prepararse para una recolección de elementos no utilizados.|  
|`COR_PRF_SUSPEND_FOR_REJIT`|El tiempo de ejecución se suspende para la recompilación JIT.|  
  
## <a name="remarks"></a>Observaciones  

 Todos los subprocesos en tiempo de ejecución que se encuentran en código no administrado pueden continuar ejecutándose hasta que intenten volver a entrar en el tiempo de ejecución, momento en el que también se suspenderán hasta que se reanude el tiempo de ejecución. Esto también se aplica a los nuevos subprocesos que entran en el tiempo de ejecución. Todos los subprocesos del tiempo de ejecución se suspenden inmediatamente si están en código interrumpido o se le piden que se suspendan cuando llegan a código interrumpido.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
