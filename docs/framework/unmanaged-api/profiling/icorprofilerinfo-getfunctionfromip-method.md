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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2b0859d2f6d4ea2abf72867f2a803132cbd04225
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54568652"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="679f2-102">ICorProfilerInfo::GetFunctionFromIP (Método)</span><span class="sxs-lookup"><span data-stu-id="679f2-102">ICorProfilerInfo::GetFunctionFromIP Method</span></span>
<span data-ttu-id="679f2-103">Asigna un puntero de instrucción de código administrado a un `FunctionID`.</span><span class="sxs-lookup"><span data-stu-id="679f2-103">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="679f2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="679f2-104">Syntax</span></span>  
  
```  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="679f2-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="679f2-105">Parameters</span></span>  
 `ip`  
 <span data-ttu-id="679f2-106">[in] El puntero de instrucción en el código administrado.</span><span class="sxs-lookup"><span data-stu-id="679f2-106">[in] The instruction pointer in managed code.</span></span>  
  
 `pFunctionId`  
 <span data-ttu-id="679f2-107">[out] El identificador de función devuelto.</span><span class="sxs-lookup"><span data-stu-id="679f2-107">[out] The returned function ID.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="679f2-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="679f2-108">Requirements</span></span>  
 <span data-ttu-id="679f2-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="679f2-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="679f2-110">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="679f2-110">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="679f2-111">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="679f2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="679f2-112">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="679f2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="679f2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="679f2-113">See also</span></span>
- [<span data-ttu-id="679f2-114">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="679f2-114">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
