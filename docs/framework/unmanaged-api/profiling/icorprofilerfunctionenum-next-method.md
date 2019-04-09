---
title: ICorProfilerFunctionEnum::Next (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerFunctionEnum.Next Method
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerFunctionEnum::Next
helpviewer_keywords:
- ICorProfilerFunctionEnum::Next method [.NET Framework profiling]
- Next method, ICorProfilerFunctionEnum interface [.NET Framework profiling]
ms.assetid: 5ed4aa83-ce56-4b9f-9237-5da7587787fe
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 62e70a2fe421651aac9a4921ca885c53c864c4f7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101808"
---
# <a name="icorprofilerfunctionenumnext-method"></a><span data-ttu-id="31a18-102">ICorProfilerFunctionEnum::Next (Método)</span><span class="sxs-lookup"><span data-stu-id="31a18-102">ICorProfilerFunctionEnum::Next Method</span></span>
<span data-ttu-id="31a18-103">Obtiene el número especificado de funciones contiguas de una colección secuencial de funciones, comenzando en la posición actual del enumerador en la secuencia.</span><span class="sxs-lookup"><span data-stu-id="31a18-103">Gets the specified number of contiguous functions from a sequential collection of functions, starting at the enumerator's current position in the sequence.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31a18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31a18-104">Syntax</span></span>  
  
```  
HRESULT Next([in]  ULONG      celt,  
             [out, size_is(celt), length_is(*pceltFetched)]  
                    COR_PRF_FUNCTION ids[],  
             [out] ULONG *   pceltFetched);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31a18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31a18-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="31a18-106">[in] Número de funciones para recuperar.</span><span class="sxs-lookup"><span data-stu-id="31a18-106">[in] The number of functions to retrieve.</span></span>  
  
 `ids`  
 <span data-ttu-id="31a18-107">[out] Matriz de valores `COR_PRF_FUNCTION`, cada uno de los cuales representa una función recuperada.</span><span class="sxs-lookup"><span data-stu-id="31a18-107">[out] An array of `COR_PRF_FUNCTION` values, each of which represents a retrieved function.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="31a18-108">[out] Puntero al número de funciones realmente devueltos en la matriz `ids`.</span><span class="sxs-lookup"><span data-stu-id="31a18-108">[out] A pointer to the number of functions actually returned in the `ids` array.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="31a18-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="31a18-109">Return Value</span></span>  
 <span data-ttu-id="31a18-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="31a18-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="31a18-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="31a18-111">HRESULT</span></span>|<span data-ttu-id="31a18-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="31a18-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="31a18-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="31a18-113">S_OK</span></span>|`celt` <span data-ttu-id="31a18-114">se devolvieron los elementos.</span><span class="sxs-lookup"><span data-stu-id="31a18-114">elements were returned.</span></span>|  
|<span data-ttu-id="31a18-115">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="31a18-115">S_FALSE</span></span>|<span data-ttu-id="31a18-116">Se devolvieron menos de `celt` elementos, lo que indica que la enumeración está completa.</span><span class="sxs-lookup"><span data-stu-id="31a18-116">Fewer than `celt` elements were returned, which indicates that the enumeration is complete.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="31a18-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31a18-117">Requirements</span></span>  
 <span data-ttu-id="31a18-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31a18-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31a18-119">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="31a18-119">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="31a18-120">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="31a18-120">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="31a18-121">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="31a18-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="31a18-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="31a18-122">See also</span></span>

- [<span data-ttu-id="31a18-123">ICorProfilerFunctionEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="31a18-123">ICorProfilerFunctionEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerfunctionenum-interface.md)
- [<span data-ttu-id="31a18-124">Interfaces para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="31a18-124">Profiling Interfaces</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)
