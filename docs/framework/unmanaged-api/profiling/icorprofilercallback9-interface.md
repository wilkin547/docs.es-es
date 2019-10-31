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
ms.openlocfilehash: c383a2e221e61770d3c28a65c561c48f6059b6d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136565"
---
# <a name="icorprofilercallback9-interface"></a>Interfaz ICorProfilerCallback9
[Se admite en el .NET Framework 4.7.2 y versiones posteriores]  

 Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada usado por el Common Language Runtime para notificar al generador de perfiles que se ha recolectado un método dinámico y que se ha descargado posteriormente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DynamicMethodUnloaded (método)](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Notifica al generador de perfiles que un método dinámico se ha recolectado como elemento no utilizado y se ha descargado posteriormente.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
