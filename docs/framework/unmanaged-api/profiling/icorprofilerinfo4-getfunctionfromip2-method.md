---
title: ICorProfilerInfo4::GetFunctionFromIP2 (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo4.GetFunctionFromIP2
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2
helpviewer_keywords:
- ICorProfilerInfo4::GetFunctionFromIP2 method [.NET Framework profiling]
- GetFunctionFromIP2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
ms.assetid: 46ff70f4-13e9-40a0-802a-0a40abcfc6a0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 51f8768fc3cd73f0fd5bdb84842af03b900fafdf
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495356"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="6edf2-102">ICorProfilerInfo4::GetFunctionFromIP2 (Método)</span><span class="sxs-lookup"><span data-stu-id="6edf2-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="6edf2-103">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función.</span><span class="sxs-lookup"><span data-stu-id="6edf2-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6edf2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6edf2-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6edf2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6edf2-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="6edf2-106">[in] El puntero de instrucción en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="6edf2-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="6edf2-107">[out] El identificador de función.</span><span class="sxs-lookup"><span data-stu-id="6edf2-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="6edf2-108">[out] La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="6edf2-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6edf2-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6edf2-109">Remarks</span></span>  
 <span data-ttu-id="6edf2-110">`GetFunctionFromIP2` es similar a `GetFunctionFromIP`, excepto en que obtiene el identificador recompilado con JIT en lugar del identificador de la función de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="6edf2-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6edf2-111">`GetFunctionFromIP2` puede desencadenar una recolección de elementos, mientras que `GetFunctionFromIP` no lo hará.</span><span class="sxs-lookup"><span data-stu-id="6edf2-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="6edf2-112">Para obtener más información, consulte [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="6edf2-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6edf2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6edf2-113">Requirements</span></span>  
 <span data-ttu-id="6edf2-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6edf2-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6edf2-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="6edf2-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="6edf2-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6edf2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6edf2-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6edf2-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6edf2-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="6edf2-118">See also</span></span>
- [<span data-ttu-id="6edf2-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6edf2-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
