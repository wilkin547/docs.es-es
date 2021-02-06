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
ms.openlocfilehash: 1acea6943e74e65e4359c7da590d3888736dbd6c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99647601"
---
# <a name="icorprofilerinfogetfunctionfromip-method"></a><span data-ttu-id="b3f5e-103">ICorProfilerInfo::GetFunctionFromIP (Método)</span><span class="sxs-lookup"><span data-stu-id="b3f5e-103">ICorProfilerInfo::GetFunctionFromIP Method</span></span>

<span data-ttu-id="b3f5e-104">Asigna un puntero de instrucción de código administrado a un `FunctionID` .</span><span class="sxs-lookup"><span data-stu-id="b3f5e-104">Maps a managed code instruction pointer to a `FunctionID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b3f5e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b3f5e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFunctionFromIP(  
    [in]  LPCBYTE    ip,  
    [out] FunctionID *pFunctionId);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b3f5e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b3f5e-106">Parameters</span></span>

- `ip`

  <span data-ttu-id="b3f5e-107">\[in] el puntero de instrucción en código administrado.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-107">\[in] The instruction pointer in managed code.</span></span>

- `pFunctionId`

  <span data-ttu-id="b3f5e-108">\[out] el identificador de función devuelto.</span><span class="sxs-lookup"><span data-stu-id="b3f5e-108">\[out] The returned function ID.</span></span>

## <a name="requirements"></a><span data-ttu-id="b3f5e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b3f5e-109">Requirements</span></span>  

 <span data-ttu-id="b3f5e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b3f5e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b3f5e-111">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b3f5e-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b3f5e-112">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b3f5e-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b3f5e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b3f5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b3f5e-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b3f5e-114">See also</span></span>

- [<span data-ttu-id="b3f5e-115">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b3f5e-115">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
