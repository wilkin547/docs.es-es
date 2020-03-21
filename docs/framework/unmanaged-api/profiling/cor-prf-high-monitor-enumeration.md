---
title: COR_PRF_HIGH_MONITOR (Enumeración)
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 5c6e34746368a7658c43fe0e2472000c29292569
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175218"
---
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR (Enumeración)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
Proporciona indicadores además de los que se encuentran en la [enumeración COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,
    COR_PRF_HIGH_DISABLE_TIERED_COMPILATION       = 0x00000008,
    COR_PRF_HIGH_BASIC_GC                         = 0x00000010,
    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS         = 0x00000020,
    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED    = 0x00000040,
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED |
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS |
                                                    COR_PRF_HIGH_BASIC_GC |
                                                    COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS |
                                                    COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = COR_PRF_HIGH_DISABLE_TIERED_COMPILATION  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a>Members  
  
|Member|Descripción|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|No se establecen marcas.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Controla la devolución de llamada [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) para agregar referencias de ensamblado durante el recorrido de cierre de referencia de ensamblado CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Controla la devolución de llamada [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) para obtener actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Controla la devolución de llamada [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) para indicar cuándo se ha recopilado y descargado un método dinámico. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|Sólo para .NET Core 3.0 y versiones posteriores: deshabilita la [compilación en niveles](../../../core/whats-new/dotnet-core-3-0.md) para los generadores de perfiles.|
|`COR_PRF_HIGH_BASIC_GC`|Sólo para .NET Core 3.0 y versiones posteriores: proporciona una opción de generación de perfiles de GC ligera en comparación con [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md). Controla solo las devoluciones de [llamada GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)y [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) . A `COR_PRF_MONITOR_GC` diferencia `COR_PRF_HIGH_BASIC_GC` de la marca, no deshabilita la recolección de elementos no utilizados simultánea.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|Sólo para .NET Core 3.0 y versiones posteriores: habilita las devoluciones de llamada [MovedReferences](icorprofilercallback-movedreferences-method.md) y [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) solo para compactar gCs.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|Sólo .NET Core 3.0 y [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)versiones posteriores: similar a , pero proporciona información sobre las asignaciones de objetos solo para el montón de objetos grandes (LOH).|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil. Corresponde a la `COR_PRF_REQUIRE_PROFILE_IMAGE` marca en el [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeración.|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización. Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.|  
  
## <a name="remarks"></a>Observaciones

Los `COR_PRF_HIGH_MONITOR` indicadores se `pdwEventsHigh` utilizan con el parámetro de la [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) y [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) métodos.  
  
A partir de .NET Framework 4.6.1, el valor del `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambio de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). A partir de .NET Framework 4.7.2, su valor cambió de `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` . `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`

`COR_PRF_HIGH_MONITOR_IMMUTABLE`está pensado para ser una máscara de bits que representa todas las marcas que solo se pueden establecer durante la inicialización. Intentar cambiar cualquiera de estas marcas en `HRESULT`otro lugar da como resultado un error .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
**Encabezado:** CorProf.idl, CorProf.h  
  
**Biblioteca:** CorGuids.lib  
  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [COR_PRF_MONITOR (enumeración)](cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5 (Interfaz)](icorprofilerinfo5-interface.md)
