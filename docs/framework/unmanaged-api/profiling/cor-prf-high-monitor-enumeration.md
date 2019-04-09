---
title: COR_PRF_HIGH_MONITOR (Enumeración)
ms.date: 04/10/2018
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 572fcee528098a4f2929e07dfae63efc56e93dfd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59081650"
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="ad432-102">COR_PRF_HIGH_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ad432-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="ad432-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="ad432-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="ad432-104">Proporciona marcas, además de los que se encuentran en el [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración que el generador de perfiles puede especificar para el [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="ad432-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad432-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ad432-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                     = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES          = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED        = 0x00000002,     
    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS = 0x00000004,    
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE            = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH           = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | 
                                                    COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE                = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="ad432-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="ad432-106">Members</span></span>  
  
|<span data-ttu-id="ad432-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="ad432-107">Member</span></span>|<span data-ttu-id="ad432-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="ad432-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="ad432-109">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="ad432-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="ad432-110">Los controles de la [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada para agregar referencias de ensamblado durante el rastreo de cierre de referencias de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="ad432-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="ad432-111">Los controles de la [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) devolución de llamada para las actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="ad432-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`|<span data-ttu-id="ad432-112">Los controles de la [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) devolución de llamada para indicar cuando un método dinámico ha sido elementos no utilizados se recopilan y se descargan.</span><span class="sxs-lookup"><span data-stu-id="ad432-112">Controls the [ICorProfilerCallback9::DynamicMethodUnloaded](icorprofilercallback9-dynamicmethodunloaded-method.md) callback for indicating when a dynamic method has been garbage collected and unloaded.</span></span> <br/> [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]|   
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="ad432-113">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="ad432-113">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="ad432-114">Se corresponde con el `COR_PRF_REQUIRE_PROFILE_IMAGE` marca en el [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="ad432-114">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="ad432-115">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="ad432-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="ad432-116">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="ad432-116">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="ad432-117">Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="ad432-117">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ad432-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ad432-118">Remarks</span></span>  
 <span data-ttu-id="ad432-119">El `COR_PRF_HIGH_MONITOR` marcas se usan con el `pdwEventsHigh` parámetro de la [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) y [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="ad432-119">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
<span data-ttu-id="ad432-120">A partir de la [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], el valor de la `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambia de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0 x 00000002).</span><span class="sxs-lookup"><span data-stu-id="ad432-120">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span> <span data-ttu-id="ad432-121">A partir de .NET Framework 4.7.2, puede cambiar su valor desde `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span><span class="sxs-lookup"><span data-stu-id="ad432-121">Starting with the .NET Framework 4.7.2, its value changed from `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED | COR_PRF_HIGH_MONITOR_DYNAMIC_FUNCTION_UNLOADS`.</span></span>   

`COR_PRF_HIGH_MONITOR_IMMUTABLE` <span data-ttu-id="ad432-122">debe ser una máscara de bits que representa todos los marcadores que solo pueden establecerse durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="ad432-122">is intended to be a bitmask that represents all flags that can only be set during initialization.</span></span> <span data-ttu-id="ad432-123">Al intentar cambiar cualquiera de estas marcas en otro lugar da como resultado un error `HRESULT`.</span><span class="sxs-lookup"><span data-stu-id="ad432-123">Trying to change any of these flags elsewhere results in a failed `HRESULT`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ad432-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ad432-124">Requirements</span></span>  
 <span data-ttu-id="ad432-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ad432-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad432-126">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ad432-126">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ad432-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ad432-127">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="ad432-128">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="ad432-128">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ad432-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="ad432-129">See also</span></span>

- [<span data-ttu-id="ad432-130">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ad432-130">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
- [<span data-ttu-id="ad432-131">COR_PRF_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ad432-131">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)
- [<span data-ttu-id="ad432-132">ICorProfilerInfo5 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ad432-132">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
