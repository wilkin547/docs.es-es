---
description: 'Más información sobre: ICorProfilerInfo4:: Getfunctionfromip2 ((método)'
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
ms.openlocfilehash: f6abda7c9e7d4abcc0f0b256d6a7785cea205d7a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99686809"
---
# <a name="icorprofilerinfo4getfunctionfromip2-method"></a><span data-ttu-id="a9452-103">ICorProfilerInfo4::GetFunctionFromIP2 (Método)</span><span class="sxs-lookup"><span data-stu-id="a9452-103">ICorProfilerInfo4::GetFunctionFromIP2 Method</span></span>

<span data-ttu-id="a9452-104">Asigna un puntero de instrucción de código administrado a la versión recompilada con JIT de una función.</span><span class="sxs-lookup"><span data-stu-id="a9452-104">Maps a managed code instruction pointer to the JIT-recompiled version of a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9452-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9452-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP2(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId,  
    [out] ReJITID *pReJitId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a9452-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9452-106">Parameters</span></span>  

 `ip`  
 <span data-ttu-id="a9452-107">de Puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="a9452-107">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="a9452-108">enuncia IDENTIFICADOR de la función.</span><span class="sxs-lookup"><span data-stu-id="a9452-108">[out] The function ID.</span></span>  
  
 `pReJitId`  
 <span data-ttu-id="a9452-109">enuncia La identidad de la versión recompilada con JIT de la función.</span><span class="sxs-lookup"><span data-stu-id="a9452-109">[out] The identity of the JIT-recompiled version of the function.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a9452-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a9452-110">Remarks</span></span>  

 <span data-ttu-id="a9452-111">`GetFunctionFromIP2` es similar a `GetFunctionFromIP` , con la salvedad de que obtiene el identificador de recompilación JIT en lugar del identificador de función de la función que contiene la dirección IP especificada.</span><span class="sxs-lookup"><span data-stu-id="a9452-111">`GetFunctionFromIP2` is similar to `GetFunctionFromIP`, except that it gets the JIT-recompiled ID instead of the function ID of the function that contains the specified IP address.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9452-112">`GetFunctionFromIP2` puede desencadenar una recolección de elementos no utilizados, mientras que `GetFunctionFromIP` no.</span><span class="sxs-lookup"><span data-stu-id="a9452-112">`GetFunctionFromIP2` can trigger a garbage collection, whereas `GetFunctionFromIP` will not.</span></span>  <span data-ttu-id="a9452-113">Para obtener más información, vea [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span><span class="sxs-lookup"><span data-stu-id="a9452-113">For more information, see [CORPROF_E_UNSUPPORTED_CALL_SEQUENCE HRESULT](corprof-e-unsupported-call-sequence-hresult.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a9452-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9452-114">Requirements</span></span>  

 <span data-ttu-id="a9452-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9452-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a9452-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="a9452-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="a9452-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a9452-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a9452-118">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9452-118">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a9452-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9452-119">See also</span></span>

- [<span data-ttu-id="a9452-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9452-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
