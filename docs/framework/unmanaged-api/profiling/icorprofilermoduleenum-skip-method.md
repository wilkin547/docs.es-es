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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 397e8afcc176bcd9733e83dc6425fe49f385931e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078207"
---
# <a name="icorprofilermoduleenumskip-method"></a><span data-ttu-id="52ed0-102">ICorProfilerModuleEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="52ed0-102">ICorProfilerModuleEnum::Skip Method</span></span>
<span data-ttu-id="52ed0-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="52ed0-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="52ed0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="52ed0-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="52ed0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="52ed0-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="52ed0-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="52ed0-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="52ed0-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="52ed0-107">Return Value</span></span>  
 <span data-ttu-id="52ed0-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="52ed0-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="52ed0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="52ed0-109">HRESULT</span></span>|<span data-ttu-id="52ed0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="52ed0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="52ed0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="52ed0-111">S_OK</span></span>|<span data-ttu-id="52ed0-112">`celt` se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="52ed0-112">`celt` elements were skipped.</span></span>|  
|<span data-ttu-id="52ed0-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="52ed0-113">S_FALSE</span></span>|<span data-ttu-id="52ed0-114">Menos de `celt` se omitieron los elementos, lo que indica que no hay ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="52ed0-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="52ed0-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="52ed0-115">Remarks</span></span>  
 <span data-ttu-id="52ed0-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="52ed0-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="52ed0-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="52ed0-117">Requirements</span></span>  
 <span data-ttu-id="52ed0-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="52ed0-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="52ed0-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="52ed0-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="52ed0-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="52ed0-120">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="52ed0-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="52ed0-121">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="52ed0-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="52ed0-122">See also</span></span>

- [<span data-ttu-id="52ed0-123">ICorProfilerModuleEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="52ed0-123">ICorProfilerModuleEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilermoduleenum-interface.md)
- [<span data-ttu-id="52ed0-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="52ed0-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
