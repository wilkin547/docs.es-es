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
# <a name="cor_prf_high_monitor-enumeration"></a><span data-ttu-id="6f023-103">COR_PRF_HIGH_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6f023-103">COR_PRF_HIGH_MONITOR Enumeration</span></span>

<span data-ttu-id="6f023-104">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="6f023-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
<span data-ttu-id="6f023-105">Proporciona marcas además de las que se encuentran en la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) que el generador de perfiles puede especificar para el método [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="6f023-105">Provides flags in addition to those found in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f023-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6f023-106">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="6f023-107">Members</span><span class="sxs-lookup"><span data-stu-id="6f023-107">Members</span></span>  
  
|<span data-ttu-id="6f023-108">Miembro</span><span class="sxs-lookup"><span data-stu-id="6f023-108">Member</span></span>|<span data-ttu-id="6f023-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6f023-109">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="6f023-110">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="6f023-110">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="6f023-111">Controla la devolución de llamada [ICorProfilerCallback6:: GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) para agregar referencias de ensamblado durante el recorrido de cierre de referencia de ensamblado de CLR.</span><span class="sxs-lookup"><span data-stu-id="6f023-111">Controls the [ICorProfilerCallback6::GetAssemblyReference](icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="6f023-112">Controla la devolución de llamada [ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) para las actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="6f023-112">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="6f023-113">Controla la devolución de llamada [ICorProfilerCallback9::D ynamicmethodunloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) para indicar cuándo se ha recolectado y descargado un método dinámico.</span><span class="sxs-lookup"><span data-stu-id="6f023-113">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|
|`COR_PRF_HIGH_DISABLE_TIERED_COMPILATION`|<span data-ttu-id="6f023-114">Solo .NET Core 3,0 y versiones posteriores: deshabilita la [compilación en capas](../../../core/whats-new/dotnet-core-3-0.md) para los perfiles.</span><span class="sxs-lookup"><span data-stu-id="6f023-114">.NET Core 3.0 and later versions only: Disables [tiered compilation](../../../core/whats-new/dotnet-core-3-0.md) for profilers.</span></span>|
|`COR_PRF_HIGH_BASIC_GC`|<span data-ttu-id="6f023-115">Solo .NET Core 3,0 y versiones posteriores: proporciona una opción de generación de perfiles de GC ligera en comparación con [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6f023-115">.NET Core 3.0 and later versions only: Provides a lightweight GC profiling option compared to [`COR_PRF_MONITOR_GC`](cor-prf-monitor-enumeration.md).</span></span> <span data-ttu-id="6f023-116">Controla solo las devoluciones de llamada  [garbagecollectionstarted (](icorprofilercallback2-garbagecollectionstarted-method.md), [garbagecollectionfinished (](icorprofilercallback2-garbagecollectionfinished-method.md)y [getgenerationbounds (](icorprofilerinfo2-getgenerationbounds-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6f023-116">Controls only the  [GarbageCollectionStarted](icorprofilercallback2-garbagecollectionstarted-method.md), [GarbageCollectionFinished](icorprofilercallback2-garbagecollectionfinished-method.md), and [GetGenerationBounds](icorprofilerinfo2-getgenerationbounds-method.md) callbacks.</span></span> <span data-ttu-id="6f023-117">A diferencia de la `COR_PRF_MONITOR_GC` marca, no `COR_PRF_HIGH_BASIC_GC` deshabilita la recolección de elementos no utilizados simultánea.</span><span class="sxs-lookup"><span data-stu-id="6f023-117">Unlike the `COR_PRF_MONITOR_GC` flag, `COR_PRF_HIGH_BASIC_GC` does not disable concurrent garbage collection.</span></span>|
|`COR_PRF_HIGH_MONITOR_GC_MOVED_OBJECTS`|<span data-ttu-id="6f023-118">Solo .NET Core 3,0 y versiones posteriores: habilita las devoluciones de llamada [MovedReferences](icorprofilercallback-movedreferences-method.md) y [movedreferences2 (](icorprofilercallback4-movedreferences2-method.md) para compactar solo GC.</span><span class="sxs-lookup"><span data-stu-id="6f023-118">.NET Core 3.0 and later versions only: Enables the [MovedReferences](icorprofilercallback-movedreferences-method.md) and [MovedReferences2](icorprofilercallback4-movedreferences2-method.md) callbacks for compacting GCs only.</span></span>|
|`COR_PRF_HIGH_MONITOR_LARGEOBJECT_ALLOCATED`|<span data-ttu-id="6f023-119">Solo .NET Core 3,0 y versiones posteriores: similar a [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md) , pero proporciona información sobre las asignaciones de objetos solo para el montón de objetos grandes (montón).</span><span class="sxs-lookup"><span data-stu-id="6f023-119">.NET Core 3.0 and later versions only: Similar to [`COR_PRF_MONITOR_OBJECT_ALLOCATED`](cor-prf-monitor-enumeration.md), but provides information on object allocations for the large object heap (LOH) only.</span></span>|
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="6f023-120">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="6f023-120">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="6f023-121">Corresponde a la `COR_PRF_REQUIRE_PROFILE_IMAGE` marca de la enumeración [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="6f023-121">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="6f023-122">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="6f023-122">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="6f023-123">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="6f023-123">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="6f023-124">Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="6f023-124">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f023-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6f023-125">Remarks</span></span>

<span data-ttu-id="6f023-126">Las `COR_PRF_HIGH_MONITOR` marcas se usan con el `pdwEventsHigh` parámetro de los métodos [ICorProfilerInfo5:: GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) y [ICorProfilerInfo5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="6f023-126">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="6f023-127">A partir de la .NET Framework 4.6.1, el valor de `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambia de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span><span class="sxs-lookup"><span data-stu-id="6f023-127">Starting with the .NET Framework 4.6.1, the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="6f023-128">A partir de la .NET Framework 4.7.2, su valor cambió de `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS` .</span><span class="sxs-lookup"><span data-stu-id="6f023-128">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>

<span data-ttu-id="6f023-129">`COR_PRF_HIGH_MONITOR_IMMUTABLE` está diseñado para ser una máscara de máscara que representa todas las marcas que solo se pueden establecer durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="6f023-129">`COR_PRF_HIGH_MONITOR_IMMUTABLE` is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="6f023-130">Al intentar cambiar cualquiera de estas marcas en otro lugar, se produce un error `HRESULT` .</span><span class="sxs-lookup"><span data-stu-id="6f023-130">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="6f023-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6f023-131">Requirements</span></span>

<span data-ttu-id="6f023-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6f023-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
<span data-ttu-id="6f023-133">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6f023-133">**Header:** CorProf.idl, CorProf.h</span></span>  
  
<span data-ttu-id="6f023-134">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f023-134">**Library:** CorGuids.lib</span></span>  
  
<span data-ttu-id="6f023-135">**.NET Framework versiones:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f023-135">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f023-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="6f023-136">See also</span></span>

- [<span data-ttu-id="6f023-137">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="6f023-137">Profiling Enumerations</span></span>](profiling-enumerations.md)
- [<span data-ttu-id="6f023-138">COR_PRF_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="6f023-138">COR_PRF_MONITOR Enumeration</span></span>](cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="6f023-139">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6f023-139">ICorProfilerInfo5 Interface</span></span>](icorprofilerinfo5-interface.md)
