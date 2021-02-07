---
description: 'Más información acerca de: ICorProfilerThreadEnum:: Skip (método)'
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
ms.openlocfilehash: 1da191980364868ed4237fccaf7495d5417705cc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736900"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="9fcdd-103">ICorProfilerThreadEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="9fcdd-103">ICorProfilerThreadEnum::Skip Method</span></span>

<span data-ttu-id="9fcdd-104">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="9fcdd-104">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fcdd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9fcdd-105">Syntax</span></span>  
  
```cpp  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9fcdd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9fcdd-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="9fcdd-107">de Número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="9fcdd-107">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9fcdd-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9fcdd-108">Return Value</span></span>  

 <span data-ttu-id="9fcdd-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="9fcdd-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="9fcdd-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9fcdd-110">HRESULT</span></span>|<span data-ttu-id="9fcdd-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="9fcdd-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9fcdd-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="9fcdd-112">S_OK</span></span>|<span data-ttu-id="9fcdd-113">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="9fcdd-113">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="9fcdd-114">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="9fcdd-114">S_FALSE</span></span>|<span data-ttu-id="9fcdd-115">`celt`Se omitieron menos de elementos, lo que indica que no hay más elementos.</span><span class="sxs-lookup"><span data-stu-id="9fcdd-115">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fcdd-116">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9fcdd-116">Remarks</span></span>  

 <span data-ttu-id="9fcdd-117">La nueva posición del cursor de este enumerador es (posición actual) + `celt` .</span><span class="sxs-lookup"><span data-stu-id="9fcdd-117">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9fcdd-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9fcdd-118">Requirements</span></span>  

 <span data-ttu-id="9fcdd-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9fcdd-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9fcdd-120">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9fcdd-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9fcdd-121">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9fcdd-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9fcdd-122">**.NET Framework versiones:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9fcdd-122">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fcdd-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="9fcdd-123">See also</span></span>

- [<span data-ttu-id="9fcdd-124">ICorProfilerThreadEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9fcdd-124">ICorProfilerThreadEnum Interface</span></span>](icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="9fcdd-125">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="9fcdd-125">Profiling Interfaces</span></span>](profiling-interfaces.md)
