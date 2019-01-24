---
title: ICorProfilerCallback8 (interfaz)
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a3bdf79582619777a22c80caac5b4e90d603f3a8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54675020"
---
# <a name="icorprofilercallback8-interface"></a>ICorProfilerCallback8 (interfaz)
[Se admite en .NET Framework 4.7 y versiones posteriores]  

 Una subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada que common language runtime utilizados para notificar al generador de perfiles que se ha iniciado y finalizado la compilación JIT de un método dinámico. 
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.|  
|[DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback9 (interfaz)](icorprofilercallback9-interface.md)
