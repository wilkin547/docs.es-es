---
title: ICorProfilerThreadEnum::Skip (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerThreadEnum.Skip
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerThreadEnum::Skip
helpviewer_keywords:
- Skip method, ICorProfilerThreadEnum interface [.NET Framework profiling]
- ICorProfilerThreadEnum::Skip method [.NET Framework profiling]
ms.assetid: acb8b029-4a96-4ed7-ae3c-310204e5ceea
topic_type:
- apiref
ms.openlocfilehash: b08a501f7d55fbb193afd8c297ca7725348dac76
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76860935"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="4679e-102">ICorProfilerThreadEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="4679e-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="4679e-103">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="4679e-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4679e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4679e-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4679e-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="4679e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4679e-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="4679e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4679e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4679e-107">Return Value</span></span>  
 <span data-ttu-id="4679e-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="4679e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="4679e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4679e-109">HRESULT</span></span>|<span data-ttu-id="4679e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4679e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4679e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4679e-111">S_OK</span></span>|<span data-ttu-id="4679e-112">`celt` elementos se omitieron.</span><span class="sxs-lookup"><span data-stu-id="4679e-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="4679e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="4679e-113">S_FALSE</span></span>|<span data-ttu-id="4679e-114">Se omitieron menos de `celt` elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="4679e-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4679e-115">Notas</span><span class="sxs-lookup"><span data-stu-id="4679e-115">Remarks</span></span>  
 <span data-ttu-id="4679e-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="4679e-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4679e-117">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="4679e-117">Requirements</span></span>  
 <span data-ttu-id="4679e-118">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4679e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4679e-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4679e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4679e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4679e-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4679e-121">**.NET Framework versiones:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4679e-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4679e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4679e-122">See also</span></span>

- [<span data-ttu-id="4679e-123">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4679e-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="4679e-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="4679e-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
