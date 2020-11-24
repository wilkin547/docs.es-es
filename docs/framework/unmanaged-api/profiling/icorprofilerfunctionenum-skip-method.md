---
title: ICorProfilerFunctionEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Skip Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
- ICorProfilerFunctionEnum::Skip method [.NET Framework profiling]
ms.assetid: 051465b9-e479-494a-804b-c880323b4cbe
topic_type:
- apiref
ms.openlocfilehash: da578e02db0744b1f64c1d392844aa020721e784
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95669267"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="581fa-102">ICorProfilerFunctionEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="581fa-102">ICorProfilerFunctionEnum::Skip Method</span></span>

<span data-ttu-id="581fa-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="581fa-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="581fa-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="581fa-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="581fa-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="581fa-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="581fa-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="581fa-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="581fa-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="581fa-107">Return Value</span></span>  

 <span data-ttu-id="581fa-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="581fa-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="581fa-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="581fa-109">HRESULT</span></span>|<span data-ttu-id="581fa-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="581fa-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="581fa-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="581fa-111">S_OK</span></span>|<span data-ttu-id="581fa-112">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="581fa-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="581fa-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="581fa-113">S_FALSE</span></span>|<span data-ttu-id="581fa-114">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="581fa-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="581fa-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="581fa-115">Remarks</span></span>  

 <span data-ttu-id="581fa-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="581fa-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="581fa-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="581fa-117">Requirements</span></span>  

 <span data-ttu-id="581fa-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="581fa-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="581fa-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="581fa-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="581fa-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="581fa-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="581fa-121">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="581fa-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="581fa-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="581fa-122">See also</span></span>

- [<span data-ttu-id="581fa-123">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="581fa-123">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="581fa-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="581fa-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
