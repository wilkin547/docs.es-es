---
description: 'Más información acerca de: ICorProfilerFunctionEnum:: Next (método)'
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
ms.openlocfilehash: ff525cfa4cc1ea1dee63b8bbd2e37eaf89fc3e74
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99737524"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="9fe8a-103">ICorProfilerFunctionEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="9fe8a-103">ICorProfilerFunctionEnum::Next Method</span></span>

<span data-ttu-id="9fe8a-104">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-104">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fe8a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fe8a-105">Syntax</span></span>  
  
```cpp  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fe8a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fe8a-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9fe8a-107">[in] Número de funciones para recuperar.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-107">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="9fe8a-108">[out] Matriz de valores `COR_PRF_FUNCTION`, cada uno de los cuales representa una función recuperada.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-108">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="9fe8a-109">[out] Puntero al número de funciones realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-109">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fe8a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9fe8a-110">Return Value</span></span>  

 <span data-ttu-id="9fe8a-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9fe8a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fe8a-112">HRESULT</span></span>|<span data-ttu-id="9fe8a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fe8a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fe8a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fe8a-114">S_OK</span></span>|<span data-ttu-id="9fe8a-115">Se devolvieron `celt` elementos.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-115">`celt` elements were returned.</span></span>|  
|<span data-ttu-id="9fe8a-116">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9fe8a-116">S_FALSE</span></span>|<span data-ttu-id="9fe8a-117">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="9fe8a-117">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="9fe8a-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fe8a-118">Requirements</span></span>  

 <span data-ttu-id="9fe8a-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fe8a-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fe8a-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fe8a-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fe8a-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fe8a-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fe8a-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fe8a-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fe8a-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fe8a-123">See also</span></span>

- [<span data-ttu-id="9fe8a-124">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9fe8a-124">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="9fe8a-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9fe8a-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
