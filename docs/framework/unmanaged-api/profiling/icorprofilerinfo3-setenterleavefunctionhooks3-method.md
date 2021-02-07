---
description: 'Más información sobre: ICorProfilerInfo3:: Setenterleavefunctionhooks3 ((método)'
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
ms.openlocfilehash: c741054c50fb74afe79f10607e24424a07d2f8c5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687030"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="bbfb2-103">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)</span><span class="sxs-lookup"><span data-stu-id="bbfb2-103">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>

<span data-ttu-id="bbfb2-104">Especifica las funciones implementadas por el generador de perfiles a las que se llamará en las funciones [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) .</span><span class="sxs-lookup"><span data-stu-id="bbfb2-104">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbfb2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbfb2-105">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bbfb2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="bbfb2-106">Parameters</span></span>  

 `pFuncEnter3`  
 <span data-ttu-id="bbfb2-107">de Puntero a la implementación de que se va a utilizar como `FunctionEnter3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-107">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="bbfb2-108">de Puntero a la implementación de que se va a utilizar como `FunctionLeave3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-108">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="bbfb2-109">de Puntero a la implementación de que se va a utilizar como `FunctionTailcall3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-109">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bbfb2-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="bbfb2-110">Remarks</span></span>  

 <span data-ttu-id="bbfb2-111">Los enlaces [FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md)y [FunctionTailcall3](functiontailcall3-function.md) no proporcionan el marco de pila y la inspección de argumentos.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-111">[FunctionEnter3](functionenter3-function.md), [FunctionLeave3](functionleave3-function.md), and [FunctionTailcall3](functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="bbfb2-112">Para tener acceso a esa información `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` se deben establecer las marcas,, y/o  `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="bbfb2-112">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="bbfb2-113">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, usar el método [ICorProfilerInfo3:: SetEnterLeaveFunctionHooks3WithInfo (](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-113">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="bbfb2-114">Solo un conjunto de devoluciones de llamada puede estar activo a la vez y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-114">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="bbfb2-115">Por lo tanto, si un generador de perfiles llama al [método SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y al `SetEnterLeaveFunctionHooks3` método, `SetEnterLeaveFunctionHooks3` se usa.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-115">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="bbfb2-116">`SetEnterLeaveFunctionHooks3`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="bbfb2-116">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbfb2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbfb2-117">Requirements</span></span>  

 <span data-ttu-id="bbfb2-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbfb2-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbfb2-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="bbfb2-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="bbfb2-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bbfb2-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bbfb2-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bbfb2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbfb2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbfb2-122">See also</span></span>

- [<span data-ttu-id="bbfb2-123">Setenterleavefunctionhooks3withinfo (</span><span class="sxs-lookup"><span data-stu-id="bbfb2-123">SetEnterLeaveFunctionHooks3WithInfo</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)
- [<span data-ttu-id="bbfb2-124">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="bbfb2-124">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="bbfb2-125">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="bbfb2-125">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="bbfb2-126">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="bbfb2-126">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="bbfb2-127">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bbfb2-127">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="bbfb2-128">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bbfb2-128">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="bbfb2-129">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="bbfb2-129">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="bbfb2-130">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bbfb2-130">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="bbfb2-131">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="bbfb2-131">ICorProfilerInfo3</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="bbfb2-132">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bbfb2-132">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="bbfb2-133">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="bbfb2-133">Profiling</span></span>](index.md)
