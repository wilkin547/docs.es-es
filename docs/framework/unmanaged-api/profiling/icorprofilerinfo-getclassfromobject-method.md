---
title: ICorProfilerInfo::GetClassFromObject (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetClassFromObject
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassFromObject
helpviewer_keywords:
- GetClassFromObject method [.NET Framework profiling]
- ICorProfilerInfo::GetClassFromObject method [.NET Framework profiling]
ms.assetid: b97493fb-713e-49d5-a73e-5688b2ad0700
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9031ae9b4870c182922baaa41883de4cddb469d2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54676684"
---
# <a name="icorprofilerinfogetclassfromobject-method"></a><span data-ttu-id="fd077-102">ICorProfilerInfo::GetClassFromObject (Método)</span><span class="sxs-lookup"><span data-stu-id="fd077-102">ICorProfilerInfo::GetClassFromObject Method</span></span>
<span data-ttu-id="fd077-103">Obtiene el `ClassID` de un objeto, dada su `ObjectID`.</span><span class="sxs-lookup"><span data-stu-id="fd077-103">Gets the `ClassID` of an object, given its `ObjectID`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd077-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd077-104">Syntax</span></span>  
  
```  
HRESULT GetClassFromObject(  
    [in]  ObjectID objectId,  
    [out] ClassID *pClassId);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="fd077-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd077-105">Parameters</span></span>  
 `objectId`  
 <span data-ttu-id="fd077-106">[in] El identificador del objeto que se va a obtener el `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="fd077-106">[in] The ID of the object for which to get the `ClassID`.</span></span>  
  
 `pClassId`  
 <span data-ttu-id="fd077-107">[out] Un puntero a la devuelta `ClassID`.</span><span class="sxs-lookup"><span data-stu-id="fd077-107">[out] A pointer to the returned `ClassID`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fd077-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd077-108">Remarks</span></span>  
 <span data-ttu-id="fd077-109">Un valor null `pClassId` indica que `objectId` tiene un tipo que se está descargando.</span><span class="sxs-lookup"><span data-stu-id="fd077-109">A null `pClassId` indicates that `objectId` has a type that is unloading.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd077-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd077-110">Requirements</span></span>  
 <span data-ttu-id="fd077-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd077-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd077-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="fd077-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="fd077-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fd077-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fd077-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd077-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd077-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd077-115">See also</span></span>
- [<span data-ttu-id="fd077-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fd077-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
