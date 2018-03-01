---
title: "IMetaDataEmit::GetTokenFromTypeSpec (Método)"
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
- IMetaDataEmit.GetTokenFromTypeSpec
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromTypeSpec
helpviewer_keywords:
- GetTokenFromTypeSpec method [.NET Framework metadata]
- IMetaDataEmit::GetTokenFromTypeSpec method [.NET Framework metadata]
ms.assetid: 7de6447a-a751-49d8-87e2-951cee77b536
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 6acb9d340aa1dc8df5d0b9dc3b0c0dd9c159257e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="473ea-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="473ea-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="473ea-103">Obtiene metadatos de un símbolo (token) para el tipo con la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="473ea-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="473ea-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="473ea-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="473ea-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="473ea-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="473ea-106">[in] La firma que se está definida.</span><span class="sxs-lookup"><span data-stu-id="473ea-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="473ea-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="473ea-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="473ea-108">[out] El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="473ea-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="473ea-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="473ea-109">Requirements</span></span>  
 <span data-ttu-id="473ea-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="473ea-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="473ea-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="473ea-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="473ea-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="473ea-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="473ea-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="473ea-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="473ea-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="473ea-114">See Also</span></span>  
 [<span data-ttu-id="473ea-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="473ea-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="473ea-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="473ea-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
