---
title: ICorProfilerInfo::IsArrayClass (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.IsArrayClass
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::IsArrayClass
helpviewer_keywords:
- IsArrayClass method [.NET Framework profiling]
- ICorProfilerInfo::IsArrayClass method [.NET Framework profiling]
ms.assetid: 7f230961-23a6-4d56-ad2d-7a876d65705f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 350221ae205636cef82581f3fe11367006dd8b2b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59072177"
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="e0d97-102">ICorProfilerInfo::IsArrayClass (Método)</span><span class="sxs-lookup"><span data-stu-id="e0d97-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="e0d97-103">Determina si la clase especificada es una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="e0d97-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0d97-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e0d97-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0d97-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e0d97-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="e0d97-106">[in] El identificador de la clase se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="e0d97-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="e0d97-107">[out] Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="e0d97-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="e0d97-108">[out] Un puntero al identificador de clase de los elementos de matriz, cuando esté disponible.</span><span class="sxs-lookup"><span data-stu-id="e0d97-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="e0d97-109">[out] Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="e0d97-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e0d97-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e0d97-110">Remarks</span></span>  
 <span data-ttu-id="e0d97-111">Si la clase especificada es una clase de matriz, el `IsArrayClass` método devuelve S_OK HRESULT y valores para cualquier parámetro de salida distinto de null.</span><span class="sxs-lookup"><span data-stu-id="e0d97-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="e0d97-112">En caso contrario, devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="e0d97-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0d97-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e0d97-113">Requirements</span></span>  
 <span data-ttu-id="e0d97-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e0d97-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e0d97-115">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e0d97-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e0d97-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e0d97-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e0d97-117">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e0d97-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e0d97-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0d97-118">See also</span></span>

- [<span data-ttu-id="e0d97-119">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e0d97-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
