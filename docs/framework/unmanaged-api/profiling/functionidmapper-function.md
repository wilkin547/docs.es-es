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
ms.openlocfilehash: 0cf2014d7007593c51868eff0b488fdab136e362
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175179"
---
# <a name="functionidmapper-function"></a><span data-ttu-id="a4086-102">FunctionIDMapper (Función)</span><span class="sxs-lookup"><span data-stu-id="a4086-102">FunctionIDMapper Function</span></span>
<span data-ttu-id="a4086-103">Notifica al generador de perfiles que el identificador especificado de una función se puede volver a asignar a un identificador alternativo que se usará en las devoluciones de llamada [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md)y [FunctionTailcall2](functiontailcall2-function.md) para esa función.</span><span class="sxs-lookup"><span data-stu-id="a4086-103">Notifies the profiler that the given identifier of a function may be remapped to an alternative ID to be used in the [FunctionEnter2](functionenter2-function.md), [FunctionLeave2](functionleave2-function.md), and [FunctionTailcall2](functiontailcall2-function.md) callbacks for that function.</span></span> <span data-ttu-id="a4086-104">Además, `FunctionIDMapper` permite al generador de perfiles indicar si desea recibir devoluciones de llamada de esa función.</span><span class="sxs-lookup"><span data-stu-id="a4086-104">`FunctionIDMapper` also enables the profiler to indicate whether it wants to receive callbacks for that function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a4086-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a4086-105">Syntax</span></span>  
  
