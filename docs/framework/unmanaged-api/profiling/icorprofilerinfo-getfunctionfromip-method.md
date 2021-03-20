---
description: 'Más información acerca de: ICorProfilerInfo:: Getfunctionfromip ((método)'
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
ms.openlocfilehash: b21b8ad10c76b2e9eaad773315122c3635845a78
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/20/2021
ms.locfileid: "104760254"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="3e136-103">ICorProfilerInfo::GetFunctionFromIP (Método)</span><span class="sxs-lookup"><span data-stu-id="3e136-103">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="3e136-104">Asigna un puntero de instrucción de código administrado a un `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="3e136-104">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3e136-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3e136-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3e136-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3e136-106">Parameters</span></span>

<span data-ttu-id="3e136-107">`ip` de Puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="3e136-107">`ip` [in] The instruction pointer in managed code.</span></span>

<span data-ttu-id="3e136-108">`pFunctionId` enuncia IDENTIFICADOR de función devuelto.</span><span class="sxs-lookup"><span data-stu-id="3e136-108">`pFunctionId` [out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="3e136-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3e136-109">Requirements</span></span>  

 <span data-ttu-id="3e136-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3e136-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3e136-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="3e136-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="3e136-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3e136-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3e136-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3e136-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3e136-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3e136-114">See also</span></span>

- [<span data-ttu-id="3e136-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3e136-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
