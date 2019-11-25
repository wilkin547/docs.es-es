---
title: COR_PRF_HIGH_MONITOR (Enumeración)
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
ms.openlocfilehash: fc0251624738a06d1be7081ebd099e97f7278a15
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283139"
---
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="92bae-102">COR_PRF_HIGH_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="92bae-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="92bae-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="92bae-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="92bae-104">Proporciona otras marcas, además de las que se encuentran en la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md), que el generador de perfiles puede especificar al método [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="92bae-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="92bae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92bae-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="92bae-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="92bae-106">Members</span></span>  
  
|<span data-ttu-id="92bae-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="92bae-107">Member</span></span>|<span data-ttu-id="92bae-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="92bae-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="92bae-109">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="92bae-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="92bae-110">Controla la devolución de llamada [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) para agregar referencias de ensamblado durante el rastreo de cierre de referencias de ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="92bae-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="92bae-111">Controla la devolución de llamada [ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) para las actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="92bae-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="92bae-112">Controla la devolución de llamada [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) para indicar cuándo se ha recolectado y descargado un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="92bae-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="92bae-113">Solo .NET Core 3,0 y versiones posteriores: deshabilita la [compilación en capas](../../../core/whats-new/dotnet-core-3-0.md) para los perfiles.</span><span class="sxs-lookup"><span data-stu-id="92bae-113">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="92bae-114">Solo .NET Core 3,0 y versiones posteriores: proporciona una opción de generación de perfiles de GC ligera en comparación con [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="92bae-114">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="92bae-115">Controla solo las devoluciones de llamada [garbagecollectionstarted (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [garbagecollectionfinished (](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md)y [getgenerationbounds (](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="92bae-115">Controls only the  [GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="92bae-116">A diferencia de la marca de `COR_PRF_MONITOR_GC`, `COR_PRF_HIGH_BASIC_GC` no deshabilita la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="92bae-116">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="92bae-117">Solo .NET Core 3,0 y versiones posteriores: habilita las devoluciones de llamada [MovedReferences](icorprofilercallback-movedreferences-method.md) y [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) para compactar solo GC.</span><span class="sxs-lookup"><span data-stu-id="92bae-117">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="92bae-118">Solo .NET Core 3,0 y versiones posteriores: similar a [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), pero proporciona información sobre las asignaciones de objetos solo para el montón de objetos grandes (montón).</span><span class="sxs-lookup"><span data-stu-id="92bae-118">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="92bae-119">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="92bae-119">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="92bae-120">Se corresponde con la marca `COR_PRF_REQUIRE_PROFILE_IMAGE` de la enumeración [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md).</span><span class="sxs-lookup"><span data-stu-id="92bae-120">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="92bae-121">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="92bae-121">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="92bae-122">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="92bae-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="92bae-123">Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="92bae-123">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="92bae-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="92bae-124">Remarks</span></span>

<span data-ttu-id="92bae-125">Las marcas `COR_PRF_HIGH_MONITOR` se usan con el parámetro `pdwEventsHigh` de los métodos [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) y [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md).</span><span class="sxs-lookup"><span data-stu-id="92bae-125">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="92bae-126">A partir de la .NET Framework 4.6.1, el valor de la `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambiar de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="92bae-126">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="92bae-127">A partir de la .NET Framework 4.7.2, su valor cambió de `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="92bae-127">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

<span data-ttu-id="92bae-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` está diseñada para ser una máscara de máscara que representa todas las marcas que solo se pueden establecer durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="92bae-128">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="92bae-129">Al intentar cambiar cualquiera de estas marcas en otro lugar, se produce un error `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="92bae-129">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="92bae-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92bae-130">Requirements</span></span>

<span data-ttu-id="92bae-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92bae-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="92bae-132">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="92bae-132">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="92bae-133">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="92bae-133">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="92bae-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="92bae-134">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92bae-135">Vea también</span><span class="sxs-lookup"><span data-stu-id="92bae-135">See also</span></span>

- [<span data-ttu-id="92bae-136">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="92bae-136">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="92bae-137">COR_PRF_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="92bae-137">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="92bae-138">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="92bae-138">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
