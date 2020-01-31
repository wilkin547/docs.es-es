---
title: ICorProfilerCallback5 (interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback5
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback5
helpviewer_keywords:
- ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type:
- apiref
ms.openlocfilehash: 7981e7d2d2a4588e56d3c30d0ede2d003fdcd32e
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76865030"
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5 (interfaz)
Complementa la información para ayudar a un generador de perfiles a identificar el cierre completo de los objetos activos, cuando se usa con el método [ICorProfilerCallback:: RootReferences](icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: RootReferences2 (](icorprofilercallback2-rootreferences2-method.md) junto con los métodos [ICorProfilerCallback:: ObjectReferences](icorprofilercallback-objectreferences-method.md) y [conditionalweaktableelementreferences (](icorprofilercallback5-conditionalweaktableelementreferences-method.md) .  
  
 Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.  
  
## <a name="remarks"></a>Notas  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences (método)](icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.|  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerCallback2 (interfaz)](icorprofilercallback2-interface.md)
