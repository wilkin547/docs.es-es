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
ms.openlocfilehash: 839cd574e5352b74b47cd6242d5706bc6405d439
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76862924"
---
# <a name="icorprofilerinfo2getarrayobjectinfo-method"></a><span data-ttu-id="58890-102">ICorProfilerInfo2::GetArrayObjectInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="58890-102">ICorProfilerInfo2::GetArrayObjectInfo Method</span></span>
<span data-ttu-id="58890-103">Obtiene información detallada sobre un objeto de matriz.</span><span class="sxs-lookup"><span data-stu-id="58890-103">Gets detailed information about an array object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="58890-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58890-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayObjectInfo(  
    [in] ObjectID objectId,  
    [in] ULONG32 cDimensions,  
    [out, size_is(cDimensions), length_is(cDimensions)] ULONG32 pDimensionSizes[],  
    [out, size_is(cDimensions), length_is(cDimensions)] int pDimensionLowerBounds[],  
    [out] BYTE **ppData);  
```  
  
## <a name="parameters"></a><span data-ttu-id="58890-105">Parameters</span><span class="sxs-lookup"><span data-stu-id="58890-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="58890-106">de IDENTIFICADOR de un objeto de matriz válido.</span><span class="sxs-lookup"><span data-stu-id="58890-106">[in] The ID of a valid array object.</span></span>  
  
 `cDimensions`  
 <span data-ttu-id="58890-107">de Rango (número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="58890-107">[in] The rank (number of dimensions) of the array.</span></span>  
  
 `pDimensionSizes`  
 <span data-ttu-id="58890-108">enuncia Una matriz que contiene enteros, cada uno de los cuales representa el tamaño de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="58890-108">[out] An array that contains integers, each representing the size of a dimension of the array.</span></span>  
  
 `pDimensionLowerBounds`  
 <span data-ttu-id="58890-109">enuncia Una matriz que contiene enteros, cada uno de los cuales representa el límite inferior de una dimensión de la matriz.</span><span class="sxs-lookup"><span data-stu-id="58890-109">[out] An array that contains integers, each representing the lower bound of a dimension of the array.</span></span>  
  
 `ppData`  
 <span data-ttu-id="58890-110">enuncia Puntero a la dirección del búfer sin formato de la matriz, que se distribuye según la C++ Convención.</span><span class="sxs-lookup"><span data-stu-id="58890-110">[out] A pointer to the address of the raw buffer for the array, which is laid out according to the C++ convention.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="58890-111">Notas</span><span class="sxs-lookup"><span data-stu-id="58890-111">Remarks</span></span>  
 <span data-ttu-id="58890-112">Los `pDimensionSizes` y `pDimensionLowerBounds` son matrices paralelas, por lo que los elementos que se encuentran en el mismo índice de cada matriz son características de la misma entidad.</span><span class="sxs-lookup"><span data-stu-id="58890-112">The `pDimensionSizes` and `pDimensionLowerBounds` are parallel arrays, so the elements located at the same index in each array are characteristics of the same entity.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="58890-113">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="58890-113">Requirements</span></span>  
 <span data-ttu-id="58890-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58890-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58890-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="58890-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="58890-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="58890-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="58890-117">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="58890-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58890-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="58890-118">See also</span></span>

- [<span data-ttu-id="58890-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58890-119">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
- [<span data-ttu-id="58890-120">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="58890-120">ICorProfilerInfo2 Interface</span></span>](icorprofilerinfo2-interface.md)
