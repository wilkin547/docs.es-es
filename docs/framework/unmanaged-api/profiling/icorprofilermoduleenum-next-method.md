---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 974879b854f7a4c18aa4625ea88abb4953123f3e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33456155"
---
# <a name="icorprofilermoduleenumnext-method"></a><span data-ttu-id="d9f35-102">ICorProfilerModuleEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="d9f35-102">ICorProfilerModuleEnum::Next Method</span></span>
<span data-ttu-id="d9f35-103">Obtiene el número especificado de módulos contiguos de una colección secuencial de módulos, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="d9f35-103">Gets the specified number of contiguous modules from a sequential collection of modules, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9f35-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d9f35-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    ModuleID ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="d9f35-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d9f35-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="d9f35-106">[in] Número de módulos para recuperar.</span><span class="sxs-lookup"><span data-stu-id="d9f35-106">[in] The number of modules to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="d9f35-107">[out] Matriz de valores `ModuleID`, cada uno de los cuales representa un módulo recuperado.</span><span class="sxs-lookup"><span data-stu-id="d9f35-107">[out] An array of `ModuleID` values, each of which represents a retrieved module.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d9f35-108">[out] Puntero al número de elementos realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="d9f35-108">[out] A pointer to the number of elements actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d9f35-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d9f35-109">Return Value</span></span>  
 <span data-ttu-id="d9f35-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="d9f35-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="d9f35-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d9f35-111">HRESULT</span></span>|<span data-ttu-id="d9f35-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="d9f35-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d9f35-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9f35-113">S_OK</span></span>|<span data-ttu-id="d9f35-114">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="d9f35-114">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="d9f35-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="d9f35-115">S_FALSE</span></span>|<span data-ttu-id="d9f35-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="d9f35-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d9f35-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d9f35-117">Requirements</span></span>  
 <span data-ttu-id="d9f35-118">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d9f35-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d9f35-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="d9f35-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="d9f35-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d9f35-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d9f35-121">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d9f35-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d9f35-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="d9f35-122">See Also</span></span>  
 [<span data-ttu-id="d9f35-123">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d9f35-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)  
 [<span data-ttu-id="d9f35-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="d9f35-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
