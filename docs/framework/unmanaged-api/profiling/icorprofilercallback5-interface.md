---
title: ICorProfilerCallback5 (interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback5
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback5
helpviewer_keywords: ICorProfilerCallback5 interface [.NET Framework profiling]
ms.assetid: 61d2e9ef-5f1f-4771-8847-239616e35d84
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1a862707dc64efbf3a9b1604a0e6a4ff1be81b43
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback5-interface"></a>ICorProfilerCallback5 (interfaz)
Proporciona información para ayudar a un generador de perfiles a identificar el cierre completo de objetos activos, cuando se usa con la [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) o [ICorProfilerCallback2:: Rootreferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-rootreferences2-method.md)método junto con el [ICorProfilerCallback:: ObjectReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-objectreferences-method.md) y [ConditionalWeakTableElementReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md) métodos.  
  
 Un generador de perfiles de memoria administrado debe implementar `ICorProfilerCallback5` para suscribirse a las notificaciones relativas a los controladores de dependencia.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[ConditionalWeakTableElementReferences (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback5-conditionalweaktableelementreferences-method.md)|Identifica el cierre transitivo de los objetos a los que esas raíces hacen referencia mediante referencias directas de campo de miembro y mediante dependencias `ConditionalWeakTable`.|  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
