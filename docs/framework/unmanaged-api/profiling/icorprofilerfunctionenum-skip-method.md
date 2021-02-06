---
description: 'Más información acerca de: ICorProfilerFunctionEnum:: Skip (método)'
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
ms.openlocfilehash: 6d176c51788135952127008f2f43545ead1e2369
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99657065"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="5249d-103">ICorProfilerFunctionEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="5249d-103">ICorProfilerFunctionEnum::Skip Method</span></span>

<span data-ttu-id="5249d-104">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="5249d-104">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5249d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5249d-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5249d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5249d-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="5249d-107">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="5249d-107">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5249d-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5249d-108">Return Value</span></span>  

 <span data-ttu-id="5249d-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="5249d-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5249d-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5249d-110">HRESULT</span></span>|<span data-ttu-id="5249d-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="5249d-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5249d-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="5249d-112">S_OK</span></span>|<span data-ttu-id="5249d-113">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="5249d-113">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="5249d-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="5249d-114">S_FALSE</span></span>|<span data-ttu-id="5249d-115">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="5249d-115">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5249d-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5249d-116">Remarks</span></span>  

 <span data-ttu-id="5249d-117">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="5249d-117">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5249d-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5249d-118">Requirements</span></span>  

 <span data-ttu-id="5249d-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5249d-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5249d-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5249d-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5249d-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5249d-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5249d-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5249d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5249d-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="5249d-123">See also</span></span>

- [<span data-ttu-id="5249d-124">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5249d-124">ICorProfilerFunctionEnum Interface</span></span>](icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="5249d-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="5249d-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
