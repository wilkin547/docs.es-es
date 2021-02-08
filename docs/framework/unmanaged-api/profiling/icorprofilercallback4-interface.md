---
description: 'Más información acerca de: interfaz ICorProfilerCallback4'
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
ms.openlocfilehash: 882f234cb94ccd65203b42ed213aab6355250af8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99788753"
---
# <a name="icorprofilercallback4-interface"></a>ICorProfilerCallback4 (Interfaz)

Proporciona métodos de devolución de llamada que el Common Language Runtime (CLR) utiliza para comunicar información al generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetReJITParameters](icorprofilercallback4-getrejitparameters-method.md)|Permite que el generador de perfiles de código establezca marcas de generación de código alternativas para un nuevo cuerpo de método recompilado.|  
|[Método MovedReferences2](icorprofilercallback4-movedreferences2-method.md)|Informa del nuevo diseño de objetos del montón como resultado de una recolección de elementos no utilizados de compactación.|  
|[Método ReJITCompilationFinished](icorprofilercallback4-rejitcompilationfinished-method.md)|Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha terminado de volver a compilar una función.|  
|[Método ReJITCompilationStarted](icorprofilercallback4-rejitcompilationstarted-method.md)|Notifica al generador de perfiles que el compilador Just-in-Time (JIT) ha empezado a volver a compilar una función.|  
|[Método ReJITError](icorprofilercallback4-rejiterror-method.md)|Informa de un error detectado durante el procesamiento de una solicitud de recompilación.|  
|[Método SurvivingReferences2](icorprofilercallback4-survivingreferences2-method.md)|Informa del diseño de objetos del montón como resultado de una recolección de elementos no utilizados sin compactación.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICorProfilerCallback2 (Interfaz)](icorprofilercallback2-interface.md)
- [Interfaces para generación de perfiles](profiling-interfaces.md)
- [ICorProfilerInfo (Interfaz)](icorprofilerinfo-interface.md)
