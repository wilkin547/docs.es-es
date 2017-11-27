---
title: "ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a30dde6f406cfb6d1140e7cd8e2a8f8f3ab40006
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="0f847-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="0f847-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="0f847-103">Especifica las funciones implementadas por el generador de perfiles que se llamará en el [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) enlaces de funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="0f847-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0f847-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f847-104">Syntax</span></span>  
  
```  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="0f847-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f847-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="0f847-106">[in] Un puntero a la implementación que se usará como el `FunctionEnter3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0f847-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="0f847-107">[in] Un puntero a la implementación que se usará como el `FunctionLeave3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0f847-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="0f847-108">[in] Un puntero a la implementación que se usará como el `FunctionTailcall3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0f847-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0f847-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0f847-109">Remarks</span></span>  
 <span data-ttu-id="0f847-110">El [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) proporcionan inspección de marco y los argumentos de la pila.</span><span class="sxs-lookup"><span data-stu-id="0f847-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="0f847-111">Para tener acceso a esa información, el `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, o `COR_PRF_ENABLE_FRAME_INFO` marcas tienen que establecerse.</span><span class="sxs-lookup"><span data-stu-id="0f847-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="0f847-112">Puede usar el generador de perfiles la [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento y, a continuación, utilizar el `SetEnterLeaveFunctionHooks3WithInfo` método para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="0f847-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="0f847-113">Únicamente un conjunto de devoluciones de llamada puede estar activo a la vez, y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="0f847-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="0f847-114">Por lo tanto, si llama a un generador de perfiles las [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="0f847-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="0f847-115">El `SetEnterLeaveFunctionHooks3WithInfo` solo desde el generador de perfiles puede llamar al método [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="0f847-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0f847-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f847-116">Requirements</span></span>  
 <span data-ttu-id="0f847-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f847-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0f847-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0f847-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0f847-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0f847-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0f847-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0f847-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f847-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f847-121">See Also</span></span>  
 [<span data-ttu-id="0f847-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="0f847-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)  
 [<span data-ttu-id="0f847-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="0f847-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)  
 [<span data-ttu-id="0f847-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="0f847-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)  
 [<span data-ttu-id="0f847-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="0f847-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)  
 [<span data-ttu-id="0f847-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0f847-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="0f847-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0f847-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="0f847-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="0f847-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="0f847-129">Funciones estáticas globales de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0f847-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)  
 [<span data-ttu-id="0f847-130">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0f847-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="0f847-131">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0f847-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="0f847-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0f847-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
