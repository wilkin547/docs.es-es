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
ms.openlocfilehash: d40cb424306535cc502d930dd61e6a1e254667da
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84496183"
---
# <a name="icorprofilerinfo3setenterleavefunctionhooks3withinfo-method"></a><span data-ttu-id="1cc16-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="1cc16-102">ICorProfilerInfo3::SetEnterLeaveFunctionHooks3WithInfo Method</span></span>
<span data-ttu-id="1cc16-103">Especifica las funciones implementadas por el generador de perfiles a las que se llamará en los enlaces [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) de las funciones administradas.</span><span class="sxs-lookup"><span data-stu-id="1cc16-103">Specifies the profiler-implemented functions that will be called on the [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks of managed functions.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cc16-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1cc16-104">Syntax</span></span>  
  
```cpp  
HRESULT SetEnterLeaveFunctionHooks3WithInfo(  
            [in] FunctionEnter3WithInfo    *pFuncEnter3,  
            [in] FunctionLeave3withInfo    *pFuncLeave3,  
            [in] FunctionTailcall3WithInfo *pFuncTailcall3);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cc16-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1cc16-105">Parameters</span></span>  
 `pFuncEnter3`  
 <span data-ttu-id="1cc16-106">de Puntero a la implementación de que se va a utilizar como `FunctionEnter3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1cc16-106">[in] A pointer to the implementation to be used as the `FunctionEnter3WithInfo` callback.</span></span>  
  
 `pFuncLeave3`  
 <span data-ttu-id="1cc16-107">de Puntero a la implementación de que se va a utilizar como `FunctionLeave3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1cc16-107">[in] A pointer to the implementation to be used as the `FunctionLeave3WithInfo` callback.</span></span>  
  
 `pFuncTailcall3`  
 <span data-ttu-id="1cc16-108">de Puntero a la implementación de que se va a utilizar como `FunctionTailcall3WithInfo` devolución de llamada.</span><span class="sxs-lookup"><span data-stu-id="1cc16-108">[in] A pointer to the implementation to be used as the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1cc16-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1cc16-109">Remarks</span></span>  
 <span data-ttu-id="1cc16-110">Los enlaces [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md)y [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) proporcionan el marco de pila y la inspección de argumentos.</span><span class="sxs-lookup"><span data-stu-id="1cc16-110">The [FunctionEnter3WithInfo](functionenter3withinfo-function.md), [FunctionLeave3WithInfo](functionleave3withinfo-function.md), and [FunctionTailcall3WithInfo](functiontailcall3withinfo-function.md) hooks provide stack frame and argument inspection.</span></span> <span data-ttu-id="1cc16-111">Para tener acceso a esa información `COR_PRF_ENABLE_FUNCTION_ARGS` , `COR_PRF_ENABLE_FUNCTION_RETVAL` se deben establecer las marcas,, y/o `COR_PRF_ENABLE_FRAME_INFO` .</span><span class="sxs-lookup"><span data-stu-id="1cc16-111">To access that information, the `COR_PRF_ENABLE_FUNCTION_ARGS`, `COR_PRF_ENABLE_FUNCTION_RETVAL`, and/or `COR_PRF_ENABLE_FRAME_INFO` flags have to be set.</span></span> <span data-ttu-id="1cc16-112">El generador de perfiles puede utilizar el método [ICorProfilerInfo:: SetEventMask](icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento y, a continuación, utilizar el `SetEnterLeaveFunctionHooks3WithInfo` método para registrar la implementación de esta función.</span><span class="sxs-lookup"><span data-stu-id="1cc16-112">The profiler can use the [ICorProfilerInfo::SetEventMask](icorprofilerinfo-seteventmask-method.md) method to set the event flags, and then use the `SetEnterLeaveFunctionHooks3WithInfo` method to register your implementation of this function.</span></span>  
  
 <span data-ttu-id="1cc16-113">Solo un conjunto de devoluciones de llamada puede estar activo a la vez y la versión más reciente tiene prioridad.</span><span class="sxs-lookup"><span data-stu-id="1cc16-113">Only one set of callbacks may be active at a time, and the newest version takes precedence.</span></span> <span data-ttu-id="1cc16-114">Por lo tanto, si un generador de perfiles llama a [SetEnterLeaveFunctionHooks2 (](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) y `SetEnterLeaveFunctionHooks3WithInfo` , `SetEnterLeaveFunctionHooks3WithInfo` se usa.</span><span class="sxs-lookup"><span data-stu-id="1cc16-114">Therefore, if a profiler calls both [SetEnterLeaveFunctionHooks2](icorprofilerinfo2-setenterleavefunctionhooks2-method.md) and `SetEnterLeaveFunctionHooks3WithInfo`, `SetEnterLeaveFunctionHooks3WithInfo` is used.</span></span>  
  
 <span data-ttu-id="1cc16-115">`SetEnterLeaveFunctionHooks3WithInfo`Solo se puede llamar al método desde la devolución de llamada [ICorProfilerCallback:: Initialize](icorprofilercallback-initialize-method.md) del generador de perfiles.</span><span class="sxs-lookup"><span data-stu-id="1cc16-115">The `SetEnterLeaveFunctionHooks3WithInfo` method may be called only from the profiler's [ICorProfilerCallback::Initialize](icorprofilercallback-initialize-method.md) callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cc16-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1cc16-116">Requirements</span></span>  
 <span data-ttu-id="1cc16-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1cc16-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cc16-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="1cc16-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="1cc16-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="1cc16-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="1cc16-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cc16-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cc16-121">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="1cc16-121">See also</span></span>

- [<span data-ttu-id="1cc16-122">Setenterleavefunctionhooks3 (</span><span class="sxs-lookup"><span data-stu-id="1cc16-122">SetEnterLeaveFunctionHooks3</span></span>](icorprofilerinfo3-setenterleavefunctionhooks3-method.md)
- [<span data-ttu-id="1cc16-123">FunctionEnter3</span><span class="sxs-lookup"><span data-stu-id="1cc16-123">FunctionEnter3</span></span>](functionenter3-function.md)
- [<span data-ttu-id="1cc16-124">FunctionLeave3</span><span class="sxs-lookup"><span data-stu-id="1cc16-124">FunctionLeave3</span></span>](functionleave3-function.md)
- [<span data-ttu-id="1cc16-125">FunctionTailcall3</span><span class="sxs-lookup"><span data-stu-id="1cc16-125">FunctionTailcall3</span></span>](functiontailcall3-function.md)
- [<span data-ttu-id="1cc16-126">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1cc16-126">FunctionEnter3WithInfo</span></span>](functionenter3withinfo-function.md)
- [<span data-ttu-id="1cc16-127">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1cc16-127">FunctionLeave3WithInfo</span></span>](functionleave3withinfo-function.md)
- [<span data-ttu-id="1cc16-128">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="1cc16-128">FunctionTailcall3WithInfo</span></span>](functiontailcall3withinfo-function.md)
- [<span data-ttu-id="1cc16-129">Funciones estáticas globales para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1cc16-129">Profiling Global Static Functions</span></span>](profiling-global-static-functions.md)
- [<span data-ttu-id="1cc16-130">ICorProfilerInfo3 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1cc16-130">ICorProfilerInfo3 Interface</span></span>](icorprofilerinfo3-interface.md)
- [<span data-ttu-id="1cc16-131">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1cc16-131">Profiling Interfaces</span></span>](profiling-interfaces.md)
- [<span data-ttu-id="1cc16-132">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="1cc16-132">Profiling</span></span>](index.md)
