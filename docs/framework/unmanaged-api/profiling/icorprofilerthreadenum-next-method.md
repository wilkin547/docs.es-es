---
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
ms.openlocfilehash: e78285c915938c553a9b4012ba57257ac43492ad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447601"
---
# <a name="icorprofilerthreadenumnext-method"></a><span data-ttu-id="65375-102">ICorProfilerThreadEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="65375-102">ICorProfilerThreadEnum::Next Method</span></span>
<span data-ttu-id="65375-103">Obtiene el número especificado de subprocesos contiguos de una colección secuencial de subprocesos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="65375-103">Gets the specified number of contiguous threads from a sequential collection of threads, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65375-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65375-104">Syntax</span></span>  
  
```cpp  
HRESULT Next (    [in]  ULONG      celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
                    ThreadID ids[],  
    [out] ULONG *   pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="65375-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="65375-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="65375-106">[in] Número de subprocesos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="65375-106">[in] The number of threads to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="65375-107">[out] Matriz de valores `ThreadID`, cada uno de los cuales representa un subproceso recuperado.</span><span class="sxs-lookup"><span data-stu-id="65375-107">[out] An array of `ThreadID` values, each of which represents a retrieved thread.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="65375-108">[out] Puntero al número de subprocesos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="65375-108">[out] A pointer to the number of threads actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="65375-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="65375-109">Return Value</span></span>  
 <span data-ttu-id="65375-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="65375-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="65375-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="65375-111">HRESULT</span></span>|<span data-ttu-id="65375-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="65375-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="65375-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="65375-113">S_OK</span></span>|<span data-ttu-id="65375-114">se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="65375-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="65375-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="65375-115">S_FALSE</span></span>|<span data-ttu-id="65375-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="65375-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="65375-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65375-117">Requirements</span></span>  
 <span data-ttu-id="65375-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65375-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65375-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="65375-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="65375-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65375-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65375-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65375-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65375-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="65375-122">See also</span></span>

- [<span data-ttu-id="65375-123">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65375-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="65375-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="65375-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
