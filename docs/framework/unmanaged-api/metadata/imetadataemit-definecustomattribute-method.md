---
title: "IMetaDataEmit::DefineCustomAttribute (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.DefineCustomAttribute
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::DefineCustomAttribute
helpviewer_keywords:
- DefineCustomAttribute method [.NET Framework metadata]
- IMetaDataEmit::DefineCustomAttribute method [.NET Framework metadata]
ms.assetid: 7dd14854-b756-4401-b167-88ca576dc8f0
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1c4c00480571b4160d7442aeafea088fe8d04ba6
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="1754d-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="1754d-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="1754d-103">Crea una definición para un atributo personalizado con la firma de metadatos especificados, que se adjuntará al objeto especificado y obtiene un símbolo (token) para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1754d-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1754d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1754d-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="1754d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1754d-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="1754d-106">[in] El token para el elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="1754d-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="1754d-107">[in] El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1754d-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="1754d-108">[in] Un puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="1754d-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="1754d-109">[in] El recuento de bytes en `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="1754d-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="1754d-110">[out] El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="1754d-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1754d-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1754d-111">Requirements</span></span>  
 <span data-ttu-id="1754d-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1754d-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1754d-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1754d-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1754d-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1754d-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1754d-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1754d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1754d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1754d-116">See Also</span></span>  
 [<span data-ttu-id="1754d-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1754d-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="1754d-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1754d-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
