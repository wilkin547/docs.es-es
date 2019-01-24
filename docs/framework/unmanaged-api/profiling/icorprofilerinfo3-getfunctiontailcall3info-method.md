---
title: ICorProfilerInfo3::GetFunctionTailcall3Info (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo3.GetFunctionTailcall3Info Method
api_location:
- Mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info
helpviewer_keywords:
- ICorProfilerInfo3::GetFunctionTailcall3Info method [.NET Framework profiling]
- GetFunctionTailcall3Info method [.NET Framework profiling]
ms.assetid: afdb5ac9-5bf5-4b91-b7cb-f81db23d7da3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9a91684ea3712c8fe20d1902f86e3880bf0ad340
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54660286"
---
# <a name="icorprofilerinfo3getfunctiontailcall3info-method"></a><span data-ttu-id="651b8-102">ICorProfilerInfo3::GetFunctionTailcall3Info (Método)</span><span class="sxs-lookup"><span data-stu-id="651b8-102">ICorProfilerInfo3::GetFunctionTailcall3Info Method</span></span>
<span data-ttu-id="651b8-103">Proporciona el marco de pila de la función que se va a notificar al generador de perfiles la [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="651b8-103">Provides the stack frame of the function that is being reported to the profiler by the [FunctionTailcall3WithInfo](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md) function.</span></span> <span data-ttu-id="651b8-104">Solo se puede llamar a este método durante la devolución de llamada `FunctionTailcall3WithInfo`.</span><span class="sxs-lookup"><span data-stu-id="651b8-104">This method can be called only during the `FunctionTailcall3WithInfo` callback.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="651b8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="651b8-105">Syntax</span></span>  
  
```  
HRESULT GetFunctionTailcall3Info(   
            [in]  FunctionID functionId,   
            [in]  COR_PRF_ELT_INFO eltInfo,  
            [out] COR_PRF_FRAME_INFO *pFrameInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="651b8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="651b8-106">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="651b8-107">[in] El `FunctionID` de la función que devuelve.</span><span class="sxs-lookup"><span data-stu-id="651b8-107">[in] The `FunctionID` of the function that is returning.</span></span>  
  
 `eltInfo`  
 <span data-ttu-id="651b8-108">[in] Controlador opaco que representa información sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="651b8-108">[in] An opaque handle that represents information about a given stack frame.</span></span> <span data-ttu-id="651b8-109">El generador de perfiles debe proporcionar el mismo `eltInfo` que no se proporcionó para el generador de perfiles mediante el `FunctionTailcall3WithInfo` función.</span><span class="sxs-lookup"><span data-stu-id="651b8-109">The profiler should provide the same `eltInfo` that was given to the profiler by the `FunctionTailcall3WithInfo` function.</span></span>  
  
 `pFrameInfo`  
 <span data-ttu-id="651b8-110">[out] Controlador opaco que representa información genérica sobre un marco de pila determinado.</span><span class="sxs-lookup"><span data-stu-id="651b8-110">[out] An opaque handle that represents generics information about a given stack frame.</span></span> <span data-ttu-id="651b8-111">Este identificador es válido solo durante la devolución de llamada `FunctionTailcall3WithInfo` en la que el generador de perfiles llamó al método `GetFunctionTailcall3Info`.</span><span class="sxs-lookup"><span data-stu-id="651b8-111">This handle is valid only during the `FunctionTailcall3WithInfo` callback in which the profiler called the `GetFunctionTailcall3Info` method.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="651b8-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="651b8-112">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="651b8-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="651b8-113">Requirements</span></span>  
 <span data-ttu-id="651b8-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="651b8-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="651b8-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="651b8-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="651b8-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="651b8-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="651b8-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="651b8-117">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="651b8-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="651b8-118">See also</span></span>
- [<span data-ttu-id="651b8-119">FunctionEnter3WithInfo</span><span class="sxs-lookup"><span data-stu-id="651b8-119">FunctionEnter3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionenter3withinfo-function.md)
- [<span data-ttu-id="651b8-120">FunctionLeave3WithInfo</span><span class="sxs-lookup"><span data-stu-id="651b8-120">FunctionLeave3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functionleave3withinfo-function.md)
- [<span data-ttu-id="651b8-121">FunctionTailcall3WithInfo</span><span class="sxs-lookup"><span data-stu-id="651b8-121">FunctionTailcall3WithInfo</span></span>](../../../../docs/framework/unmanaged-api/profiling/functiontailcall3withinfo-function.md)
- [<span data-ttu-id="651b8-122">ICorProfilerInfo3 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="651b8-122">ICorProfilerInfo3 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo3-interface.md)
- [<span data-ttu-id="651b8-123">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="651b8-123">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
- [<span data-ttu-id="651b8-124">Generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="651b8-124">Profiling</span></span>](../../../../docs/framework/unmanaged-api/profiling/index.md)
