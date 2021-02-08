---
description: 'Más información acerca de: ICorProfilerModuleEnum:: Skip (método)'
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
ms.openlocfilehash: 4d814e5e9e369fe286b471fadc9675345cfb5b94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99798971"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="9d5a7-103">ICorProfilerModuleEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="9d5a7-103">ICorProfilerModuleEnum::Skip Method</span></span>

<span data-ttu-id="9d5a7-104">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="9d5a7-104">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d5a7-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d5a7-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9d5a7-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d5a7-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9d5a7-107">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="9d5a7-107">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9d5a7-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9d5a7-108">Return Value</span></span>  

 <span data-ttu-id="9d5a7-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9d5a7-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9d5a7-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9d5a7-110">HRESULT</span></span>|<span data-ttu-id="9d5a7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9d5a7-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9d5a7-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9d5a7-112">S_OK</span></span>|<span data-ttu-id="9d5a7-113">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="9d5a7-113">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="9d5a7-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9d5a7-114">S_FALSE</span></span>|<span data-ttu-id="9d5a7-115">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="9d5a7-115">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9d5a7-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9d5a7-116">Remarks</span></span>  

 <span data-ttu-id="9d5a7-117">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="9d5a7-117">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d5a7-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d5a7-118">Requirements</span></span>  

 <span data-ttu-id="9d5a7-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d5a7-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d5a7-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9d5a7-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9d5a7-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9d5a7-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9d5a7-122">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d5a7-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d5a7-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d5a7-123">See also</span></span>

- [<span data-ttu-id="9d5a7-124">ICorProfilerModuleEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d5a7-124">ICorProfilerModuleEnum Interface</span></span>](icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="9d5a7-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9d5a7-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
