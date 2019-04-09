---
title: ICorProfilerInfo2::GetArrayObjectInfo (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo2.GetArrayObjectInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5276c69da05cedcd3195a09da12ddc5b2d0fed67
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59201278"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="36c89-102">ICorProfilerInfo2::GetArrayObjectInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="36c89-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="36c89-103">Obtiene información detallada sobre un objeto de matriz.</span><span class="sxs-lookup"><span data-stu-id="36c89-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36c89-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="36c89-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="36c89-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="36c89-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="36c89-106">[in] El identificador de un objeto de matriz válida.</span><span class="sxs-lookup"><span data-stu-id="36c89-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="36c89-107">[in] El rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="36c89-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="36c89-108">[out] Una matriz que contiene enteros, cada uno que representa el tamaño de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="36c89-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="36c89-109">[out] Una matriz que contiene enteros, cada uno que representa la parte inferior se enlaza de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="36c89-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="36c89-110">[out] Un puntero a la dirección del búfer sin formato para la matriz, que se distribuyen según la convención de C++.</span><span class="sxs-lookup"><span data-stu-id="36c89-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="36c89-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="36c89-111">Remarks</span></span>  
 <span data-ttu-id="36c89-112">El `pDimensionSizes` y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentra en el mismo índice de cada matriz son características de la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="36c89-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36c89-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="36c89-113">Requirements</span></span>  
 <span data-ttu-id="36c89-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="36c89-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36c89-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="36c89-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="36c89-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="36c89-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="36c89-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="36c89-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="36c89-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="36c89-118">See also</span></span>

- [<span data-ttu-id="36c89-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36c89-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
- [<span data-ttu-id="36c89-120">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="36c89-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
