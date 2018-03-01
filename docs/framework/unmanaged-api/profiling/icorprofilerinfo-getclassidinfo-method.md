---
title: "ICorProfilerInfo::GetClassIDInfo (Método)"
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
- ICorProfilerInfo.GetClassIDInfo
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetClassIDInfo
helpviewer_keywords:
- GetClassIDInfo method [.NET Framework profiling]
- ICorProfilerInfo::GetClassIDInfo method [.NET Framework profiling]
ms.assetid: 9e93b99e-5aca-415c-8e37-7f33753b612d
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a9da3ee3823f5d2062ea7a99c76ccf953448fb87
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="icorprofilerinfogetclassidinfo-method"></a><span data-ttu-id="128ff-102">ICorProfilerInfo::GetClassIDInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="128ff-102">ICorProfilerInfo::GetClassIDInfo Method</span></span>
<span data-ttu-id="128ff-103">Obtiene el módulo primario y el token de metadatos para la clase especificada.</span><span class="sxs-lookup"><span data-stu-id="128ff-103">Gets the parent module and the metadata token for the specified class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="128ff-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="128ff-104">Syntax</span></span>  
  
```  
HRESULT GetClassIDInfo(  
    [in]  ClassID   classId,  
    [out] ModuleID  *pModuleId,  
    [out] mdTypeDef *pTypeDefToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="128ff-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="128ff-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="128ff-106">[in] El identificador de la clase para la que se va a obtener la información.</span><span class="sxs-lookup"><span data-stu-id="128ff-106">[in] The ID of the class for which to get the information.</span></span>  
  
 `pModuleId`  
 <span data-ttu-id="128ff-107">[out] Un puntero al identificador del módulo primario de la clase.</span><span class="sxs-lookup"><span data-stu-id="128ff-107">[out] A pointer to the ID of the parent module of the class.</span></span>  
  
 `pTypeDefToken`  
 <span data-ttu-id="128ff-108">[out] Un puntero al token de metadatos para la clase.</span><span class="sxs-lookup"><span data-stu-id="128ff-108">[out] A pointer to the metadata token for the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="128ff-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="128ff-109">Remarks</span></span>  
 <span data-ttu-id="128ff-110">El código del generador de perfiles puede llamar a [ICorProfilerInfo:: GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) para obtener una interfaz de metadatos para un módulo determinado.</span><span class="sxs-lookup"><span data-stu-id="128ff-110">The profiler code can call [ICorProfilerInfo::GetModuleMetaData](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getmodulemetadata-method.md) to obtain a metadata interface for a given module.</span></span> <span data-ttu-id="128ff-111">Después, el token de metadatos que se devuelve a la ubicación a la que `pTypeDefToken` hace referencia puede usarse para acceder a los metadatos de la clase.</span><span class="sxs-lookup"><span data-stu-id="128ff-111">The metadata token that is returned to the location referenced by `pTypeDefToken` can then be used to access the metadata for the class.</span></span>  
  
 <span data-ttu-id="128ff-112">Para obtener más información sobre tipos genéricos, use [ICorProfilerInfo2:: Getclassidinfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span><span class="sxs-lookup"><span data-stu-id="128ff-112">To get more information for generic types, use [ICorProfilerInfo2::GetClassIDInfo2](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-getclassidinfo2-method.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="128ff-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="128ff-113">Requirements</span></span>  
 <span data-ttu-id="128ff-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="128ff-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="128ff-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="128ff-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="128ff-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="128ff-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="128ff-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="128ff-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="128ff-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="128ff-118">See Also</span></span>  
 [<span data-ttu-id="128ff-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="128ff-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
