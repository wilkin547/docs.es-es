---
description: 'Más información acerca de: enumeración COR_PRF_HIGH_MONITOR'
title: COR_PRF_HIGH_MONITOR (Enumeración)
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: 800bad21af96d8bbdf73f2af799f474f11294705
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99648771"
---
# <a name="cor_prf_high_monitor-enumeration"></a>COR_PRF_HIGH_MONITOR (Enumeración)

[Compatible con .NET Framework 4.5.2 y versiones posteriores]  
  
Proporciona marcas además de las que se encuentran en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el método [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.  
  
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
  
|Miembro|Descripción|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|No se establecen marcas.|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|Controla la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) para agregar referencias de ensamblado durante el recorrido de cierre de referencia de ensamblado de CLR.|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|Controla la devolución de llamada [ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) para las actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|Controla la devolución de llamada [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) para indicar cuándo se ha recolectado y descargado un método dinámico. <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|Solo .NET Core 3,0 y versiones posteriores: deshabilita la [compilación en capas](../../../core/whats-new/dotnet-core-3-0.md) para los perfiles.|
|`COR_PRF_HIGH_BASIC_GC`|Solo .NET Core 3,0 y versiones posteriores: proporciona una opción de generación de perfiles de GC ligera en comparación con [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md) . Controla solo las devoluciones de llamada  [garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md), [garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md)y [getgenerationbounds (](icorprofilerinfo2-getgenerationbounds-method.md) . A diferencia de la `COR_PRF_MONITOR_GC` marca, no `COR_PRF_HIGH_BASIC_GC` deshabilita la recolección de elementos no utilizados simultánea.|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|Solo .NET Core 3,0 y versiones posteriores: habilita las devoluciones de llamada [MovedReferences](icorprofilercallback-movedreferences-method.md) y [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) para compactar solo GC.|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|Solo .NET Core 3,0 y versiones posteriores: similar a [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md) , pero proporciona información sobre las asignaciones de objetos solo para el montón de objetos grandes (montón).|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil. Corresponde a la `COR_PRF_REQUIRE_PROFILE_IMAGE` marca de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización. Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.|  
  
## <a name="remarks"></a>Observaciones

Las `COR_PRF_HIGH_MONITOR` marcas se usan con el `pdwEventsHigh` parámetro de los métodos [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) y [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .  
  
A partir de la .NET Framework 4.6.1, el valor de `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambia de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002). A partir de la .NET Framework 4.7.2, su valor cambió de `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS` .

`COR_PRF_HIGH_MONITOR_IMMUTABLE` está diseñado para ser una máscara de máscara que representa todas las marcas que solo se pueden establecer durante la inicialización. Al intentar cambiar cualquiera de estas marcas en otro lugar, se produce un error `HRESULT` .

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
**Encabezado:** CorProf.idl, CorProf.h  
  
**Biblioteca:** CorGuids.lib  
  
**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Enumeraciones para generación de perfiles](profiling-enumerations.md)
- [COR_PRF_MONITOR (Enumeración)](cor-prf-monitor-enumeration.md)
- [ICorProfilerInfo5 (Interfaz)](icorprofilerinfo5-interface.md)
