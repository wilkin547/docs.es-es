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
ms.openlocfilehash: a522df8abfba1c5837e3136f966935ff1f56d8d2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721548"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="604ff-102">ICorProfilerInfo4::GetFunctionFromIP2 (Método)</span><span class="sxs-lookup"><span data-stu-id="604ff-102">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>

<span data-ttu-id="604ff-103">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función.</span><span class="sxs-lookup"><span data-stu-id="604ff-103">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="604ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="604ff-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="604ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="604ff-105">Parameters</span></span>  

 `ip`  
 <span data-ttu-id="604ff-106">de Puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="604ff-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="604ff-107">enuncia IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="604ff-107">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="604ff-108">enuncia La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="604ff-108">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="604ff-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="604ff-109">Remarks</span></span>  

 <span data-ttu-id="604ff-110">`GetFunctionFromIP2` es similar a `GetFunctionFromIP` , con la salvedad de que obtiene el identificador de recompilación JIT en lugar del identificador de función de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="604ff-110">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="604ff-111">`GetFunctionFromIP2` puede desencadenar una recolección de elementos no utilizados, mientras que `GetFunctionFromIP` no.</span><span class="sxs-lookup"><span data-stu-id="604ff-111">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="604ff-112">Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="604ff-112">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="604ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="604ff-113">Requirements</span></span>  

 <span data-ttu-id="604ff-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="604ff-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="604ff-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="604ff-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="604ff-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="604ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="604ff-117">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="604ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="604ff-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="604ff-118">See also</span></span>

- [<span data-ttu-id="604ff-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="604ff-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
