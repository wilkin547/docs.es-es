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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f0e334c75afee60591db2b4e1f45cf0ec753ee2e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59141657"
---
# <a name="icorprofilerfunctionenumskip-method"></a><span data-ttu-id="0555e-102">ICorProfilerFunctionEnum::Skip (Método)</span><span class="sxs-lookup"><span data-stu-id="0555e-102">ICorProfilerFunctionEnum::Skip Method</span></span>
<span data-ttu-id="0555e-103">Desplaza el cursor del enumerador desde su posición actual de manera que se omita el número especificado de elementos.</span><span class="sxs-lookup"><span data-stu-id="0555e-103">Advances the enumerator's cursor from its current position so that the specified number of elements are skipped.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0555e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0555e-104">Syntax</span></span>  
  
```  
HRESULT Skip([in] ULONG celt);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0555e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0555e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="0555e-106">[in] El número de elementos que se van a omitir.</span><span class="sxs-lookup"><span data-stu-id="0555e-106">[in] The number of elements to be skipped.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0555e-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0555e-107">Return Value</span></span>  
 <span data-ttu-id="0555e-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="0555e-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0555e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0555e-109">HRESULT</span></span>|<span data-ttu-id="0555e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0555e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0555e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0555e-111">S_OK</span></span>|`celt` <span data-ttu-id="0555e-112">se omitieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="0555e-112">elements were skipped.</span></span>|  
|<span data-ttu-id="0555e-113">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="0555e-113">S_FALSE</span></span>|<span data-ttu-id="0555e-114">Menos de `celt` se omitieron los elementos, lo que indica que no hay ningún elemento más.</span><span class="sxs-lookup"><span data-stu-id="0555e-114">Fewer than `celt` elements were skipped, which indicates that there are no more elements.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0555e-115">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0555e-115">Remarks</span></span>  
 <span data-ttu-id="0555e-116">La nueva posición del cursor de este enumerador es (posición actual) + `celt`.</span><span class="sxs-lookup"><span data-stu-id="0555e-116">The new position of this enumerator's cursor is (current position) + `celt`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0555e-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0555e-117">Requirements</span></span>  
 <span data-ttu-id="0555e-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0555e-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0555e-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="0555e-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="0555e-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0555e-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="0555e-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0555e-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0555e-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="0555e-122">See also</span></span>

- [<span data-ttu-id="0555e-123">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0555e-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="0555e-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="0555e-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
