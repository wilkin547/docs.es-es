---
title: "ICorProfilerInfo3::GetFunctionLeave3Info (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location: Mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 04f48562e1ddc07ad1ae166ec44ac7de8afd4312
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="81383-102">ICorProfilerInfo3::GetFunctionLeave3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="81383-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="81383-103">Proporciona el marco de pila y el valor devuelto de la función que se va a notificar al generador de perfiles la [función FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="81383-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="81383-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="81383-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81383-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81383-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81383-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81383-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="81383-107">[in] El `FunctionID` de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="81383-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="81383-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="81383-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="81383-109">El generador de perfiles debe proporcionar el mismo `eltInfo` el generador de perfiles que se ha especificado el [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="81383-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="81383-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="81383-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="81383-111">Este identificador es válido solo durante la devolución de llamada `FunctionLeave3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="81383-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="81383-112">[out] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructura que contiene el valor que se devuelve de la función.</span><span class="sxs-lookup"><span data-stu-id="81383-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="81383-113">Para obtener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="81383-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="81383-114">Puede usar el generador de perfiles la [método ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="81383-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="81383-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81383-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81383-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81383-116">Requirements</span></span>  
 <span data-ttu-id="81383-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81383-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81383-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81383-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81383-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81383-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81383-120">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81383-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81383-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="81383-121">See Also</span></span>  
 [<span data-ttu-id="81383-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="81383-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="81383-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="81383-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="81383-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="81383-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="81383-125">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="81383-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="81383-126">Interfaces de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81383-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="81383-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81383-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
