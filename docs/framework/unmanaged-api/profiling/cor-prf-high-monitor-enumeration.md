---
title: "COR_PRF_HIGH_MONITOR (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3ba543d8-15e5-4322-b6e7-1ebfc92ed7dd
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1df931796b32b6bea49e8b69da02d39e6a4803e3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="corprfhighmonitor-enumeration"></a><span data-ttu-id="00f4b-102">COR_PRF_HIGH_MONITOR (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="00f4b-102">COR_PRF_HIGH_MONITOR Enumeration</span></span>
<span data-ttu-id="00f4b-103">[Compatible con .NET Framework 4.5.2 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="00f4b-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="00f4b-104">Proporciona marcas, además de las que se encuentran en el [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración que puede especificar el generador de perfiles a la [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método cuando se está cargando.</span><span class="sxs-lookup"><span data-stu-id="00f4b-104">Provides flags in addition to those found in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration that the profiler can specify to the [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method when it is loading.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="00f4b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="00f4b-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_HIGH_MONITOR_NONE                = 0x00000000,  
    COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES     = 0x00000001,  
    COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED     = 0x00000002,     
    COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE       = 0,  
    COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH      = COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED,  
    COR_PRF_HIGH_MONITOR_IMMUTABLE           = 0  
} COR_PRF_HIGH_MONITOR;  
```  
  
## <a name="members"></a><span data-ttu-id="00f4b-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="00f4b-106">Members</span></span>  
  
|<span data-ttu-id="00f4b-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="00f4b-107">Member</span></span>|<span data-ttu-id="00f4b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="00f4b-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_HIGH_MONITOR_NONE`|<span data-ttu-id="00f4b-109">No se establecen marcas.</span><span class="sxs-lookup"><span data-stu-id="00f4b-109">No flags are set.</span></span>|  
|`COR_PRF_HIGH_ADD_ASSEMBLY_REFERENCES`|<span data-ttu-id="00f4b-110">Controles de la [icorprofilercallback6:: Getassemblyreference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) devolución de llamada para agregar referencias de ensamblado durante el rastreo de cierre de referencias de ensamblado CLR.</span><span class="sxs-lookup"><span data-stu-id="00f4b-110">Controls the [ICorProfilerCallback6::GetAssemblyReference](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback6-getassemblyreferences-method.md) callback for adding assembly references during the CLR assembly reference closure walk.</span></span>|  
|`COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED`|<span data-ttu-id="00f4b-111">Controles de la [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) devolución de llamada para las actualizaciones de la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="00f4b-111">Controls the [ICorProfilerCallback7::ModuleInMemorySymbolsUpdated](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-moduleinmemorysymbolsupdated-method.md) callback for updates to the symbol stream associated with an in-memory module.</span></span>|  
|`COR_PRF_HIGH_REQUIRE_PROFILE_IMAGE`|<span data-ttu-id="00f4b-112">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que requieren imágenes mejoradas para el perfil.</span><span class="sxs-lookup"><span data-stu-id="00f4b-112">Represents all `COR_PRF_HIGH_MONITOR` flags that require profile-enhanced images.</span></span> <span data-ttu-id="00f4b-113">Se corresponde con el `COR_PRF_REQUIRE_PROFILE_IMAGE` se marcan en la [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeración.</span><span class="sxs-lookup"><span data-stu-id="00f4b-113">It corresponds to the `COR_PRF_REQUIRE_PROFILE_IMAGE` flag in the [COR_PRF_MONITOR](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md) enumeration.</span></span>|  
|`COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH`|<span data-ttu-id="00f4b-114">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer después de que el generador de perfiles se asocie a una aplicación en ejecución.</span><span class="sxs-lookup"><span data-stu-id="00f4b-114">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set after the profiler is attached to a running app.</span></span>|  
|`COR_PRF_HIGH_MONITOR_IMMUTABLE`|<span data-ttu-id="00f4b-115">Representa todas las marcas `COR_PRF_HIGH_MONITOR` que se pueden establecer solo durante la inicialización.</span><span class="sxs-lookup"><span data-stu-id="00f4b-115">Represents all `COR_PRF_HIGH_MONITOR` flags that can be set only during initialization.</span></span> <span data-ttu-id="00f4b-116">Al intentar cambiar cualquiera de estas marcas en otro lugar se genera un valor `HRESULT` que indica error.</span><span class="sxs-lookup"><span data-stu-id="00f4b-116">Trying to change any of these flags elsewhere results in an `HRESULT` value that indicates failure.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="00f4b-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="00f4b-117">Remarks</span></span>  
 <span data-ttu-id="00f4b-118">El `COR_PRF_HIGH_MONITOR` marcas se usan con la `pdwEventsHigh` parámetro de la [icorprofilerinfo5:: Geteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) y [icorprofilerinfo5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) métodos.</span><span class="sxs-lookup"><span data-stu-id="00f4b-118">The `COR_PRF_HIGH_MONITOR` flags are used with the `pdwEventsHigh` parameter of the [ICorProfilerInfo5::GetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-geteventmask2-method.md) and [ICorProfilerInfo5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) methods.</span></span>  
  
 <span data-ttu-id="00f4b-119">A partir de la [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], el valor de la `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` cambia de 0 a `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0 x 00000002).</span><span class="sxs-lookup"><span data-stu-id="00f4b-119">Starting with the [!INCLUDE[net_v461](../../../../includes/net-v461-md.md)], the value of the `COR_PRF_HIGH_ALLOWABLE_AFTER_ATTACH` changed from 0 to `COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED` (0x00000002).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="00f4b-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="00f4b-120">Requirements</span></span>  
 <span data-ttu-id="00f4b-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="00f4b-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="00f4b-122">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="00f4b-122">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="00f4b-123">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="00f4b-123">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="00f4b-124">**Versiones de .NET framework:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="00f4b-124">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="00f4b-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="00f4b-125">See Also</span></span>  
 [<span data-ttu-id="00f4b-126">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="00f4b-126">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)  
 [<span data-ttu-id="00f4b-127">COR_PRF_MONITOR (enumeración)</span><span class="sxs-lookup"><span data-stu-id="00f4b-127">COR_PRF_MONITOR Enumeration</span></span>](../../../../docs/framework/unmanaged-api/profiling/cor-prf-monitor-enumeration.md)  
 [<span data-ttu-id="00f4b-128">ICorProfilerInfo5 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="00f4b-128">ICorProfilerInfo5 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-interface.md)
