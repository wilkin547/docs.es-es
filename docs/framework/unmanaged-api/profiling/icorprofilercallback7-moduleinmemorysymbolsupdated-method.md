---
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
ms.openlocfilehash: f6dd10d196ffd3a653584e1bc8d1a5643850bc33
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136604"
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
  
## <a name="remarks"></a>Comentarios  
 Esta devolución de llamada se controla estableciendo la marca de máscara de evento [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) cuando se llama al método [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .  
  
> [!NOTE]
> Este evento no se genera actualmente para los símbolos creados o modificados implícitamente mediante <xref:System.Reflection.Emit> API.  
  
 Incluso cuando se proporcionan símbolos por adelantado en una llamada a una de las sobrecargas de los métodos de <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> administrados que incluyen un argumento de `rawSymbolStore` para especificar los símbolos del ensamblado, es posible que el tiempo de ejecución no asocie realmente los datos simbólicos con el módulo hasta después de la Se ha producido una devolución de llamada [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) . Este evento proporciona una oportunidad posterior para recopilar símbolos para estos módulos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorProf.idl, CorProf.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ModuleLoadFinished (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [SetEventMask2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [ICorProfilerCallback7 (interfaz)](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
