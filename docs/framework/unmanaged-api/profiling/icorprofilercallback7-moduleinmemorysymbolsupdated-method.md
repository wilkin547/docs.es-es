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
ms.openlocfilehash: b9e404de96fa42509144904f5b2ff58e341578a9
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740435"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="f9583-102">ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="f9583-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="f9583-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f9583-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f9583-104">Notifica al generador de perfiles cada vez que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="f9583-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9583-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f9583-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f9583-106">Parameters</span><span class="sxs-lookup"><span data-stu-id="f9583-106">Parameters</span></span>  
 <span data-ttu-id="f9583-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="f9583-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="f9583-108">Identificador del módulo en memoria cuya secuencia de símbolos se actualiza.</span><span class="sxs-lookup"><span data-stu-id="f9583-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f9583-109">Notas</span><span class="sxs-lookup"><span data-stu-id="f9583-109">Remarks</span></span>  
 <span data-ttu-id="f9583-110">Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f9583-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f9583-111">Este evento no se genera actualmente para los símbolos creados o modificados implícitamente mediante <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="f9583-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="f9583-112">Incluso cuando se proporcionan símbolos por adelantado en una llamada a una de las sobrecargas de los métodos <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> administrados que incluyen un argumento `rawSymbolStore` para especificar los símbolos del ensamblado, es posible que el tiempo de ejecución no asocie realmente los datos simbólicos con el módulo hasta después de que se haya producido la devolución de llamada [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="f9583-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="f9583-113">Este evento proporciona una oportunidad posterior para recopilar símbolos para estos módulos.</span><span class="sxs-lookup"><span data-stu-id="f9583-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9583-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="f9583-114">Requirements</span></span>  
 <span data-ttu-id="f9583-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9583-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9583-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f9583-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f9583-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f9583-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f9583-118">**.NET Framework versiones:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9583-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9583-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f9583-119">See also</span></span>

- [<span data-ttu-id="f9583-120">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="f9583-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="f9583-121">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="f9583-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="f9583-122">ICorProfilerCallback7 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f9583-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
