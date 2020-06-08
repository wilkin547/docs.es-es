---
title: ICorProfilerCallback6 (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback6
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: edc420b7-96d1-4dec-ace0-36d907f644bc
topic_type:
- apiref
ms.openlocfilehash: 0156a7dfa2a67ce9e62b502df00fc6bc5fccf925
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499186"
---
# <a name="icorprofilercallback6-interface"></a>ICorProfilerCallback6 (Interfaz)
[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
 Una subclase de [ICorProfilerCallback5](icorprofilercallback5-interface.md) que proporciona un método de devolución de llamada que el Common Language Runtime utiliza para notificar a un generador de perfiles que se está cargando un ensamblado.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAssemblyReferences (método)](icorprofilercallback6-getassemblyreferences-method.md)|Notifica al generador de perfiles que un ensamblado está en una etapa de carga muy temprana, cuando Common Language Runtime realiza un rastreo de cierre de referencias de ensamblado.|  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Interfaces para generación de perfiles](profiling-interfaces.md)
