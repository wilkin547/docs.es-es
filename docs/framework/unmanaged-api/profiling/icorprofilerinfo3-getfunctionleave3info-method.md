---
title: ICorProfilerInfo3::GetFunctionLeave3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionLeave3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionLeave3Info
helpviewer_keywords:
- GetFunctionLeave3Info method [.NET Framework profiling]
- ICorProfilerInfo3::GetFunctionLeave3Info method [.NET Framework profiling]
ms.assetid: df7083d2-fd43-44c7-9ce5-912c25cef0ff
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 70fdc548c02015f0950f009abe94652795cba568
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33459802"
---
# <a name="icorprofilerinfo3getfunctionleave3info-method"></a><span data-ttu-id="436a2-102">ICorProfilerInfo3::GetFunctionLeave3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="436a2-102">ICorProfilerInfo3::GetFunctionLeave3Info Method</span></span>
<span data-ttu-id="436a2-103">Proporciona el marco de pila y el valor devuelto de la función que se va a notificar al generador de perfiles la [función FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="436a2-103">Provides the stack frame and return value of the function that is being reported to the profiler by the [FunctionLeave3WithInfo function](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span> <span data-ttu-id="436a2-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionLeave3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="436a2-104">This method can be called only during the `FunctionLeave3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="436a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="436a2-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionLeave3Info(  
            [in]  FunctionID functionId,  
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo,  
            [out] COR_PRF_FUNCTION_ARGUMENT_RANGE *pRetvalRange);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="436a2-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="436a2-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="436a2-107">[in] El `FunctionID` de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="436a2-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="436a2-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="436a2-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="436a2-109">El generador de perfiles debe proporcionar el mismo `eltInfo` el generador de perfiles que se ha especificado el [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="436a2-109">The profiler should provide the same `eltInfo` that was given to the profiler by the [FunctionLeave3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md) function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="436a2-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="436a2-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="436a2-111">Este identificador es válido solo durante la devolución de llamada `FunctionLeave3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionLeave3Info`.</span><span class="sxs-lookup"><span data-stu-id="436a2-111">This handle is valid only during the `FunctionLeave3WithInfo` callback in which the profiler called the `GetFunctionLeave3Info` method.</span></span>  
  
 `pRetvalRange`  
 <span data-ttu-id="436a2-112">[out] Un puntero a un [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) estructura que contiene el valor que se devuelve de la función.</span><span class="sxs-lookup"><span data-stu-id="436a2-112">[out] A pointer to a [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) structure that contains the value that is returned from the function.</span></span> <span data-ttu-id="436a2-113">Para obtener acceso a información del valor devuelto, el `COR_PRF_ENABLE_FUNCTION_RETVAL` se debe establecer la marca.</span><span class="sxs-lookup"><span data-stu-id="436a2-113">To access return value information, the `COR_PRF_ENABLE_FUNCTION_RETVAL` flag must be set.</span></span> <span data-ttu-id="436a2-114">Puede usar el generador de perfiles la [método ICorProfilerInfo:: SetEventMask](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) para establecer las marcas de evento.</span><span class="sxs-lookup"><span data-stu-id="436a2-114">The profiler can use the [ICorProfilerInfo::SetEventMask method](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-seteventmask-method.md) to set the event flags.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="436a2-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="436a2-115">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="436a2-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="436a2-116">Requirements</span></span>  
 <span data-ttu-id="436a2-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="436a2-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="436a2-118">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="436a2-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="436a2-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="436a2-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="436a2-120">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="436a2-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="436a2-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="436a2-121">See Also</span></span>  
 [<span data-ttu-id="436a2-122">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="436a2-122">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)  
 [<span data-ttu-id="436a2-123">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="436a2-123">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)  
 [<span data-ttu-id="436a2-124">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="436a2-124">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)  
 [<span data-ttu-id="436a2-125">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="436a2-125">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)  
 [<span data-ttu-id="436a2-126">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="436a2-126">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [<span data-ttu-id="436a2-127">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="436a2-127">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
