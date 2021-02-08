---
description: 'Más información acerca de: ICorProfilerInfo:: Gettokenandmetadatafromfunction ((método)'
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
ms.openlocfilehash: 0cea6564df15c7a7f4c46097714cc0956002599b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99783851"
---
# <a name="icorprofilerinfogettokenandmetadatafromfunction-method"></a><span data-ttu-id="aea1e-103">ICorProfilerInfo::GetTokenAndMetadataFromFunction (Método)</span><span class="sxs-lookup"><span data-stu-id="aea1e-103">ICorProfilerInfo::GetTokenAndMetadataFromFunction Method</span></span>

<span data-ttu-id="aea1e-104">Obtiene el token de metadatos y una instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="aea1e-104">Gets the metadata token and a metadata interface instance that can be used against the token for the specified function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aea1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aea1e-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenAndMetaDataFromFunction(  
    [in]  FunctionID functionId,  
    [in]  REFIID     riid,  
    [out] IUnknown   **ppImport,  
    [out] mdToken    *pToken);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aea1e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aea1e-106">Parameters</span></span>  

 `functionId`  
 <span data-ttu-id="aea1e-107">de IDENTIFICADOR de la función para la que se va a obtener el token de metadatos y la interfaz de metadatos.</span><span class="sxs-lookup"><span data-stu-id="aea1e-107">[in] The ID of the function for which to get the metadata token and metadata interface.</span></span>  
  
 `riid`  
 <span data-ttu-id="aea1e-108">de IDENTIFICADOR de referencia de la interfaz de metadatos de la que se va a obtener la instancia.</span><span class="sxs-lookup"><span data-stu-id="aea1e-108">[in] The reference ID of the metadata interface to get the instance of.</span></span>  
  
 `ppImport`  
 <span data-ttu-id="aea1e-109">enuncia Puntero a la dirección de la instancia de la interfaz de metadatos que se puede usar con el token para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="aea1e-109">[out] A pointer to the address of the metadata interface instance that can be used against the token for the specified function.</span></span>  
  
 `pToken`  
 <span data-ttu-id="aea1e-110">enuncia Puntero al símbolo (token) de metadatos para la función especificada.</span><span class="sxs-lookup"><span data-stu-id="aea1e-110">[out] A pointer to the metadata token for the specified function.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aea1e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aea1e-111">Requirements</span></span>  

 <span data-ttu-id="aea1e-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aea1e-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aea1e-113">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aea1e-113">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aea1e-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aea1e-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aea1e-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aea1e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aea1e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="aea1e-116">See also</span></span>

- [<span data-ttu-id="aea1e-117">ICorProfilerInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aea1e-117">ICorProfilerInfo Interface</span></span>](icorprofilerinfo-interface.md)
