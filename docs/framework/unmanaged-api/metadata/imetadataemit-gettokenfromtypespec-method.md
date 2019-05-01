---
title: IMetaDataEmit::GetTokenFromTypeSpec (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 09256deafdb42847f369664ec8c4bc96d72424d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62043134"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="79495-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="79495-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="79495-103">Obtiene los metadatos de un token para el tipo con la firma de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="79495-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79495-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="79495-104">Syntax</span></span>  
  
```  
HRESULT GetTokenFromTypeSpec (   
    [in]  PCCOR_SIGNATURE       pvSig,   
    [in]  ULONG                 cbSig,   
    [out] mdTypeSpec            *ptypespec   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79495-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="79495-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="79495-106">[in] La firma que se está definida.</span><span class="sxs-lookup"><span data-stu-id="79495-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="79495-107">[in] El recuento de bytes en `pvSig`.</span><span class="sxs-lookup"><span data-stu-id="79495-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="79495-108">[out] El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="79495-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79495-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="79495-109">Requirements</span></span>  
 <span data-ttu-id="79495-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="79495-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79495-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="79495-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79495-112">**Biblioteca:** Usar como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="79495-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="79495-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79495-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79495-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="79495-114">See also</span></span>

- [<span data-ttu-id="79495-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79495-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="79495-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="79495-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
