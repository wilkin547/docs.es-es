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
ms.openlocfilehash: e1711def5e2aa41fd63912361ef8250ad160fb88
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61991996"
---
# <a name="icorprofilercallback9-interface"></a>Interfaz ICorProfilerCallback9
[Compatible con .NET Framework 4.7.2 y versiones posteriores]  

 Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada que common language runtime utilizado para notificar al generador de perfiles que un método dinámico ha sido recolectado y posteriormente descargan.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[DynamicMethodUnloaded (método)](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Notifica al generador de perfiles que un método dinámico se ha recolectado y posteriormente descargan.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback8 (interfaz)](icorprofilercallback9-interface.md)
- [Método ICorProfilerCallback8.DynamicMethodJITCompilationStarted](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [Método ICorProfilerCallback8.DynamicMethodJITCompilationFinished](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
