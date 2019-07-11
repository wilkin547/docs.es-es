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
ms.openlocfilehash: b608b8818890bdb27a956a90c7987cf7c421304d
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67772272"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="8f6ef-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="8f6ef-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>
<span data-ttu-id="8f6ef-103">Obtiene el token de metadatos y una instancia de la interfaz de metadatos que puede utilizarse con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="8f6ef-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8f6ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8f6ef-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="8f6ef-106">[in] El identificador de la función que se va a obtener el token de metadatos y la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="8f6ef-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="8f6ef-107">[in] El identificador de referencia de la interfaz de metadatos para obtener la instancia de.</span><span class="sxs-lookup"><span data-stu-id="8f6ef-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="8f6ef-108">[out] Un puntero a la dirección de la instancia de la interfaz de metadatos que puede utilizarse con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="8f6ef-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="8f6ef-109">[out] Un puntero al token de metadatos para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="8f6ef-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6ef-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f6ef-110">Requirements</span></span>  
 <span data-ttu-id="8f6ef-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f6ef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6ef-112">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8f6ef-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8f6ef-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f6ef-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f6ef-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6ef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6ef-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f6ef-115">See also</span></span>

- [<span data-ttu-id="8f6ef-116">ICorProfilerInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f6ef-116">ICorProfilerInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)
