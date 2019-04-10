---
title: Método ICorProfilerCallback7::ModuleInMemorySymbolsUpdated
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
ms.openlocfilehash: 12414064bf0651eab443951bde2a50dcff7b2291
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226981"
---
# <a name="icorprofilercallback7moduleinmemorysymbolsupdated-method"></a><span data-ttu-id="aee34-102">Método ICorProfilerCallback7::ModuleInMemorySymbolsUpdated</span><span class="sxs-lookup"><span data-stu-id="aee34-102">ICorProfilerCallback7::ModuleInMemorySymbolsUpdated Method</span></span>
<span data-ttu-id="aee34-103">[Compatible con .NET Framework 4.6.1 y versiones posteriores]</span><span class="sxs-lookup"><span data-stu-id="aee34-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="aee34-104">Notifica al generador de perfiles cuando se actualiza la secuencia de símbolos asociada a un módulo en memoria.</span><span class="sxs-lookup"><span data-stu-id="aee34-104">Notifies the profiler whenever the symbol stream associated with an in-memory module is updated.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aee34-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aee34-105">Syntax</span></span>  
  
```  
HRESULT ModuleInMemorySymbolsUpdated(  
     ModuleID moduleId  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aee34-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aee34-106">Parameters</span></span>  
 <span data-ttu-id="aee34-107">[in]</span><span class="sxs-lookup"><span data-stu-id="aee34-107">[in]</span></span> `moduleId`  
 <span data-ttu-id="aee34-108">El identificador del módulo en memoria se actualiza cuya secuencia de símbolos.</span><span class="sxs-lookup"><span data-stu-id="aee34-108">The identifier of the in-memory module whose symbol stream is updated.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aee34-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="aee34-109">Remarks</span></span>  
 <span data-ttu-id="aee34-110">Esta devolución de llamada se controla estableciendo la [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) marca de máscara de eventos cuando se llama a la [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="aee34-110">This callback is controlled by setting the [COR_PRF_HIGH_IN_MEMORY_SYMBOLS_UPDATED](../../../../docs/framework/unmanaged-api/profiling/cor-prf-high-monitor-enumeration.md) event mask flag when calling the [ICorProfilerCallback5::SetEventMask2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md) method.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aee34-111">Este evento no se produce actualmente símbolos implícitamente creado o modificado a través de <xref:System.Reflection.Emit> API.</span><span class="sxs-lookup"><span data-stu-id="aee34-111">This event is not currently raised for symbols implicitly created or modified via <xref:System.Reflection.Emit> APIs.</span></span>  
  
 <span data-ttu-id="aee34-112">Incluso cuando los símbolos se proporcionan por adelantado en una llamada a una de las sobrecargas de los recursos administrados <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> métodos que incluye un `rawSymbolStore` argumento para especificar los símbolos para el ensamblado, el tiempo de ejecución no puede asociar realmente los datos simbólicos con el módulo hasta después de la [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) se ha producido la devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="aee34-112">Even when symbols are provided up front in a call to one of the overloads of the managed <xref:System.Reflection.Assembly.Load*?displayProperty=nameWithType> methods that includes a `rawSymbolStore` argument to specify the symbols for the assembly, the runtime may not actually associate the symbolic data with the module until after the [ModuleLoadFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md) callback has occurred.</span></span> <span data-ttu-id="aee34-113">Este evento proporciona una oportunidad para recopilar los símbolos para dichos módulos posterior.</span><span class="sxs-lookup"><span data-stu-id="aee34-113">This event provides a later opportunity to collect symbols for such modules.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aee34-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aee34-114">Requirements</span></span>  
 <span data-ttu-id="aee34-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aee34-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aee34-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aee34-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aee34-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aee34-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="aee34-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="aee34-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="aee34-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="aee34-119">See also</span></span>

- [<span data-ttu-id="aee34-120">Método ModuleLoadFinished</span><span class="sxs-lookup"><span data-stu-id="aee34-120">ModuleLoadFinished Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-moduleloadfinished-method.md)
- [<span data-ttu-id="aee34-121">Método SetEventMask2</span><span class="sxs-lookup"><span data-stu-id="aee34-121">SetEventMask2 Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo5-seteventmask2-method.md)
- [<span data-ttu-id="aee34-122">Interfaz ICorProfilerCallback7</span><span class="sxs-lookup"><span data-stu-id="aee34-122">ICorProfilerCallback7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback7-interface.md)
