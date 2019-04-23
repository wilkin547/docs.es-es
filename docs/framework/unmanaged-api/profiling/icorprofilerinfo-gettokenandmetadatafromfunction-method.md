---
title: ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)
ms.date: 03/30/2017
api_name:
- ICorProfilerInfo.GetTokenAndMetadataFromFunction
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction
helpviewer_keywords:
- ICorProfilerInfo::GetTokenAndMetadataFromFunction method [.NET Framework profiling]
- GetTokenAndMetadataFromFunction method [.NET Framework profiling]
ms.assetid: e525aa16-c923-4b16-833b-36f1f0dd70fc
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 7e7f2e8247d3ba822cc09a98f985926e6b5400c6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59206894"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="9da6f-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="9da6f-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="9da6f-103">Obtiene el token de metadatos y una instancia de la interfaz de metadatos que puede utilizarse con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="9da6f-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9da6f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9da6f-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9da6f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9da6f-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="9da6f-106">[in] El identificador de la función que se va a obtener el token de metadatos y la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="9da6f-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="9da6f-107">[in] El identificador de referencia de la interfaz de metadatos para obtener la instancia de.</span><span class="sxs-lookup"><span data-stu-id="9da6f-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="9da6f-108">[out] Un puntero a la dirección de la instancia de la interfaz de metadatos que puede utilizarse con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="9da6f-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="9da6f-109">[out] Un puntero al token de metadatos para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="9da6f-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9da6f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9da6f-110">Requirements</span></span>  
 <span data-ttu-id="9da6f-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9da6f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9da6f-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="9da6f-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="9da6f-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9da6f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9da6f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9da6f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9da6f-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="9da6f-115">See also</span></span>

- [<span data-ttu-id="9da6f-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9da6f-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
