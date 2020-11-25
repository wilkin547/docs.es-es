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
ms.openlocfilehash: 12b7b53c408388c21d7508f6591ead5ccf55936b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721184"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="ef3cd-102">ICorProfilerThreadEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="ef3cd-102">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="ef3cd-103">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="ef3cd-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef3cd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ef3cd-104">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef3cd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ef3cd-105">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="ef3cd-106">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="ef3cd-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ef3cd-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ef3cd-107">Return Value</span></span>  

 <span data-ttu-id="ef3cd-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="ef3cd-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="ef3cd-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ef3cd-109">HRESULT</span></span>|<span data-ttu-id="ef3cd-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef3cd-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ef3cd-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="ef3cd-111">S_OK</span></span>|<span data-ttu-id="ef3cd-112">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="ef3cd-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="ef3cd-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="ef3cd-113">S_FALSE</span></span>|<span data-ttu-id="ef3cd-114">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="ef3cd-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef3cd-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef3cd-115">Remarks</span></span>  

 <span data-ttu-id="ef3cd-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="ef3cd-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef3cd-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef3cd-117">Requirements</span></span>  

 <span data-ttu-id="ef3cd-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef3cd-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef3cd-119">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="ef3cd-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="ef3cd-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ef3cd-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ef3cd-121">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef3cd-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef3cd-122">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ef3cd-122">See also</span></span>

- [<span data-ttu-id="ef3cd-123">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef3cd-123">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="ef3cd-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="ef3cd-124">Profiling Interfaces</span></span>](profiling-interfaces.md)
