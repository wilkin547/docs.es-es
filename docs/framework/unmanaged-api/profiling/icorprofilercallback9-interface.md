---
title: Interfaz ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 488af069e7798fde650abb1473df256eed2d692f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallback9-interface"></a>Interfaz ICorProfilerCallback9
[Compatible con .NET Framework 4.7.2 y versiones posteriores]  

 Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada utilizado por common language runtime para notificar al generador de perfiles que un método dinámico ha sido recolectado y descargando posteriormente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DynamicMethodUnloaded (método)](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Notifica al generador de perfiles que un método dinámico se ha recolectado y descargando posteriormente.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vea también  
[Interfaces de generación de perfiles](profiling-interfaces.md)   
[Interfaz ICorProfilerCallback8](icorprofilercallback9-interface.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)   
[ICorProfilerCallback8.DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)   
