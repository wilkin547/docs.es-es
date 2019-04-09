---
title: IMetaDataEmit::DefineCustomAttribute (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineCustomAttribute
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 52190583338f1c1ee9183a98d5f4a6cd7236342d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075690"
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="872de-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="872de-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="872de-103">Crea una definición para un atributo personalizado con la firma de metadatos especificado, que se adjuntará al objeto especificado y obtiene un token para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="872de-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="872de-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="872de-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="872de-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="872de-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="872de-106">[in] El token para el elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="872de-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="872de-107">[in] El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="872de-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="872de-108">[in] Un puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="872de-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="872de-109">[in] El recuento de bytes en `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="872de-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="872de-110">[out] El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="872de-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="872de-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="872de-111">Requirements</span></span>  
 <span data-ttu-id="872de-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="872de-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="872de-113">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="872de-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="872de-114">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="872de-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="872de-115">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="872de-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="872de-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="872de-116">See also</span></span>

- [<span data-ttu-id="872de-117">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="872de-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="872de-118">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="872de-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
