---
title: ICorProfilerCallback3 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback3
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback3
helpviewer_keywords:
- ICorProfilerCallback3 interface [.NET Framework profiling]
ms.assetid: be83af41-3dec-4c77-8529-9dd6b8042af6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66e6a67ce022365fa8c9e1005dfecbe4b23abd10
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59158390"
---
# <a name="icorprofilercallback3-interface"></a>ICorProfilerCallback3 (Interfaz)
Proporciona métodos de devolución de llamada que common language runtime (CLR) se usa para comunicarse adjuntar y separar la información de estado en el generador de perfiles.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[InitializeForAttach (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-initializeforattach-method.md)|Lo llama el CLR para dar al generador de perfiles una oportunidad de inicializar su estado después de una operación de asociación.|  
|[ProfilerAttachComplete (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerattachcomplete-method.md)|Lo llama el CLR para indicar que el generador de perfiles puede llamar ahora a los métodos de puesta al día.|  
|[ProfilerDetachSucceeded (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback3-profilerdetachsucceeded-method.md)|Notifica al generador de perfiles que Common Language Runtime (CLR) está a punto de descargar el archivo DLL del generador de perfiles.|  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [ICorProfilerInfo (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [ICorProfilerCallback2 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)
- [ICorProfilerCallback4 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback4-interface.md)
