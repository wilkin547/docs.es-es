---
title: ICorProfilerModuleEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerModuleEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerModuleEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerModuleEnum interface [.NET Framework profiling]
- ICorProfilerModuleEnum::Skip method [.NET Framework profiling]
ms.assetid: 8dc29c6a-e2ba-41d8-a1e0-0fdd21421e0b
topic_type:
- apiref
ms.openlocfilehash: fb7a2a6d8bac7e9a67a5275694fc07e0f1d469e1
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76861338"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="67d3b-102">ICorProfilerModuleEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="67d3b-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="67d3b-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="67d3b-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="67d3b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="67d3b-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="67d3b-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="67d3b-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="67d3b-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="67d3b-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="67d3b-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="67d3b-107">Return Value</span></span>  
 <span data-ttu-id="67d3b-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="67d3b-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="67d3b-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="67d3b-109">HRESULT</span></span>|<span data-ttu-id="67d3b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="67d3b-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="67d3b-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="67d3b-111">S_OK</span></span>|<span data-ttu-id="67d3b-112">`celt` elementos se omitieron.</span><span class="sxs-lookup"><span data-stu-id="67d3b-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="67d3b-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="67d3b-113">S_FALSE</span></span>|<span data-ttu-id="67d3b-114">Se omitieron menos de `celt` elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="67d3b-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="67d3b-115">Notas</span><span class="sxs-lookup"><span data-stu-id="67d3b-115">Remarks</span></span>  
 <span data-ttu-id="67d3b-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="67d3b-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="67d3b-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="67d3b-117">Requirements</span></span>  
 <span data-ttu-id="67d3b-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="67d3b-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="67d3b-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="67d3b-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="67d3b-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="67d3b-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="67d3b-121">**.NET Framework versiones:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="67d3b-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67d3b-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="67d3b-122">See also</span></span>

- [<span data-ttu-id="67d3b-123">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="67d3b-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="67d3b-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="67d3b-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
