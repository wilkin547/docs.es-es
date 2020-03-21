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
ms.openlocfilehash: 8c609d730297881c0ac20dca8569f0e9492638e9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175725"
---
# <a name="imetadataemitgettokenfromtypespec-method"></a><span data-ttu-id="54d91-102">IMetaDataEmit::GetTokenFromTypeSpec (Método)</span><span class="sxs-lookup"><span data-stu-id="54d91-102">IMetaDataEmit::GetTokenFromTypeSpec Method</span></span>
<span data-ttu-id="54d91-103">Obtiene un token de metadatos para el tipo con la firma de metadatos especificada.</span><span class="sxs-lookup"><span data-stu-id="54d91-103">Gets a metadata token for the type with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54d91-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54d91-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTokenFromTypeSpec (
    [in]  PCCOR_SIGNATURE       pvSig,
    [in]  ULONG                 cbSig,
    [out] mdTypeSpec            *ptypespec
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54d91-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54d91-105">Parameters</span></span>  
 `pvSig`  
 <span data-ttu-id="54d91-106">[en] La firma que se está definiendo.</span><span class="sxs-lookup"><span data-stu-id="54d91-106">[in] The signature being defined.</span></span>  
  
 `cbSig`  
 <span data-ttu-id="54d91-107">[en] El recuento de `pvSig`bytes en .</span><span class="sxs-lookup"><span data-stu-id="54d91-107">[in] The count of bytes in `pvSig`.</span></span>  
  
 `ptypespec`  
 <span data-ttu-id="54d91-108">[fuera] El `mdTypeSpec` token asignado.</span><span class="sxs-lookup"><span data-stu-id="54d91-108">[out] The `mdTypeSpec` token assigned.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54d91-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54d91-109">Requirements</span></span>  
 <span data-ttu-id="54d91-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54d91-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54d91-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="54d91-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="54d91-112">**Biblioteca:** Se utiliza como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="54d91-112">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="54d91-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54d91-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54d91-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="54d91-114">See also</span></span>

- [<span data-ttu-id="54d91-115">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54d91-115">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="54d91-116">IMetaDataEmit2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="54d91-116">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
