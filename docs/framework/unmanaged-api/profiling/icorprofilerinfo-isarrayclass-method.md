---
title: "ICorProfilerInfo::IsArrayClass (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a1063aea795d73ebaad0803abb7e555e1bb8b7e4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfoisarrayclass-method"></a><span data-ttu-id="5de00-102">ICorProfilerInfo::IsArrayClass (Método)</span><span class="sxs-lookup"><span data-stu-id="5de00-102">ICorProfilerInfo::IsArrayClass Method</span></span>
<span data-ttu-id="5de00-103">Determina si la clase especificada es una clase de matriz.</span><span class="sxs-lookup"><span data-stu-id="5de00-103">Determines whether the specified class is an array class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5de00-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5de00-104">Syntax</span></span>  
  
```  
HRESULT IsArrayClass(  
    [in]  ClassID        classId,  
    [out] CorElementType *pBaseElemType,  
    [out] ClassID        *pBaseClassId,  
    [out] ULONG          *pcRank);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="5de00-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5de00-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="5de00-106">[in] El identificador de la clase se va a examinar.</span><span class="sxs-lookup"><span data-stu-id="5de00-106">[in] The ID of the class to be examined.</span></span>  
  
 `pBaseElemType`  
 <span data-ttu-id="5de00-107">[out] Un puntero a un valor de la enumeración CorElementType que indica el tipo de los elementos de matriz.</span><span class="sxs-lookup"><span data-stu-id="5de00-107">[out] A pointer to a value of the CorElementType enumeration that indicates the type of the array elements.</span></span>  
  
 `pBaseClassId`  
 <span data-ttu-id="5de00-108">[out] Un puntero al identificador de clase de los elementos de matriz, si está disponible.</span><span class="sxs-lookup"><span data-stu-id="5de00-108">[out] A pointer to the class ID of the array elements, when available.</span></span>  
  
 `pcRank`  
 <span data-ttu-id="5de00-109">[out] Un puntero a un entero que indica el rango (es decir, el número de dimensiones) de la matriz.</span><span class="sxs-lookup"><span data-stu-id="5de00-109">[out] A pointer to an integer that indicates the rank (that is, number of dimensions) of the array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5de00-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5de00-110">Remarks</span></span>  
 <span data-ttu-id="5de00-111">Si la clase especificada es una clase de matriz, el `IsArrayClass` método devuelve un HRESULT de S_OK y valores para cualquier parámetro de salida distinto de null.</span><span class="sxs-lookup"><span data-stu-id="5de00-111">If the specified class is an array class, the `IsArrayClass` method returns an S_OK HRESULT and values for any non-null output parameters.</span></span> <span data-ttu-id="5de00-112">En caso contrario, devuelve S_FALSE.</span><span class="sxs-lookup"><span data-stu-id="5de00-112">Otherwise, it returns S_FALSE.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5de00-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5de00-113">Requirements</span></span>  
 <span data-ttu-id="5de00-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5de00-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5de00-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="5de00-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="5de00-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5de00-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5de00-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5de00-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5de00-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5de00-118">See Also</span></span>  
 [<span data-ttu-id="5de00-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5de00-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
