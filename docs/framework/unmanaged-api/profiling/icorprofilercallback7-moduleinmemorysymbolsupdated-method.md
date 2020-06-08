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
ms.openlocfilehash: c7e53816c2f571fe6ff68b517ed827459a0f1562
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84499095"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="91a38-102">ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="91a38-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="91a38-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="91a38-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="91a38-104">Notifica al generador de perfiles cada vez que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="91a38-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="91a38-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="91a38-105">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91a38-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="91a38-106">Parameters</span></span>  
 <span data-ttu-id="91a38-107">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="91a38-107">[in] `moduleId`</span></span>  
 <span data-ttu-id="91a38-108">Identificador del módulo en memoria cuya secuencia de símbolos se actualiza.</span><span class="sxs-lookup"><span data-stu-id="91a38-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="91a38-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="91a38-109">Remarks</span></span>  
 <span data-ttu-id="91a38-110">Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91a38-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="91a38-111">Este evento no se genera actualmente para símbolos creados o modificados implícitamente mediante <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="91a38-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="91a38-112">Incluso cuando se proporcionan símbolos por adelantado en una llamada a una de las sobrecargas de los <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> métodos administrados que incluyen un `rawSymbolStore` argumento para especificar los símbolos del ensamblado, es posible que el tiempo de ejecución no asocie realmente los datos simbólicos con el módulo hasta después de que se haya producido la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="91a38-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="91a38-113">Este evento proporciona una oportunidad posterior para recopilar símbolos para estos módulos.</span><span class="sxs-lookup"><span data-stu-id="91a38-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="91a38-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="91a38-114">Requirements</span></span>  
 <span data-ttu-id="91a38-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="91a38-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91a38-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="91a38-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="91a38-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="91a38-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="91a38-118">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91a38-118">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a38-119">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="91a38-119">See also</span></span>

- [<span data-ttu-id="91a38-120">Método ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="91a38-120">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="91a38-121">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="91a38-121">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="91a38-122">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="91a38-122">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
