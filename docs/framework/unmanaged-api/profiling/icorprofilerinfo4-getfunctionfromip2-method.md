---
title: "ICorProfilerInfo4::GetFunctionFromIP2 (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4f354bdc198a8060c7241a2b9bdb472bee5ed7b6
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="f7205-102">ICorProfilerInfo4::GetFunctionFromIP2 (Método)</span><span class="sxs-lookup"><span data-stu-id="f7205-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="f7205-103">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función.</span><span class="sxs-lookup"><span data-stu-id="f7205-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7205-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7205-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7205-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7205-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="f7205-106">[in] El puntero de instrucción en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="f7205-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="f7205-107">[out] El identificador de función.</span><span class="sxs-lookup"><span data-stu-id="f7205-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="f7205-108">[out] La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="f7205-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7205-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7205-109">Remarks</span></span>  
 <span data-ttu-id="f7205-110">`GetFunctionFromIP2`es similar a `GetFunctionFromIP`, excepto en que obtiene el identificador recompilado con JIT en lugar de lo Id. de función de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="f7205-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f7205-111">`GetFunctionFromIP2`puede desencadenar una recolección, mientras que `GetFunctionFromIP` no lo hará.</span><span class="sxs-lookup"><span data-stu-id="f7205-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="f7205-112">Para obtener más información, consulte [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="f7205-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7205-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7205-113">Requirements</span></span>  
 <span data-ttu-id="f7205-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7205-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7205-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7205-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7205-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7205-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7205-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7205-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7205-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7205-118">See Also</span></span>  
 [<span data-ttu-id="f7205-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7205-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
