---
description: 'Más información acerca de: ICorProfilerInfo2:: Getarrayobjectinfo ((método)'
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
ms.openlocfilehash: 1427ad696f73d90a2a07698c71456571fb14ee70
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760542"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="47ad1-103">ICorProfilerInfo2::GetArrayObjectInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="47ad1-103">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>

<span data-ttu-id="47ad1-104">Obtiene información detallada sobre un objeto de matriz.</span><span class="sxs-lookup"><span data-stu-id="47ad1-104">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47ad1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47ad1-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47ad1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47ad1-106">Parameters</span></span>  

 `objectId`  
 <span data-ttu-id="47ad1-107">de IDENTIFICADOR de un objeto de matriz válido.</span><span class="sxs-lookup"><span data-stu-id="47ad1-107">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="47ad1-108">de Rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="47ad1-108">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="47ad1-109">enuncia Una matriz que contiene enteros, cada uno de los cuales representa el tamaño de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="47ad1-109">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="47ad1-110">enuncia Una matriz que contiene enteros, cada uno de los cuales representa el límite inferior de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="47ad1-110">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="47ad1-111">enuncia Puntero a la dirección del búfer sin formato de la matriz, que se distribuye según la Convención de C++.</span><span class="sxs-lookup"><span data-stu-id="47ad1-111">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47ad1-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="47ad1-112">Remarks</span></span>  

 <span data-ttu-id="47ad1-113">`pDimensionSizes`Y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentran en el mismo índice de cada matriz son características de la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="47ad1-113">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47ad1-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47ad1-114">Requirements</span></span>  

 <span data-ttu-id="47ad1-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47ad1-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47ad1-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="47ad1-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="47ad1-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47ad1-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47ad1-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47ad1-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47ad1-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="47ad1-119">See also</span></span>

- [<span data-ttu-id="47ad1-120">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47ad1-120">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="47ad1-121">ICorProfilerInfo2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47ad1-121">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
