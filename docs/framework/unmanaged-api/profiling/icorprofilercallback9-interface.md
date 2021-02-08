---
description: 'Más información acerca de: interfaz ICorProfilerCallback9'
title: Interfaz ICorProfilerCallback9
ms.date: 04/10/2018
api_name:
- ICorProfilerCallback9
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.openlocfilehash: 4bfcaf6f8985909ef9142ef4d08535a19facd7e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781654"
---
# <a name="icorprofilercallback9-interface"></a>Interfaz ICorProfilerCallback9

[Se admite en el .NET Framework 4.7.2 y versiones posteriores]  

 Una subclase de [ICorProfilerCallback8](icorprofilercallback8-interface.md) que proporciona un método de devolución de llamada usado por el Common Language Runtime para notificar al generador de perfiles que se ha recolectado un método dinámico y que se ha descargado posteriormente.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método DynamicMethodUnloaded](ICorProfilerCallback9-dynamicmethodunloaded-method.md)|Notifica al generador de perfiles que un método dinámico se ha recolectado como elemento no utilizado y se ha descargado posteriormente.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  

## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [Interfaz ICorProfilerCallback8](icorprofilercallback9-interface.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationStarted, método](icorprofilercallback8-dynamicmethodjitcompilationstarted-method.md)
- [ICorProfilerCallback8. DynamicMethodJITCompilationFinished, método](icorprofilercallback8-dynamicmethodjitcompilationfinished-method.md)
