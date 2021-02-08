---
description: 'Más información acerca de: interfaz ICorProfilerCallback8'
title: Interfaz ICorProfilerCallback8
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback8
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 8dd9b8eea82f38b7598d578bd718743af826070d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781680"
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

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback9](icorprofilercallback9-interface.md)
