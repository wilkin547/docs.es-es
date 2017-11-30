---
title: "ICorProfilerInfo::GetClassFromObject (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo.GetClassFromObject
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 706118a197677ec97672cca36f5bcf6421a1c328
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="097ad-102">ICorProfilerInfo::GetClassFromObject (Método)</span><span class="sxs-lookup"><span data-stu-id="097ad-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="097ad-103">Obtiene el `ClassID` de un objeto, dados su `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="097ad-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097ad-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="097ad-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="097ad-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="097ad-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="097ad-106">[in] El identificador del objeto para el que se va a obtener el `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="097ad-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="097ad-107">[out] Un puntero para el valor devuelto `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="097ad-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="097ad-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="097ad-108">Remarks</span></span>  
 <span data-ttu-id="097ad-109">Un valor null `pClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="097ad-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097ad-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="097ad-110">Requirements</span></span>  
 <span data-ttu-id="097ad-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="097ad-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097ad-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="097ad-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="097ad-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="097ad-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="097ad-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097ad-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097ad-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="097ad-115">See Also</span></span>  
 [<span data-ttu-id="097ad-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="097ad-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
