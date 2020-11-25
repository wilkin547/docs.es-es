---
title: FunctionIDMapper (Función)
ms.date: 03/30/2017
api_name:
- FunctionIDMapper
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- FunctionIDMapper
helpviewer_keywords:
- FunctionIDMapper function [.NET Framework profiling]
ms.assetid: b8205b60-1893-4303-8cff-7ac5a00892aa
topic_type:
- apiref
ms.openlocfilehash: 17396d3038578c16b74c3717174dc0fa4dc17631
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722848"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="da73f-102">FunctionIDMapper (Función)</span><span class="sxs-lookup"><span data-stu-id="da73f-102">FunctionIDMapper Function</span></span>

<span data-ttu-id="da73f-103">Notifica al generador de perfiles que el identificador especificado de una función puede reasignarse a un identificador alternativo que se va a usar en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función.</span><span class="sxs-lookup"><span data-stu-id="da73f-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="da73f-104">Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="da73f-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da73f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da73f-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da73f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da73f-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="da73f-107">\[en] el identificador de función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="da73f-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="da73f-108">\[out] un puntero a un valor que el generador de perfiles establece en `true` si desea recibir `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` devoluciones de llamada, y; de lo contrario, establece este valor en `false` .</span><span class="sxs-lookup"><span data-stu-id="da73f-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="da73f-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da73f-109">Return Value</span></span>  

 <span data-ttu-id="da73f-110">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="da73f-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="da73f-111">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="da73f-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="da73f-112">De lo contrario, un valor devuelto null producirá resultados imprevisibles, incluso la detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="da73f-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="da73f-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="da73f-113">Remarks</span></span>  

 <span data-ttu-id="da73f-114">La `FunctionIDMapper` función es una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="da73f-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="da73f-115">Lo implementa el generador de perfiles para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="da73f-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="da73f-116">`FunctionIDMapper`Devuelve el identificador alternativo que se va a utilizar para una función determinada.</span><span class="sxs-lookup"><span data-stu-id="da73f-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="da73f-117">A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este identificador alternativo, además del identificador de función tradicional, de nuevo al generador de perfiles en el `clientData` parámetro de los `FunctionEnter2` `FunctionLeave2` enlaces, y `FunctionTailcall2` , para identificar la función para la que se llama al enlace.</span><span class="sxs-lookup"><span data-stu-id="da73f-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="da73f-118">Puede usar el método [ICorProfilerInfo:: setfunctionidmapper (](icorprofilerinfo-setfunctionidmapper-method.md) para especificar la implementación de la `FunctionIDMapper` función.</span><span class="sxs-lookup"><span data-stu-id="da73f-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="da73f-119">Puede llamar al `ICorProfilerInfo::SetFunctionIDMapper` método solo una vez y se recomienda hacerlo en la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) .</span><span class="sxs-lookup"><span data-stu-id="da73f-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="da73f-120">De forma predeterminada, se supone que un generador de perfiles que establece la marca COR_PRF_MONITOR_ENTERLEAVE mediante [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md)y que establece enlaces a través de [ICorProfilerInfo:: SetEnterLeaveFunctionHooks (](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2:: SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir las `FunctionEnter2` `FunctionLeave2` `FunctionTailcall2` devoluciones de llamada, y para cada función.</span><span class="sxs-lookup"><span data-stu-id="da73f-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="da73f-121">Sin embargo, los profileres pueden implementar `FunctionIDMapper` para evitar de forma selectiva la recepción de estas devoluciones de llamada para ciertas funciones estableciendo `pbHookFunction` en `false` .</span><span class="sxs-lookup"><span data-stu-id="da73f-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="da73f-122">Los perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación de la que se va a crear el perfiles llamen al mismo método o función simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="da73f-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="da73f-123">En tales casos, el generador de perfiles puede recibir varias `FunctionIDMapper` devoluciones de llamada para el mismo `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="da73f-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="da73f-124">El generador de perfiles debe asegurarse de que devuelve los mismos valores de esta devolución de llamada cuando se llama varias veces con el mismo `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="da73f-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da73f-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da73f-125">Requirements</span></span>  

 <span data-ttu-id="da73f-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da73f-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da73f-127">**Encabezado:** Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="da73f-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="da73f-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da73f-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da73f-129">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da73f-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da73f-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da73f-130">See also</span></span>

- [<span data-ttu-id="da73f-131">Método SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="da73f-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="da73f-132">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="da73f-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="da73f-133">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="da73f-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="da73f-134">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="da73f-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="da73f-135">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="da73f-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="da73f-136">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="da73f-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
