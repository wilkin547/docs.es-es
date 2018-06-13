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
ms.openlocfilehash: 9bcf8919037d5b79f3819fffec02708886064b40
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33453208"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="63d0a-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="63d0a-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="63d0a-103">Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="63d0a-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d0a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="63d0a-104">Syntax</span></span>  
  
```  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="63d0a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="63d0a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="63d0a-106">[in] El identificador de la función para la que se va a obtener el token de metadatos y la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="63d0a-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="63d0a-107">[in] El identificador de referencia de la interfaz de metadatos para obtener la instancia de.</span><span class="sxs-lookup"><span data-stu-id="63d0a-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="63d0a-108">[out] Un puntero a la dirección de la instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="63d0a-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="63d0a-109">[out] Un puntero al token de metadatos para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="63d0a-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63d0a-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="63d0a-110">Requirements</span></span>  
 <span data-ttu-id="63d0a-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="63d0a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d0a-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="63d0a-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="63d0a-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63d0a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63d0a-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63d0a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63d0a-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="63d0a-115">See Also</span></span>  
 [<span data-ttu-id="63d0a-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="63d0a-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
