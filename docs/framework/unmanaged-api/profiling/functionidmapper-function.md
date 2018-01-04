---
title: "FunctionIDMapper (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: FunctionIDMapper
api_location: mscorwks.dll
api_type: COM
f1_keywords: FunctionIDMapper
helpviewer_keywords: FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 24e48ecb551a5faacc7da94b857b2e260f5aeca0
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="functionidmapper-function"></a><span data-ttu-id="43ab5-102">FunctionIDMapper (Función)</span><span class="sxs-lookup"><span data-stu-id="43ab5-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="43ab5-103">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a otro identificador que se usará en el [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), y [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="43ab5-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md), [FunctionLeave2](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md), and [FunctionTailcall2](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="43ab5-104">Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="43ab5-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43ab5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43ab5-105">Syntax</span></span>  
  
```  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,   
    [out] BOOL       *pbHookFunction  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43ab5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43ab5-106">Parameters</span></span>  
 `funcId`  
 <span data-ttu-id="43ab5-107">[in] Identificador de la función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="43ab5-107">[in] The function identifier to be remapped.</span></span>  
  
 `pbHookFunction`  
 <span data-ttu-id="43ab5-108">[out] Un puntero a un valor que el generador de perfiles establece en `true` si desea recibir `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` las devoluciones de llamada; de lo contrario, establece este valor en `false`.</span><span class="sxs-lookup"><span data-stu-id="43ab5-108">[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43ab5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43ab5-109">Return Value</span></span>  
 <span data-ttu-id="43ab5-110">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="43ab5-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="43ab5-111">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="43ab5-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="43ab5-112">En caso contrario, un valor devuelto nulo generará resultados imprevisibles, que posiblemente incluyan la detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="43ab5-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="43ab5-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43ab5-113">Remarks</span></span>  
 <span data-ttu-id="43ab5-114">El `FunctionIDMapper` función es una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="43ab5-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="43ab5-115">Se implementa el generador de perfiles para volver a asignar un Id. de función a algún otro identificador que es más útil para el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="43ab5-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="43ab5-116">El `FunctionIDMapper` devuelve el identificador alternativo que se usará para una función determinada.</span><span class="sxs-lookup"><span data-stu-id="43ab5-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="43ab5-117">El motor de ejecución, a continuación, respeta solicitud del generador de perfiles pasando este Id. alternativo, además del identificador de función tradicional, vuelva al generador de perfiles en el `clientData` parámetro de la `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` enlaces para identificar la función para la que se llama el enlace.</span><span class="sxs-lookup"><span data-stu-id="43ab5-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="43ab5-118">Puede usar el [ICorProfilerInfo:: SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) método para especificar la implementación de la `FunctionIDMapper` (función).</span><span class="sxs-lookup"><span data-stu-id="43ab5-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="43ab5-119">Puede llamar a la `ICorProfilerInfo::SetFunctionIDMapper` sólo una vez al método y se recomienda hacer esto en el [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="43ab5-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="43ab5-120">De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE utilizando [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), y que establece enlaces mediante [ICorProfilerInfo:: SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: Setenterleavefunctionhooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debería recibir el `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` las devoluciones de llamada para cada función.</span><span class="sxs-lookup"><span data-stu-id="43ab5-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="43ab5-121">Sin embargo, pueden implementar los generadores de perfiles `FunctionIDMapper` para evitar selectivamente la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` a `false`.</span><span class="sxs-lookup"><span data-stu-id="43ab5-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="43ab5-122">Los generadores de perfiles deben tolerar los casos en los que varios subprocesos de una aplicación de perfiles llamen el mismo método o función simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="43ab5-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="43ab5-123">En tales casos, el generador de perfiles puede recibir varias `FunctionIDMapper` las devoluciones de llamada para el mismo `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="43ab5-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="43ab5-124">El generador de perfiles debe garantizar que se devuelvan los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="43ab5-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43ab5-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43ab5-125">Requirements</span></span>  
 <span data-ttu-id="43ab5-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43ab5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43ab5-127">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="43ab5-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="43ab5-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43ab5-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43ab5-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43ab5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43ab5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="43ab5-130">See Also</span></span>  
 [<span data-ttu-id="43ab5-131">SetFunctionIDMapper (método)</span><span class="sxs-lookup"><span data-stu-id="43ab5-131">SetFunctionIDMapper Method</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setfunctionidmapper-method.md)  
 [<span data-ttu-id="43ab5-132">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="43ab5-132">FunctionIDMapper2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionidmapper2-function.md)  
 [<span data-ttu-id="43ab5-133">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="43ab5-133">FunctionEnter2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter2-function.md)  
 [<span data-ttu-id="43ab5-134">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="43ab5-134">FunctionLeave2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave2-function.md)  
 [<span data-ttu-id="43ab5-135">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="43ab5-135">FunctionTailcall2 Function</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall2-function.md)  
 [<span data-ttu-id="43ab5-136">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="43ab5-136">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
