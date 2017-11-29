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
ms.openlocfilehash: aefd95f62fce70f87c0724cbb4013462a449c7f0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemitgettokenfromsig-method"></a><span data-ttu-id="85a2f-102">IMetaDataEmit::GetTokenFromSig (Método)</span><span class="sxs-lookup"><span data-stu-id="85a2f-102">IMetaDataEmit::GetTokenFromSig Method</span></span>
<span data-ttu-id="85a2f-103">Obtiene un token para la firma de metadatos especificados.</span><span class="sxs-lookup"><span data-stu-id="85a2f-103">Gets a token for the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85a2f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="85a2f-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromSig (   
    [in]  PCCOR_SIGNATURE pvSig,   
    [in]  ULONG       cbSig,   
    [out] mdSignature *pmsig   
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="85a2f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="85a2f-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="85a2f-106">[in] La firma se conserven y se almacenan.</span><span class="sxs-lookup"><span data-stu-id="85a2f-106">[in] The signature to be persisted and stored.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="85a2f-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="85a2f-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `pmsig`  
 <span data-ttu-id="85a2f-108">[out] El `mdSignature` token asignado.</span><span class="sxs-lookup"><span data-stu-id="85a2f-108">[out] The `mdSignature` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85a2f-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="85a2f-109">Requirements</span></span>  
 <span data-ttu-id="85a2f-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="85a2f-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85a2f-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="85a2f-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="85a2f-112">**Biblioteca:** usada como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="85a2f-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="85a2f-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85a2f-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85a2f-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="85a2f-114">See Also</span></span>  
 [<span data-ttu-id="85a2f-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85a2f-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [<span data-ttu-id="85a2f-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="85a2f-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
