---
title: "ICorProfilerInfo2::GetStaticFieldInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetStaticFieldInfo
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetStaticFieldInfo
helpviewer_keywords:
- ICorProfilerInfo2::GetStaticFieldInfo method [.NET Framework profiling]
- GetStaticFieldInfo method [.NET Framework profiling]
ms.assetid: fc663e76-e23f-49a8-bdd5-52cdf1a3b2b3
topic_type: apiref
caps.latest.revision: "14"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7cf16a0fae7f3e2afd095534b2e7f7957d44e3e7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getstaticfieldinfo-method"></a><span data-ttu-id="41a02-102">ICorProfilerInfo2::GetStaticFieldInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="41a02-102">ICorProfilerInfo2::GetStaticFieldInfo Method</span></span>
<span data-ttu-id="41a02-103">Obtiene un valor que indica el tipo de estática que se aplica al campo especificado.</span><span class="sxs-lookup"><span data-stu-id="41a02-103">Gets a value that indicates the kind of static that applies to the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="41a02-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41a02-104">Syntax</span></span>  
  
```  
HRESULT GetStaticFieldInfo (  
    [in] ClassID               classId,  
    [in] mdFieldDef            fieldToken,  
    [out] COR_PRF_STATIC_TYPE  *pFieldInfo);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="41a02-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41a02-105">Parameters</span></span>  
 `classId`  
 <span data-ttu-id="41a02-106">[in] El identificador de la clase en la que se define el campo estático.</span><span class="sxs-lookup"><span data-stu-id="41a02-106">[in] The ID of the class in which the static field is defined.</span></span>  
  
 `fieldToken`  
 <span data-ttu-id="41a02-107">[in] El token de metadatos para el campo estático.</span><span class="sxs-lookup"><span data-stu-id="41a02-107">[in] The metadata token for the static field.</span></span>  
  
 `pFieldInfo`  
 <span data-ttu-id="41a02-108">[out] Un puntero a un valor de la [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeración que indica si el campo especificado es estático y, si es así, el tipo de estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="41a02-108">[out] A pointer to a value of the [COR_PRF_STATIC_TYPE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-static-type-enumeration.md) enumeration that indicates whether the specified field is static, and if so, the kind of static that applies to the field.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="41a02-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="41a02-109">Remarks</span></span>  
 <span data-ttu-id="41a02-110">Esta información puede utilizarse para determinar a qué función llamar para obtener la dirección del campo estático.</span><span class="sxs-lookup"><span data-stu-id="41a02-110">This information can be used to determine which function to call to get the address of the static field.</span></span>  
  
 <span data-ttu-id="41a02-111">El código del generador de perfiles debería comprobar los metadatos de un campo estático para asegurarse de que realmente tiene una dirección.</span><span class="sxs-lookup"><span data-stu-id="41a02-111">The profiler code should still check the metadata for a static field to ensure that it actually has an address.</span></span> <span data-ttu-id="41a02-112">Los literales estáticos (es decir, constantes) sólo existen en los metadatos y no tiene una dirección.</span><span class="sxs-lookup"><span data-stu-id="41a02-112">Static literals (that is, constants) exist only in the metadata and do not have an address.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="41a02-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41a02-113">Requirements</span></span>  
 <span data-ttu-id="41a02-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41a02-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="41a02-115">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="41a02-115">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="41a02-116">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="41a02-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="41a02-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41a02-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="41a02-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="41a02-118">See Also</span></span>  
 [<span data-ttu-id="41a02-119">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41a02-119">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [<span data-ttu-id="41a02-120">ICorProfilerInfo2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="41a02-120">ICorProfilerInfo2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)
