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
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="18667-102">COR_PRF_HIGH_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="18667-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="18667-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="18667-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="18667-104">Proporciona indicadores además de los que se encuentran en la [enumeración COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="18667-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18667-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="18667-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="18667-106">Members</span><span class="sxs-lookup"><span data-stu-id="18667-106">Members</span></span>  
  
|<span data-ttu-id="18667-107">Member</span><span class="sxs-lookup"><span data-stu-id="18667-107">Member</span></span>|<span data-ttu-id="18667-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="18667-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="18667-109">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="18667-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="18667-110">Controla la devolución de llamada [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) para agregar referencias de ensamblado durante el recorrido de cierre de referencia de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="18667-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="18667-111">Controla la devolución de llamada [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) para obtener actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="18667-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="18667-112">Controla la devolución de llamada [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) para indicar cuándo se ha recopilado y descargado un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="18667-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="18667-113">Sólo para .NET Core 3.0 y versiones posteriores: deshabilita la [compilación en niveles](../../../core/whats-new/dotnet-core-3-0.md) para los generadores de perfiles.</span><span class="sxs-lookup"><span data-stu-id="18667-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="18667-114">Sólo para .NET Core 3.0 y versiones posteriores: proporciona una opción de generación de perfiles de GC ligera en comparación con [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="18667-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="18667-115">Controla solo las devoluciones de [llamada GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md)y [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="18667-115">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="18667-116">A `COR_PRF_MONITOR_GC` diferencia `COR_PRF_HIGH_BASIC_GC` de la marca, no deshabilita la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="18667-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="18667-117">Sólo para .NET Core 3.0 y versiones posteriores: habilita las devoluciones de llamada [MovedReferences](icorprofilercallback-movedreferences-method.md) y [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) solo para compactar gCs.</span><span class="sxs-lookup"><span data-stu-id="18667-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="18667-118">Sólo .NET Core 3.0 y [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md)versiones posteriores: similar a , pero proporciona información sobre las asignaciones de objetos solo para el montón de objetos grandes (LOH).</span><span class="sxs-lookup"><span data-stu-id="18667-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="18667-119">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="18667-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="18667-120">Corresponde a la `COR_PRF_REQUIRE_PROFILE_IMAGE` marca en el [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="18667-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="18667-121">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="18667-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="18667-122">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="18667-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="18667-123">Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="18667-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="18667-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="18667-124">Remarks</span></span>

<span data-ttu-id="18667-125">Los `COR_PRF_HIGH_MONITOR` indicadores se `pdwEventsHigh` utilizan con el parámetro de la [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) y [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="18667-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="18667-126">A partir de .NET Framework 4.6.1, el valor del `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambio de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="18667-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="18667-127">A partir de .NET Framework 4.7.2, su valor cambió de `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` . `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`</span><span class="sxs-lookup"><span data-stu-id="18667-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="18667-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE`está pensado para ser una máscara de bits que representa todas las marcas que solo se pueden establecer durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="18667-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="18667-129">Intentar cambiar cualquiera de estas marcas en `HRESULT`otro lugar da como resultado un error .</span><span class="sxs-lookup"><span data-stu-id="18667-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="18667-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="18667-130">Requirements</span></span>

<span data-ttu-id="18667-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="18667-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="18667-132">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="18667-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="18667-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="18667-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="18667-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18667-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18667-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="18667-135">See also</span></span>

- [<span data-ttu-id="18667-136">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="18667-136">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="18667-137">COR_PRF_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="18667-137">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="18667-138">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="18667-138">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
