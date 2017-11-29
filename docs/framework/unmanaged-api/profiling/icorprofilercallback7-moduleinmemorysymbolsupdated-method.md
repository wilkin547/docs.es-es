---
title: "ICorProfilerCallback7::ModuleInMemorySymbolsUpdated (método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfiler7.ModuleInMemorySymbolsUpdated
api_location:
- mscorwks.dll
- corprof.idl
api_type: COM
ms.assetid: f362a896-3247-4894-9727-e48dbbcd2c78
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 088749195165039639f58f4eb6444fb640ab4cec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="f1b4f-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated (método)</span><span class="sxs-lookup"><span data-stu-id="f1b4f-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="f1b4f-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="f1b4f-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="f1b4f-104">Notifica al generador de perfiles siempre que se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f1b4f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f1b4f-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f1b4f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f1b4f-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="f1b4f-107">El identificador del módulo en memoria se actualiza cuya secuencia de símbolos.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-107">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f1b4f-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f1b4f-108">Remarks</span></span>  
 <span data-ttu-id="f1b4f-109">Esta devolución de llamada se controla estableciendo la [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) marca de máscara de eventos cuando se llama a la [icorprofilercallback5:: Seteventmask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-109">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f1b4f-110">Este evento no se desencadena actualmente símbolos implícitamente creados o modificados a través de <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-110">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="f1b4f-111">Incluso cuando símbolos se proporcionan por adelantado en una llamada a una de las sobrecargas de los recursos administrados <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> métodos que incluye un `rawSymbolStore` argumento para especificar los símbolos del ensamblado, el tiempo de ejecución no puede asociar realmente los datos simbólicos con el módulo hasta después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se ha producido la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-111">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="f1b4f-112">Este evento proporciona una oportunidad para recopilar los símbolos para dichos módulos más adelante.</span><span class="sxs-lookup"><span data-stu-id="f1b4f-112">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f1b4f-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1b4f-113">Requirements</span></span>  
 <span data-ttu-id="f1b4f-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1b4f-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1b4f-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f1b4f-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f1b4f-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1b4f-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1b4f-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1b4f-117">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1b4f-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1b4f-118">See Also</span></span>  
 [<span data-ttu-id="f1b4f-119">ModuleLoadFinished (método)</span><span class="sxs-lookup"><span data-stu-id="f1b4f-119">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)  
 [<span data-ttu-id="f1b4f-120">SetEventMask2 (método)</span><span class="sxs-lookup"><span data-stu-id="f1b4f-120">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)  
 [<span data-ttu-id="f1b4f-121">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="f1b4f-121">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
