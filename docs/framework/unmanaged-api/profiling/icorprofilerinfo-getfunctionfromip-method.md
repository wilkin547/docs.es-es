---
title: ICorProfilerInfo::GetFunctionFromIP (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetFunctionFromIP
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetFunctionFromIP
helpviewer_keywords:
- GetFunctionFromIP method [.NET Framework profiling]
- ICorProfilerInfo::GetFunctionFromIP method [.NET Framework profiling]
ms.assetid: f069802a-198f-46dd-9f09-4f77adffc9ba
topic_type:
- apiref
ms.openlocfilehash: 4a7e21ae60253c741b57674212e0ecabdd844d2d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722569"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="da2a5-102">ICorProfilerInfo::GetFunctionFromIP (Método)</span><span class="sxs-lookup"><span data-stu-id="da2a5-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="da2a5-103">Asigna un puntero de instrucción de código administrado a un `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="da2a5-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2a5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da2a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2a5-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da2a5-105">Parameters</span></span>

- `ip`

  <span data-ttu-id="da2a5-106">\[in] el puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="da2a5-106">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="da2a5-107">\[out] el identificador de función devuelto.</span><span class="sxs-lookup"><span data-stu-id="da2a5-107">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="da2a5-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da2a5-108">Requirements</span></span>  

 <span data-ttu-id="da2a5-109">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da2a5-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2a5-110">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="da2a5-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="da2a5-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="da2a5-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="da2a5-112">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2a5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2a5-113">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da2a5-113">See also</span></span>

- [<span data-ttu-id="da2a5-114">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="da2a5-114">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
