---
title: "ICorProfilerInfo2::GetArrayObjectInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetArrayObjectInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetArrayObjectInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetArrayObjectInfo method [.NET Framework profiling]
- GetArrayObjectInfo method [.NET Framework profiling]
ms.assetid: bda75017-739f-4ce5-9000-f3b526e8473c
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b20530081f7c9ad32f4702099abacc78e052ebd9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="f7153-102">ICorProfilerInfo2::GetArrayObjectInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="f7153-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="f7153-103">Obtiene información detallada sobre un objeto de matriz.</span><span class="sxs-lookup"><span data-stu-id="f7153-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f7153-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f7153-104">Syntax</span></span>  
  
```  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f7153-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f7153-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="f7153-106">[in] El identificador de un objeto de matriz válida.</span><span class="sxs-lookup"><span data-stu-id="f7153-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="f7153-107">[in] El rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f7153-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="f7153-108">[out] Una matriz que contiene enteros, cada uno representa el tamaño de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f7153-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="f7153-109">[out] Una matriz que contiene enteros, cada uno que representa la parte inferior se enlaza de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="f7153-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="f7153-110">[out] Un puntero a la dirección del búfer sin formato de la matriz, que se dispone de acuerdo con la convención de C++.</span><span class="sxs-lookup"><span data-stu-id="f7153-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f7153-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f7153-111">Remarks</span></span>  
 <span data-ttu-id="f7153-112">El `pDimensionSizes` y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentran en el mismo índice de cada matriz son características de la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="f7153-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f7153-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f7153-113">Requirements</span></span>  
 <span data-ttu-id="f7153-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f7153-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7153-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="f7153-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="f7153-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f7153-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f7153-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7153-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7153-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="f7153-118">See Also</span></span>  
 [<span data-ttu-id="f7153-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7153-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="f7153-120">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f7153-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