```cpp  
UINT_PTR __stdcall FunctionIDMapper (  
    [in]  FunctionID  funcId,
    [out] BOOL       *pbHookFunction  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a4086-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a4086-106">Parameters</span></span>

- `funcId`

  <span data-ttu-id="a4086-107">\[en] El identificador de función que se va a reasignar.</span><span class="sxs-lookup"><span data-stu-id="a4086-107">\[in] The function identifier to be remapped.</span></span>

- `pbHookFunction`

  <span data-ttu-id="a4086-108">\[out] Un puntero a un valor `true` que el generador `FunctionEnter2` `FunctionLeave2`de `FunctionTailcall2` perfiles establece si desea recibir , , y devoluciones de llamada; de lo contrario, `false`establece este valor en .</span><span class="sxs-lookup"><span data-stu-id="a4086-108">\[out] A pointer to a value that the profiler sets to `true` if it wants to receive `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks; otherwise, it sets this value to `false`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a4086-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a4086-109">Return Value</span></span>  
 <span data-ttu-id="a4086-110">El generador de perfiles devuelve un valor que el motor de ejecución utiliza como identificador de función alternativo.</span><span class="sxs-lookup"><span data-stu-id="a4086-110">The profiler returns a value that the execution engine uses as an alternative function identifier.</span></span> <span data-ttu-id="a4086-111">El valor devuelto no puede ser null a menos que se devuelva `false` en `pbHookFunction`.</span><span class="sxs-lookup"><span data-stu-id="a4086-111">The return value cannot be null unless `false` is returned in `pbHookFunction`.</span></span> <span data-ttu-id="a4086-112">De lo contrario, un valor devuelto nulo producirá resultados impredecibles, incluida la posible detención del proceso.</span><span class="sxs-lookup"><span data-stu-id="a4086-112">Otherwise, a null return value will produce unpredictable results, including possibly halting the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a4086-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a4086-113">Remarks</span></span>  
 <span data-ttu-id="a4086-114">La `FunctionIDMapper` función es una devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="a4086-114">The `FunctionIDMapper` function is a callback.</span></span> <span data-ttu-id="a4086-115">El generador de perfiles lo implementa para reasignar un identificador de función a algún otro identificador que sea más útil para el generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="a4086-115">It is implemented by the profiler to remap a function ID to some other identifier that is more useful for the profiler.</span></span> <span data-ttu-id="a4086-116">El `FunctionIDMapper` devuelve el identificador alternativo que se usará para cualquier función dada.</span><span class="sxs-lookup"><span data-stu-id="a4086-116">The `FunctionIDMapper` returns the alternate ID to be used for any given function.</span></span> <span data-ttu-id="a4086-117">A continuación, el motor de ejecución respeta la solicitud del generador de perfiles pasando este identificador `clientData` alternativo, `FunctionEnter2` `FunctionLeave2`además del identificador de función tradicional, al generador de perfiles en el parámetro de , , y `FunctionTailcall2` los ganchos, para identificar la función para la que se llama al enlace.</span><span class="sxs-lookup"><span data-stu-id="a4086-117">The execution engine then honors the profiler's request by passing this alternate ID, in addition to the traditional function ID, back to the profiler in the `clientData` parameter of the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` hooks, to identify the function for which the hook is being called.</span></span>  
  
 <span data-ttu-id="a4086-118">Puede utilizar el método [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) para `FunctionIDMapper` especificar la implementación de la función.</span><span class="sxs-lookup"><span data-stu-id="a4086-118">You can use the [ICorProfilerInfo::SetFunctionIDMapper](icorprofilerinfo-setfunctionidmapper-method.md) method to specify the implementation of the `FunctionIDMapper` function.</span></span> <span data-ttu-id="a4086-119">Puede llamar `ICorProfilerInfo::SetFunctionIDMapper` al método solo una vez y se recomienda que lo haga en la devolución de llamada [ICorProfilerCallback::Initialize.](icorprofilercallback-initialize-method.md)</span><span class="sxs-lookup"><span data-stu-id="a4086-119">You can call the `ICorProfilerInfo::SetFunctionIDMapper` method only once, and we recommend that you do so in the [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
 <span data-ttu-id="a4086-120">De forma predeterminada, se supone que un generador de perfiles que establece la COR_PRF_MONITOR_ENTERLEAVE marca mediante [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md)y que establece los enlaces a través de [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) o [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), debe recibir el `FunctionEnter2`, `FunctionLeave2`, y `FunctionTailcall2` las devoluciones de llamada para cada función.</span><span class="sxs-lookup"><span data-stu-id="a4086-120">By default, it is assumed that a profiler that sets the COR_PRF_MONITOR_ENTERLEAVE flag by using [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md), and which sets hooks via [ICorProfilerInfo::SetEnterLeaveFunctionHooks](icorprofilerinfo-setenterleavefunctionhooks-method.md) or [ICorProfilerInfo2::SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md), should receive the `FunctionEnter2`, `FunctionLeave2`, and `FunctionTailcall2` callbacks for every function.</span></span> <span data-ttu-id="a4086-121">Sin embargo, los `FunctionIDMapper` generadores de perfiles pueden implementar `pbHookFunction` para `false`evitar selectivamente recibir estas devoluciones de llamada para ciertas funciones estableciendo en .</span><span class="sxs-lookup"><span data-stu-id="a4086-121">However, profilers may implement `FunctionIDMapper` to selectively avoid receiving these callbacks for certain functions by setting `pbHookFunction` to `false`.</span></span>  
  
 <span data-ttu-id="a4086-122">Los generadores de perfiles deben ser tolerantes a los casos en los que varios subprocesos de una aplicación con perfiles llaman al mismo método o función simultáneamente.</span><span class="sxs-lookup"><span data-stu-id="a4086-122">Profilers should be tolerant of cases where multiple threads of a profiled application are calling the same method/function simultaneously.</span></span> <span data-ttu-id="a4086-123">En tales casos, el generador `FunctionIDMapper` de perfiles `FunctionID`puede recibir varias devoluciones de llamada para el mismo archivo .</span><span class="sxs-lookup"><span data-stu-id="a4086-123">In such cases, the profiler may receive multiple `FunctionIDMapper` callbacks for the same `FunctionID`.</span></span> <span data-ttu-id="a4086-124">El generador de perfiles debe estar seguro de devolver los mismos `FunctionID`valores de esta devolución de llamada cuando se llama varias veces con el mismo archivo .</span><span class="sxs-lookup"><span data-stu-id="a4086-124">The profiler should be certain to return the same values from this callback when it is called multiple times with the same `FunctionID`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a4086-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a4086-125">Requirements</span></span>  
 <span data-ttu-id="a4086-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a4086-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a4086-127">**Encabezado:** CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="a4086-127">**Header:** CorProf.idl</span></span>  
  
 <span data-ttu-id="a4086-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a4086-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a4086-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a4086-129">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a4086-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="a4086-130">See also</span></span>

- [<span data-ttu-id="a4086-131">Método SetFunctionIDMapper</span><span class="sxs-lookup"><span data-stu-id="a4086-131">SetFunctionIDMapper Method</span></span>](icorprofilerinfo-setfunctionidmapper-method.md)
- [<span data-ttu-id="a4086-132">FunctionIDMapper2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a4086-132">FunctionIDMapper2 Function</span></span>](functionidmapper2-function.md)
- [<span data-ttu-id="a4086-133">FunctionEnter2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a4086-133">FunctionEnter2 Function</span></span>](functionenter2-function.md)
- [<span data-ttu-id="a4086-134">FunctionLeave2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a4086-134">FunctionLeave2 Function</span></span>](functionleave2-function.md)
- [<span data-ttu-id="a4086-135">FunctionTailcall2 (Función)</span><span class="sxs-lookup"><span data-stu-id="a4086-135">FunctionTailcall2 Function</span></span>](functiontailcall2-function.md)
- [<span data-ttu-id="a4086-136">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="a4086-136">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
