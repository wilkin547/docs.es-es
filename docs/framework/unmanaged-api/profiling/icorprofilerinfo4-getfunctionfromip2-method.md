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
ms.openlocfilehash: 5153a25ef87d9c06bb46b74945c8eb68eb041682
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443144"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="d0a30-102">ICorProfilerInfo4::GetFunctionFromIP2 (Método)</span><span class="sxs-lookup"><span data-stu-id="d0a30-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>
<span data-ttu-id="d0a30-103">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función.</span><span class="sxs-lookup"><span data-stu-id="d0a30-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d0a30-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0a30-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d0a30-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0a30-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="d0a30-106">de Puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="d0a30-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="d0a30-107">enuncia IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="d0a30-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="d0a30-108">enuncia La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="d0a30-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d0a30-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d0a30-109">Remarks</span></span>  
 <span data-ttu-id="d0a30-110">`GetFunctionFromIP2` es similar a `GetFunctionFromIP`, salvo que obtiene el identificador de recompilación JIT en lugar del identificador de función de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="d0a30-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d0a30-111">`GetFunctionFromIP2` puede desencadenar una recolección de elementos no utilizados, mientras que `GetFunctionFromIP` no lo hará.</span><span class="sxs-lookup"><span data-stu-id="d0a30-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="d0a30-112">Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="d0a30-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](../../../../docs/framework/unmanaged-api/profiling/corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d0a30-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0a30-113">Requirements</span></span>  
 <span data-ttu-id="d0a30-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0a30-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d0a30-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d0a30-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d0a30-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d0a30-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d0a30-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0a30-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d0a30-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0a30-118">See also</span></span>

- [<span data-ttu-id="d0a30-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0a30-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
