---
title: ICorProfilerFunctionEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
ms.openlocfilehash: df62ad1af0ea91783cb62bb0590b6e36d812de3a
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503073"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="960dc-102">ICorProfilerFunctionEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="960dc-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="960dc-103">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="960dc-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="960dc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="960dc-104">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="960dc-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="960dc-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="960dc-106">[in] Número de funciones para recuperar.</span><span class="sxs-lookup"><span data-stu-id="960dc-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="960dc-107">[out] Matriz de valores `COR_PRF_FUNCTION`, cada uno de los cuales representa una función recuperada.</span><span class="sxs-lookup"><span data-stu-id="960dc-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="960dc-108">[out] Puntero al número de funciones realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="960dc-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="960dc-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="960dc-109">Return Value</span></span>  
 <span data-ttu-id="960dc-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="960dc-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="960dc-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="960dc-111">HRESULT</span></span>|<span data-ttu-id="960dc-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="960dc-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="960dc-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="960dc-113">S_OK</span></span>|<span data-ttu-id="960dc-114">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="960dc-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="960dc-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="960dc-115">S_FALSE</span></span>|<span data-ttu-id="960dc-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="960dc-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="960dc-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="960dc-117">Requirements</span></span>  
 <span data-ttu-id="960dc-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="960dc-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="960dc-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="960dc-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="960dc-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="960dc-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="960dc-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="960dc-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="960dc-122">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="960dc-122">See also</span></span>

- [<span data-ttu-id="960dc-123">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="960dc-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="960dc-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="960dc-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
