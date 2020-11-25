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
ms.openlocfilehash: 8e03eefc3758347389be4af6d53921480ee40263
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95724083"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="226ed-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="226ed-102">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>

<span data-ttu-id="226ed-103">Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="226ed-103">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="226ed-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="226ed-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="226ed-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="226ed-105">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="226ed-106">de IDENTIFICADOR de la función para la que se va a obtener el token de metadatos y la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="226ed-106">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="226ed-107">de IDENTIFICADOR de referencia de la interfaz de metadatos de la que se va a obtener la instancia.</span><span class="sxs-lookup"><span data-stu-id="226ed-107">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="226ed-108">enuncia Puntero a la dirección de la instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="226ed-108">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="226ed-109">enuncia Puntero al símbolo (token) de metadatos para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="226ed-109">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="226ed-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="226ed-110">Requirements</span></span>  

 <span data-ttu-id="226ed-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="226ed-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="226ed-112">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="226ed-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="226ed-113">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="226ed-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="226ed-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="226ed-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="226ed-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="226ed-115">See also</span></span>

- [<span data-ttu-id="226ed-116">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="226ed-116">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
