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
ms.openlocfilehash: 82f6262c2c576b49be4e7fcaa14043950df4c67a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84495632"
---
# <a name="icorprofilerinfo5-interface"></a>ICorProfilerInfo5 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Subclase de [ICorProfilerInfo4](icorprofilerinfo4-interface.md) que proporciona métodos para que los profileres de código puedan usar para comunicarse con el Common Language Runtime (CLR) para controlar la supervisión de eventos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetEventMask2 (método)](icorprofilerinfo5-geteventmask2-method.md)|Obtiene las categorías de eventos actuales para las que el generador de perfiles quiere recibir notificaciones de CLR.|  
|[SetEventMask2 (método)](icorprofilerinfo5-seteventmask2-method.md)|Establece un valor que especifica los tipos de eventos para los que el generador de perfiles quiere recibir notificaciones de eventos desde CLR.|  
  
## <a name="remarks"></a>Comentarios  
 Los métodos disponibles en esta interfaz están diseñados para reemplazar los métodos [ICorProfilerInfo:: GetEventMask (](icorprofilerinfo-geteventmask-method.md) y [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces para generación de perfiles](profiling-interfaces.md)
