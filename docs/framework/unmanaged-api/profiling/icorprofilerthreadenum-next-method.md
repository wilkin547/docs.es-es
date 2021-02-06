---
description: 'Más información sobre: ICorProfilerThreadEnum:: Next (método)'
title: ICorProfilerThreadEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Next
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Next
helpviewer_keywords:
- ICorProfilerThreadEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerThreadEnum interface [.NET Framework profiling]
ms.assetid: f3535279-3c63-41a2-ab0e-a129dc5a01e8
topic_type:
- apiref
ms.openlocfilehash: 74567624cbe5042b8ab63a28e7fb07e9f708a959
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636348"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="14602-103">ICorProfilerThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="14602-103">ICorProfilerThreadEnum::Next Method</span></span>

<span data-ttu-id="14602-104">Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="14602-104">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14602-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14602-105">Syntax</span></span>  
  
```cpp  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="14602-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14602-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="14602-107">[in] Número de subprocesos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="14602-107">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="14602-108">[out] Matriz de valores `ThreadID`, cada uno de los cuales representa un subproceso recuperado.</span><span class="sxs-lookup"><span data-stu-id="14602-108">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="14602-109">[out] Puntero al número de subprocesos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="14602-109">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="14602-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14602-110">Return Value</span></span>  

 <span data-ttu-id="14602-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="14602-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="14602-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="14602-112">HRESULT</span></span>|<span data-ttu-id="14602-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="14602-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="14602-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="14602-114">S_OK</span></span>|<span data-ttu-id="14602-115">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="14602-115">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="14602-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="14602-116">S_FALSE</span></span>|<span data-ttu-id="14602-117">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="14602-117">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="14602-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14602-118">Requirements</span></span>  

 <span data-ttu-id="14602-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14602-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14602-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="14602-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="14602-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="14602-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="14602-122">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14602-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14602-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="14602-123">See also</span></span>

- [<span data-ttu-id="14602-124">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="14602-124">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="14602-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="14602-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
