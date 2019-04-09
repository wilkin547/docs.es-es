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
ms.openlocfilehash: 242618fb2a5ab748132baf68e24240d1ffaf2301
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139846"
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="09c3f-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="09c3f-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="09c3f-103">Obtiene un token para la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="09c3f-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c3f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09c3f-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09c3f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="09c3f-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="09c3f-106">[in] La firma se conserven y se almacenan.</span><span class="sxs-lookup"><span data-stu-id="09c3f-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="09c3f-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="09c3f-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="09c3f-108">[out] El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="09c3f-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09c3f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09c3f-109">Requirements</span></span>  
 <span data-ttu-id="09c3f-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09c3f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09c3f-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="09c3f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09c3f-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="09c3f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="09c3f-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="09c3f-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="09c3f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09c3f-114">See also</span></span>

- [<span data-ttu-id="09c3f-115">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09c3f-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="09c3f-116">IMetaDataEmit2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="09c3f-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
