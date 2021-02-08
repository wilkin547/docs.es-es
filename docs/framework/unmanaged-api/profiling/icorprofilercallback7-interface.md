---
description: 'Más información acerca de: interfaz ICorProfilerCallback7'
title: Interfaz ICorProfilerCallback7
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: a0be019e-aaa1-4036-990f-565f114d4b5c
ms.openlocfilehash: 3db402db221fca4487939f9817b20ec0c5207fc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781745"
---
# <a name="icorprofilercallback7-interface"></a>Interfaz ICorProfilerCallback7

[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Una subclase de [ICorProfilerCallback6](icorprofilercallback6-interface.md) que proporciona un método de devolución de llamada que Common Language Runtime utiliza para notificar al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md)|Notifica al generador de perfiles que se ha actualizado la secuencia de símbolos asociada a un módulo en memoria.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Interfaces para generación de perfiles](profiling-interfaces.md)
