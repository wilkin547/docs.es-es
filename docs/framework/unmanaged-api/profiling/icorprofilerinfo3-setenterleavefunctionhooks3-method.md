---
title: "ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetEnterLeaveFunctionHooks3 Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 method [.NET Framework profiling]
ms.assetid: f0621465-b84f-40ab-a4e5-56a7abc776a7
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: f36a73d26bae96a57d205bb85fa232d16a964dc5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3-method"></a><span data-ttu-id="52de1-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 (Método)</span><span class="sxs-lookup"><span data-stu-id="52de1-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3 Method</span></span>
<span data-ttu-id="52de1-103">Especifica las funciones implementadas por el generador de perfiles que se llamará en el [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) funciones.</span><span class="sxs-lookup"><span data-stu-id="52de1-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52de1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52de1-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3(  
            [in] FunctionEnter3    *pFuncEnter3,  
            [in] FunctionLeave3    *pFuncLeave3,  
            [in] FunctionTailcall3 *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="52de1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52de1-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="52de1-106">[in] Un puntero a la implementación que se usará como el `FunctionEnter3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="52de1-106">[in] A pointer to the implementation to be used as the `FunctionEnter3` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="52de1-107">[in] Un puntero a la implementación que se usará como el `FunctionLeave3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="52de1-107">[in] A pointer to the implementation to be used as the `FunctionLeave3` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="52de1-108">[in] Un puntero a la implementación que se usará como el `FunctionTailcall3` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="52de1-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="52de1-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52de1-109">Remarks</span></span>  
 <span data-ttu-id="52de1-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), y [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) enlaces no proporcionan inspección de marco y los argumentos de la pila.</span><span class="sxs-lookup"><span data-stu-id="52de1-110">[FunctionEnter3](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md), [FunctionLeave3](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md), and [FunctionTailcall3](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md) hooks do not provide stack frame and argument inspection.</span></span> <span data-ttu-id="52de1-111">Para tener acceso a esa información, el `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, o `COR_PRF_ENABLE_FRAME_INFO` marcas tienen que establecerse.</span><span class="sxs-lookup"><span data-stu-id="52de1-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or  `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="52de1-112">Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento y, a continuación, use la [ICorProfilerInfo3:: Setenterleavefunctionhooks3withinfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) método para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="52de1-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the [ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md) method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="52de1-113">Únicamente un conjunto de devoluciones de llamada puede estar activo a la vez, y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="52de1-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="52de1-114">Por lo tanto, si un generador de perfiles llama a las el [SetEnterLeaveFunctionHooks2 (método)](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y `SetEnterLeaveFunctionHooks3` método `SetEnterLeaveFunctionHooks3` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="52de1-114">Therefore, if a profiler calls both the [SetEnterLeaveFunctionHooks2 Method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and the `SetEnterLeaveFunctionHooks3` method, `SetEnterLeaveFunctionHooks3` is used.</span></span>  
  
 <span data-ttu-id="52de1-115">El `SetEnterLeaveFunctionHooks3` solo desde el generador de perfiles puede llamar al método [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="52de1-115">The `SetEnterLeaveFunctionHooks3` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52de1-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52de1-116">Requirements</span></span>  
 <span data-ttu-id="52de1-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52de1-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52de1-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52de1-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52de1-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52de1-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52de1-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52de1-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52de1-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="52de1-121">See Also</span></span>  
 [<span data-ttu-id="52de1-122">SetEnterLeaveFunctionHooks3WithInfo</span><span class="sxs-lookup"><span data-stu-id="52de1-122">SetEnterLeaveFunctionHooks3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3withinfo-method.md)  
 [<span data-ttu-id="52de1-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="52de1-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="52de1-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="52de1-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="52de1-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="52de1-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="52de1-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="52de1-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="52de1-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="52de1-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="52de1-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="52de1-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="52de1-129">Funciones estáticas globales de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="52de1-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 [<span data-ttu-id="52de1-130">ICorProfilerInfo3</span><span class="sxs-lookup"><span data-stu-id="52de1-130">ICorProfilerInfo3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="52de1-131">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="52de1-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="52de1-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="52de1-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
