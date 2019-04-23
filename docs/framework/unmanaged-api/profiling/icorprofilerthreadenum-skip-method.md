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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cce96e8c6d046beba9e45c7121bf68444fd51c95
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59173347"
---
# <a name="icorprofilerthreadenumskip-method"></a><span data-ttu-id="79048-102">ICorProfilerThreadEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="79048-102">ICorProfilerThreadEnum::Skip Method</span></span>
<span data-ttu-id="79048-103">Desplaza el cursor del enumerador desde su posición actual para omitir el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="79048-103">Advances the enumerator's cursor from its current position to skip the specified number of elements.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79048-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79048-104">Syntax</span></span>  
  
```  
HRESULT Skip (    [in] ULONG celt  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79048-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79048-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="79048-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="79048-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79048-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="79048-107">Return Value</span></span>  
 <span data-ttu-id="79048-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="79048-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="79048-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79048-109">HRESULT</span></span>|<span data-ttu-id="79048-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="79048-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="79048-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="79048-111">S_OK</span></span>|<span data-ttu-id="79048-112">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="79048-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="79048-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="79048-113">S_FALSE</span></span>|<span data-ttu-id="79048-114">Menos de `celt` se omitieron los elementos, lo que indica que no hay ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="79048-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79048-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="79048-115">Remarks</span></span>  
 <span data-ttu-id="79048-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="79048-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79048-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79048-117">Requirements</span></span>  
 <span data-ttu-id="79048-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79048-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79048-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="79048-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="79048-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="79048-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="79048-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79048-121">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79048-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="79048-122">See also</span></span>

- [<span data-ttu-id="79048-123">ICorProfilerThreadEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79048-123">ICorProfilerThreadEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerthreadenum-interface.md)
- [<span data-ttu-id="79048-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="79048-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
