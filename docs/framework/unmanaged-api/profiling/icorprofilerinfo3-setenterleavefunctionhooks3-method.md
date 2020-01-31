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
ms.openlocfilehash: 3e07d2b61e85bb626613c40832c1a6aa499ef248
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76868504"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="9da61-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)</span><span class="sxs-lookup"><span data-stu-id="9da61-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="9da61-103">Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="9da61-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9da61-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9da61-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="9da61-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="9da61-106">de Puntero a la implementación de que se va a utilizar como la devolución de llamada de `FunctionEnter3`.</span><span class="sxs-lookup"><span data-stu-id="9da61-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="9da61-107">de Puntero a la implementación de que se va a utilizar como la devolución de llamada de `FunctionLeave3`.</span><span class="sxs-lookup"><span data-stu-id="9da61-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="9da61-108">de Puntero a la implementación de que se va a utilizar como la devolución de llamada de `FunctionTailcall3`.</span><span class="sxs-lookup"><span data-stu-id="9da61-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9da61-109">Notas</span><span class="sxs-lookup"><span data-stu-id="9da61-109">Remarks</span></span>  
 <span data-ttu-id="9da61-110">Los enlaces [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) no proporcionan el marco de pila y la inspección de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9da61-110">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="9da61-111">Para tener acceso a esa información, se deben establecer las marcas `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`y/o `COR_PRF_ENABLE_FRAME_INFO`.</span><span class="sxs-lookup"><span data-stu-id="9da61-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="9da61-112">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el método [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="9da61-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="9da61-113">Solo un conjunto de devoluciones de llamada puede estar activo a la vez y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="9da61-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="9da61-114">Por consiguiente, si un generador de perfiles llama al [método SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y al método `SetEnterLeaveFunctionHooks3`, se utiliza `SetEnterLeaveFunctionHooks3`.</span><span class="sxs-lookup"><span data-stu-id="9da61-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="9da61-115">Solo se puede llamar al método `SetEnterLeaveFunctionHooks3` desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="9da61-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da61-116">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="9da61-116">Requirements</span></span>  
 <span data-ttu-id="9da61-117">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da61-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da61-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9da61-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9da61-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9da61-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9da61-120">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da61-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da61-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="9da61-121">See also</span></span>

- [<span data-ttu-id="9da61-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9da61-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="9da61-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="9da61-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="9da61-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="9da61-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="9da61-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="9da61-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="9da61-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9da61-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="9da61-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9da61-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="9da61-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="9da61-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="9da61-129">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9da61-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="9da61-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="9da61-130">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="9da61-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9da61-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="9da61-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9da61-132">Profiling</span></span>](index.md)
