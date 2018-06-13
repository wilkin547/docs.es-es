---
title: ICorProfilerCallback7::ModuleInMemorySymbolsUpdated (método)
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type:
- COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9aa690378a32ffee2def672f02dc8b5582647a5e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33455819"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="98f9f-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="98f9f-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="98f9f-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="98f9f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="98f9f-104">Notifica al generador de perfiles siempre que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="98f9f-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f9f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98f9f-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="98f9f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98f9f-106">Parameters</span></span>  
 <span data-ttu-id="98f9f-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="98f9f-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="98f9f-108">El identificador del módulo en memoria se actualiza cuya secuencia de símbolos.</span><span class="sxs-lookup"><span data-stu-id="98f9f-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="98f9f-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98f9f-109">Remarks</span></span>  
 <span data-ttu-id="98f9f-110">Esta devolución de llamada se controla estableciendo la [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) marca de máscara de eventos cuando se llama a la [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="98f9f-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="98f9f-111">Este evento no se desencadena actualmente símbolos implícitamente creados o modificados a través de <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="98f9f-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="98f9f-112">Incluso cuando símbolos se proporcionan por adelantado en una llamada a una de las sobrecargas de los recursos administrados <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> métodos que incluye un `rawSymbolStore` argumento para especificar los símbolos del ensamblado, el tiempo de ejecución no puede asociar realmente los datos simbólicos con el módulo hasta después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se ha producido la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="98f9f-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="98f9f-113">Este evento proporciona una oportunidad para recopilar los símbolos para dichos módulos más adelante.</span><span class="sxs-lookup"><span data-stu-id="98f9f-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="98f9f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98f9f-114">Requirements</span></span>  
 <span data-ttu-id="98f9f-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98f9f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98f9f-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="98f9f-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="98f9f-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="98f9f-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="98f9f-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98f9f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f9f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="98f9f-119">See Also</span></span>  
 [<span data-ttu-id="98f9f-120">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="98f9f-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="98f9f-121">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="98f9f-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="98f9f-122">ICorProfilerCallback7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="98f9f-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
