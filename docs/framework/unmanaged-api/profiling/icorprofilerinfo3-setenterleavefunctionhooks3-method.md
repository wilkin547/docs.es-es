---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type:
- apiref
ms.openlocfilehash: eb658d682ce589b7dfdcfc0228d0c657310e6f7a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496274"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="1ce74-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)</span><span class="sxs-lookup"><span data-stu-id="1ce74-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="1ce74-103">Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="1ce74-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1ce74-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1ce74-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1ce74-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1ce74-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="1ce74-106">de Puntero a la implementación de que se va a utilizar como `FunctionEnter3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ce74-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="1ce74-107">de Puntero a la implementación de que se va a utilizar como `FunctionLeave3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ce74-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="1ce74-108">de Puntero a la implementación de que se va a utilizar como `FunctionTailcall3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1ce74-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1ce74-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1ce74-109">Remarks</span></span>  
 <span data-ttu-id="1ce74-110">Los enlaces [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) no proporcionan el marco de pila y la inspección de argumentos.</span><span class="sxs-lookup"><span data-stu-id="1ce74-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="1ce74-111">Para tener acceso a esa información `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` se deben establecer las marcas,, y/o `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="1ce74-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="1ce74-112">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el método [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="1ce74-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="1ce74-113">Solo un conjunto de devoluciones de llamada puede estar activo a la vez y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="1ce74-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="1ce74-114">Por lo tanto, si un generador de perfiles llama al [método SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y al `SetEnterLeaveFunctionHooks3` método, `SetEnterLeaveFunctionHooks3` se usa.</span><span class="sxs-lookup"><span data-stu-id="1ce74-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="1ce74-115">`SetEnterLeaveFunctionHooks3`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="1ce74-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1ce74-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1ce74-116">Requirements</span></span>  
 <span data-ttu-id="1ce74-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1ce74-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1ce74-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1ce74-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1ce74-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1ce74-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1ce74-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1ce74-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1ce74-121">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="1ce74-121">See also</span></span>

- [<span data-ttu-id="1ce74-122">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="1ce74-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="1ce74-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="1ce74-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="1ce74-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="1ce74-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="1ce74-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="1ce74-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="1ce74-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1ce74-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="1ce74-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1ce74-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="1ce74-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1ce74-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="1ce74-129">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1ce74-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="1ce74-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="1ce74-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="1ce74-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1ce74-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1ce74-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1ce74-132">Profiling</span></span>](index.md)
