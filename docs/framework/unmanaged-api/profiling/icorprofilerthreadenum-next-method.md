---
title: "ICorProfilerThreadEnum::Next (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerThreadEnum.Next
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: bfefb140b49a606487f1fe2bbdfb8c6a3b5c6fc1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="469a8-102">ICorProfilerThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="469a8-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="469a8-103">Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="469a8-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="469a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="469a8-104">Syntax</span></span>  
  
```  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="469a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="469a8-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="469a8-106">[in] El número de subprocesos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="469a8-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="469a8-107">[out] Matriz de valores `ThreadID`, cada uno de los cuales representa un subproceso recuperado.</span><span class="sxs-lookup"><span data-stu-id="469a8-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="469a8-108">[out] Puntero al número de subprocesos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="469a8-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="469a8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="469a8-109">Return Value</span></span>  
 <span data-ttu-id="469a8-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="469a8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="469a8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="469a8-111">HRESULT</span></span>|<span data-ttu-id="469a8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="469a8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="469a8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="469a8-113">S_OK</span></span>|<span data-ttu-id="469a8-114">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="469a8-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="469a8-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="469a8-115">S_FALSE</span></span>|<span data-ttu-id="469a8-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="469a8-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="469a8-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="469a8-117">Requirements</span></span>  
 <span data-ttu-id="469a8-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="469a8-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="469a8-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="469a8-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="469a8-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="469a8-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="469a8-121">**Versiones de .NET framework:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="469a8-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="469a8-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="469a8-122">See Also</span></span>  
 [<span data-ttu-id="469a8-123">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="469a8-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)  
 [<span data-ttu-id="469a8-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="469a8-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
