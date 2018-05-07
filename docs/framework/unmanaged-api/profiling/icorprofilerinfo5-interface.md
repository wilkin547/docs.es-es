---
title: ICorProfilerInfo5 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo5
api_location:
- mscorwks.dll
api_type:
- COM
ms.assetid: 7bd48c34-37ed-4230-9eec-39a17280f05d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ba082182ec7e2f639ef94baeb29203ee792fba0
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilerinfo5-interface"></a>ICorProfilerInfo5 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Una subclase de [ICorProfilerInfo4](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md) que proporciona métodos que pueden para utilizar los generadores de perfiles de código para comunicarse con common language runtime (CLR) para controlar la supervisión de eventos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md)|Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de CLR.|  
|[SetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)|Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde CLR.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos disponibles en esta interfaz están diseñados para reemplazar la [ICorProfilerInfo:: GetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) métodos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces para generación de perfiles](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
