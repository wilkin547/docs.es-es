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
ms.workload: dotnet
ms.openlocfilehash: 053601376f8b75e5469a3ef8a3d890a6c6620e28
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitdefinecustomattribute-method"></a><span data-ttu-id="f306e-102">IMetaDataEmit::DefineCustomAttribute (Método)</span><span class="sxs-lookup"><span data-stu-id="f306e-102">IMetaDataEmit::DefineCustomAttribute Method</span></span>
<span data-ttu-id="f306e-103">Crea una definición para un atributo personalizado con la firma de metadatos especificados, que se adjuntará al objeto especificado y obtiene un símbolo (token) para esa definición de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f306e-103">Creates a definition for a custom attribute with the specified metadata signature, to be attached to the specified object, and gets a token to that custom attribute definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f306e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f306e-104">Syntax</span></span>  
  
```  
HRESULT DefineCustomAttribute (   
    [in]  mdToken     tkObj,   
    [in]  mdToken     tkType,   
    [in]  void const  *pCustomAttribute,   
    [in]  ULONG       cbCustomAttribute,   
    [out] mdCustomAttribute *pcv   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f306e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f306e-105">Parameters</span></span>  
 `tkObj`  
 <span data-ttu-id="f306e-106">[in] El token para el elemento de propietario.</span><span class="sxs-lookup"><span data-stu-id="f306e-106">[in] The token for the owner item.</span></span>  
  
 `tkType`  
 <span data-ttu-id="f306e-107">[in] El token que identifica el atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f306e-107">[in] The token that identifies the custom attribute.</span></span>  
  
 `pCustomAttribute`  
 <span data-ttu-id="f306e-108">[in] Un puntero al atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="f306e-108">[in] A pointer to the custom attribute.</span></span>  
  
 `cbCustomAttribute`  
 <span data-ttu-id="f306e-109">[in] El recuento de bytes en `pCustomAttribute`.</span><span class="sxs-lookup"><span data-stu-id="f306e-109">[in] The count of bytes in `pCustomAttribute`.</span></span>  
  
 `pcv`  
 <span data-ttu-id="f306e-110">[out] El `mdCustomAttribute` token asignado.</span><span class="sxs-lookup"><span data-stu-id="f306e-110">[out] The `mdCustomAttribute` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f306e-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f306e-111">Requirements</span></span>  
 <span data-ttu-id="f306e-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f306e-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f306e-113">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f306e-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f306e-114">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f306e-114">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f306e-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f306e-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f306e-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f306e-116">See Also</span></span>  
 [<span data-ttu-id="f306e-117">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f306e-117">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="f306e-118">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f306e-118">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
