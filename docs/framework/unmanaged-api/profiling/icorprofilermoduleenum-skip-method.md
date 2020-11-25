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
ms.openlocfilehash: 6a967f9a50b3220e2d5e206503330a2bab764c4b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701645"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="51254-102">ICorProfilerModuleEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="51254-102">ICorProfilerModuleEnum::Skip Method</span></span>

<span data-ttu-id="51254-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="51254-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51254-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51254-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="51254-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51254-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="51254-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="51254-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="51254-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51254-107">Return Value</span></span>  

 <span data-ttu-id="51254-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="51254-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="51254-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="51254-109">HRESULT</span></span>|<span data-ttu-id="51254-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="51254-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="51254-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="51254-111">S_OK</span></span>|<span data-ttu-id="51254-112">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="51254-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="51254-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="51254-113">S_FALSE</span></span>|<span data-ttu-id="51254-114">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="51254-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="51254-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51254-115">Remarks</span></span>  

 <span data-ttu-id="51254-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="51254-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51254-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51254-117">Requirements</span></span>  

 <span data-ttu-id="51254-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51254-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51254-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="51254-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="51254-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="51254-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="51254-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51254-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51254-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="51254-122">See also</span></span>

- [<span data-ttu-id="51254-123">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="51254-123">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="51254-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="51254-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
