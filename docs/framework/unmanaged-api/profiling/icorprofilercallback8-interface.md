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
ms.openlocfilehash: 22a133d02bb69026190428905379323362943d40
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732390"
---
# <a name="icorprofilercallback8-interface"></a>Interfaz ICorProfilerCallback8

[Se admite en el .NET Framework 4,7 y versiones posteriores]  

 Subclase de [ICorProfilerCallback7](icorprofilercallback7-interface.md) que proporciona métodos de devolución de llamada utilizados por el Common Language Runtime para notificar al generador de perfiles que la compilación JIT de un método dinámico se ha iniciado y finalizado.
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado la compilación JIT de un método dinámico.|  
|[Método DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)|Notifica al generador de perfiles que ha finalizado la compilación JIT de un método dinámico.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Consulte también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md)
