---
description: 'Más información sobre: ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)'
title: 'ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)'
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
ms.openlocfilehash: 74adf7edc5269824a924933eb3284a5964e1bac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781732"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a>ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)

[Compatible con .NET Framework 4.6.1 y versiones posteriores]  
  
 Notifica al generador de perfiles cada vez que se actualiza la secuencia de símbolos asociada a un módulo en memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 [in] `moduleId`  
 Identificador del módulo en memoria cuya secuencia de símbolos se actualiza.  
  
## <a name="remarks"></a>Observaciones  

 Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Este evento no se genera actualmente para símbolos creados o modificados implícitamente mediante <xref:System.Reflection.Emit> API.  
  
 Incluso cuando se proporcionan símbolos por adelantado en una llamada a una de las sobrecargas de los <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> métodos administrados que incluyen un `rawSymbolStore` argumento para especificar los símbolos del ensamblado, es posible que el tiempo de ejecución no asocie realmente los datos simbólicos con el módulo hasta después de que se haya producido la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) . Este evento proporciona una oportunidad posterior para recopilar símbolos para estos módulos.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 (método)](icorprofilerinfo5-seteventmask2-method.md)
- [Interfaz ICorProfilerCallback7](icorprofilercallback7-interface.md)
