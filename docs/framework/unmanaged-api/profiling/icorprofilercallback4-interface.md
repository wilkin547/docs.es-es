---
title: ICorProfilerCallback4 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback4
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback4
helpviewer_keywords:
- ICorProfilerCallback4 interface [.NET Framework profiling]
ms.assetid: 665f3cfc-cd6f-4880-906c-ea65ad384783
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3eb1f46900199db65be5d14c56bfc0b6f55bf269
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205139"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4 (Interfaz)
Proporciona métodos de devolución de llamada que common language runtime (CLR) se usa para comunicar información al generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReJITParameters](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-getrejitparameters-method.md)|Permite al analizador de código establecer las marcas de generación de código alternativa para un nuevo cuerpo de método ha vuelto a compilar.|  
|[Método MovedReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-movedreferences2-method.md)|Informa de la nueva disposición de los objetos del montón como resultado de una recolección de elementos no utilizados con compactación.|  
|[Método ReJITCompilationFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador de just-in-time (JIT) ha terminado la recompilación de una función.|  
|[Método ReJITCompilationStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejitcompilationstarted-method.md)|Notifica al generador de perfiles que se ha iniciado el compilador de just-in-time (JIT) volver a compilar una función.|  
|[Método ReJITError](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-rejiterror-method.md)|Notifica un error al procesar una solicitud de recompilación.|  
|[Método SurvivingReferences2](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-survivingreferences2-method.md)|Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback2 (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo (Interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
