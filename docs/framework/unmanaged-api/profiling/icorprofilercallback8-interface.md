---
title: Interfaz ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 617b27923e96d9abc62ccbf158b076c6e45b20a8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175101"
---
# <a name="icorprofilercallback8-interface"></a>Interfaz ICorProfilerCallback8
[Soportado en .NET Framework 4.7 y versiones posteriores]  

 Subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada utilizados por Common Language Runtime para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DynamicMethodJITCompilationStarted (método)](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.|  
|[DynamicMethodJITCompilationFinished (método)](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Notifica al generador de perfiles que la compilación JIT de un método dinámico ha finalizado.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback9 (interfaz)](icorprofilercallback9-interface.md)
