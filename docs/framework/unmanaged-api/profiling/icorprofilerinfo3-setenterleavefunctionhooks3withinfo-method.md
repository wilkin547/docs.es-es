---
title: ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.SetEnterLeaveFunctionHooks3WithInfo Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo
helpviewer_keywords:
- SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
- ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo method [.NET Framework profiling]
ms.assetid: ca8ea534-e441-47b8-be85-466410988c0a
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bb07fb7d5dfaad8623c269a86d2e1182b200cb61
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780898"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="e0230-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="e0230-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="e0230-103">Especifica las funciones implementadas por el generador de perfiles que se llamará en el [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) enlaces de funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="e0230-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0230-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0230-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0230-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0230-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="e0230-106">[in] Un puntero a la implementación que se usará como el `FunctionEnter3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e0230-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="e0230-107">[in] Un puntero a la implementación que se usará como el `FunctionLeave3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e0230-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="e0230-108">[in] Un puntero a la implementación que se usará como el `FunctionTailcall3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e0230-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0230-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0230-109">Remarks</span></span>  
 <span data-ttu-id="e0230-110">El [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), y [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) proporcionan inspección de marco y los argumentos de la pila.</span><span class="sxs-lookup"><span data-stu-id="e0230-110">The [FunctionEnter3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md), [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="e0230-111">Para obtener acceso a esa información, el `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, o `COR_PRF_ENABLE_FRAME_INFO` marcas deben establecerse.</span><span class="sxs-lookup"><span data-stu-id="e0230-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="e0230-112">El generador de perfiles puede utilizar el [ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) método para establecer las marcas de evento y, a continuación, utilice el `SetEnterLeaveFunctionHooks3WithInfo` método para registrar su implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="e0230-112">The profiler can use the [ICorProfilerInfo::SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="e0230-113">Solo un conjunto de devoluciones de llamada puede estar activo en un momento y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="e0230-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="e0230-114">Por lo tanto, si un generador de perfiles llama a ambos [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e0230-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="e0230-115">El `SetEnterLeaveFunctionHooks3WithInfo` método puede llamarse solo desde el generador de perfiles [ICorProfilerCallback:: Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="e0230-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0230-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0230-116">Requirements</span></span>  
 <span data-ttu-id="e0230-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0230-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0230-118">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0230-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0230-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0230-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e0230-120">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e0230-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0230-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0230-121">See also</span></span>

- [<span data-ttu-id="e0230-122">SetEnterLeaveFunctionHooks3</span><span class="sxs-lookup"><span data-stu-id="e0230-122">SetEnterLeaveFunctionHooks3</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="e0230-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="e0230-123">FunctionEnter3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3-function.md)
- [<span data-ttu-id="e0230-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="e0230-124">FunctionLeave3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3-function.md)
- [<span data-ttu-id="e0230-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="e0230-125">FunctionTailcall3</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3-function.md)
- [<span data-ttu-id="e0230-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e0230-126">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="e0230-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e0230-127">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="e0230-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="e0230-128">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="e0230-129">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e0230-129">Profiling Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-global-static-functions.md)
- [<span data-ttu-id="e0230-130">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0230-130">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="e0230-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e0230-131">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="e0230-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e0230-132">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
