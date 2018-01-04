---
title: "IMetaDataEmit::GetTokenFromSig (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit.GetTokenFromSig
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: df454b8dd95839f4cabe3c725e206f3683437ec4
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="9d4d3-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="9d4d3-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="9d4d3-103">Obtiene un token para la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="9d4d3-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9d4d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9d4d3-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="9d4d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9d4d3-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="9d4d3-106">[in] La firma se conserven y se almacenan.</span><span class="sxs-lookup"><span data-stu-id="9d4d3-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="9d4d3-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="9d4d3-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="9d4d3-108">[out] El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="9d4d3-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9d4d3-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9d4d3-109">Requirements</span></span>  
 <span data-ttu-id="9d4d3-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9d4d3-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9d4d3-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9d4d3-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9d4d3-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9d4d3-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="9d4d3-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9d4d3-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9d4d3-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="9d4d3-114">See Also</span></span>  
 [<span data-ttu-id="9d4d3-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d4d3-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="9d4d3-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9d4d3-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
