---
title: IMetaDataEmit::GetTokenFromSig (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.GetTokenFromSig
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::GetTokenFromSig
helpviewer_keywords:
- IMetaDataEmit::GetTokenFromSig method [.NET Framework metadata]
- GetTokenFromSig method [.NET Framework metadata]
ms.assetid: 50a58a83-6287-40a4-b315-47823cea0a5c
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 2f94c12654626e149b0f75327e8fdfa55aefe697
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57467130"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="e2790-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="e2790-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="e2790-103">Obtiene un token para la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="e2790-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2790-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e2790-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e2790-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e2790-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="e2790-106">[in] La firma se conserven y se almacenan.</span><span class="sxs-lookup"><span data-stu-id="e2790-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="e2790-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="e2790-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="e2790-108">[out] El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="e2790-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e2790-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e2790-109">Requirements</span></span>  
 <span data-ttu-id="e2790-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e2790-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e2790-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e2790-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e2790-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e2790-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e2790-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e2790-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e2790-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="e2790-114">See also</span></span>
- [<span data-ttu-id="e2790-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2790-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="e2790-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e2790-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
