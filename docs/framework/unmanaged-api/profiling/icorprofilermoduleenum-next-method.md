---
description: 'Más información acerca de: ICorProfilerModuleEnum:: Next (método)'
title: ICorProfilerModuleEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Next
helpviewer_keywords:
- ICorProfilerModuleEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerModuleEnum interface [.NET Framework profiling]
ms.assetid: a3cea59d-7622-4323-897a-0a464c40f77f
topic_type:
- apiref
ms.openlocfilehash: 06c9528d5468847a905e84fe38591c9b5ef3ee44
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798997"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="d9d48-103">ICorProfilerModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="d9d48-103">ICorProfilerModuleEnum::Next Method</span></span>

<span data-ttu-id="d9d48-104">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d9d48-104">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9d48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9d48-105">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9d48-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9d48-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="d9d48-107">[in] Número de módulos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="d9d48-107">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="d9d48-108">[out] Matriz de valores `ModuleID`, cada uno de los cuales representa un módulo recuperado.</span><span class="sxs-lookup"><span data-stu-id="d9d48-108">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d9d48-109">[out] Puntero al número de elementos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="d9d48-109">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9d48-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9d48-110">Return Value</span></span>  

 <span data-ttu-id="d9d48-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d9d48-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d9d48-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9d48-112">HRESULT</span></span>|<span data-ttu-id="d9d48-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9d48-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9d48-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9d48-114">S_OK</span></span>|<span data-ttu-id="d9d48-115">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="d9d48-115">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="d9d48-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d9d48-116">S_FALSE</span></span>|<span data-ttu-id="d9d48-117">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="d9d48-117">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9d48-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9d48-118">Requirements</span></span>  

 <span data-ttu-id="d9d48-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9d48-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9d48-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9d48-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9d48-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9d48-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9d48-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9d48-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9d48-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9d48-123">See also</span></span>

- [<span data-ttu-id="d9d48-124">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9d48-124">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="d9d48-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9d48-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
