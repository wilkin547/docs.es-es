---
description: 'Más información sobre: ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)'
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
ms.openlocfilehash: 74adf7edc5269824a924933eb3284a5964e1bac1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781732"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="9fd87-103">ICorProfilerCallback7:: ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="9fd87-103">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>

<span data-ttu-id="9fd87-104">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="9fd87-104">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="9fd87-105">Notifica al generador de perfiles cada vez que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="9fd87-105">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fd87-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fd87-106">Syntax</span></span>  
  
```cpp  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fd87-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fd87-107">Parameters</span></span>  

 <span data-ttu-id="9fd87-108">[in] `moduleId`</span><span class="sxs-lookup"><span data-stu-id="9fd87-108">[in] `moduleId`</span></span>  
 <span data-ttu-id="9fd87-109">Identificador del módulo en memoria cuya secuencia de símbolos se actualiza.</span><span class="sxs-lookup"><span data-stu-id="9fd87-109">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9fd87-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9fd87-110">Remarks</span></span>  

 <span data-ttu-id="9fd87-111">Esta devolución de llamada se controla estableciendo la marca de máscara de eventos [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) al llamar al método [ICorProfilerCallback5:: SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd87-111">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9fd87-112">Este evento no se genera actualmente para símbolos creados o modificados implícitamente mediante <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="9fd87-112">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="9fd87-113">Incluso cuando se proporcionan símbolos por adelantado en una llamada a una de las sobrecargas de los <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> métodos administrados que incluyen un `rawSymbolStore` argumento para especificar los símbolos del ensamblado, es posible que el tiempo de ejecución no asocie realmente los datos simbólicos con el módulo hasta después de que se haya producido la devolución de llamada [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) .</span><span class="sxs-lookup"><span data-stu-id="9fd87-113">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load%2A?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="9fd87-114">Este evento proporciona una oportunidad posterior para recopilar símbolos para estos módulos.</span><span class="sxs-lookup"><span data-stu-id="9fd87-114">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fd87-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fd87-115">Requirements</span></span>  

 <span data-ttu-id="9fd87-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fd87-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fd87-117">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fd87-117">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fd87-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fd87-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fd87-119">**.NET Framework versiones:**[!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fd87-119">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fd87-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fd87-120">See also</span></span>

- [<span data-ttu-id="9fd87-121">Método ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="9fd87-121">ModuleLoadFinished Method</span></span>](icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="9fd87-122">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="9fd87-122">SetEventMask2 Method</span></span>](icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="9fd87-123">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="9fd87-123">ICorProfilerCallback7 Interface</span></span>](icorprofilercallback7-interface.md)
